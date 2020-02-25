This is a continuation of the tutorial on adding Web3-based logins to an old PHP application. To follow along, go through the first part, or just clone the `part-1-done` branch from [this repository](https://github.com/swader/phpback).

> If you're starting from the branch, please make sure you changed the database credentials in `config/database-example.php` and renamed the file to just `database.php`, and make sure that your `users` database table has an address field as per [Part 1](https://bitfalls.com/v5l6).

Let's dive right into it. If your app isn't running, run the PHP local server inside the phpback folder with `php -S localhost:8085`, then visit the app in the browser at `localhost:8085/`.

## Checking if a User Exists

In the previous part we defined an event listener for our "Confirm" button which called `checkUser`, a function we'll implement now.

```js
  async function checkUser() {
    $.ajax('/action/web3login', {data: {
      'address': document.querySelector("#web3accounts").value
  }}).then(
      function(r) {
        if (r.status == 200) {
          // Check if user exists. If not, offer to pick username.
          if (parseInt(r.payload) > 0) {
            console.log("User found");
            //loginWeb3(r.payload);
          } else {
            console.log("User not found");
            let newUsername = prompt("Pick a username");
            if (newUsername === "" || newUsername === null) {
              return;
            } else {
              console.log("Picked: " + newUsername);
              // registerAndLoginWeb3(newUsername);
            }
          }
        } else {
          alert("That didn't work, try again: " + r.payload);
        }
      }
    );
  }
```

Lots to unpack here!

When the user confirms the selection of their account, we emit an ajax call to the endpoint `/action/web3login` which we've yet to create. We pass along the address that the user selected. We then react to the response which will have a payload and a status.

If the status is 200 (OK), we check the payload, otherwise we error out. In case of a success, we check how many accounts we have in the payload. Anything more than 0 means we found an account with this address and the user can log in (`loginWeb3` function). Zero means there is no account with such an address, so we can create it - that's the `registerAndLoginWeb3` placeholder function.

Let's build the user-checking endpoint now. In `/application/controllers/action.php` we'll add two functions.

```php
   public function web3login() {

        if ($_SERVER['REQUEST_METHOD'] === 'GET') {
            $address = $_GET['address'] ?? false;
            if (!$address) {
                $this->jsonReturn(null, false, "No address found!");
            }
            // CHECK IF USER EXISTS
            $this->jsonReturn($userExists);
        }

        // MORE STUFF HERE
    }

    private function jsonReturn($data, $success = true, $msg = "") {
        header('Content-Type: application/json');
        die(json_encode(($success) ? ["status" => 200, "payload" => $data] : ["status" => "error", "payload" => $msg]));
    }
```

The `jsonReturn` function is a utility function to return JSON responses from PHP. The JSON object it returns always has a payload property, and a status property. Such standardization makes it easy to create API calls from the JavaScript side.

The `web3login` function first checks if the request type is GET, so a simple reading operation. It checks if the address is set, and errors if not. Then it checks if the user exists (placeholder) and returns the result.

Curiously, we can find all database accessors squeezed into `models/get.php` for read operations and `models/post.php` for write operations. Since our user checking operation is a reading type, we'll update `get.php` with a new function.

```php
    public function getUserByAddress($address) {
    $sql = $this->db->query("SELECT * FROM users WHERE `address`= '".$address."'");
        if($sql->num_rows() != 0){
            $user = $sql->row();
            return $user->id;
        }
        return false;
    }
```

_Note: some of you will have noticed that all the queries in this file are vulnerable to SQL injection. Can you think of a way to prevent this?_

The function is rather straightforward - it gets a user by registered address and returns the ID or `false` otherwise.

Now we can replace our `// CHECK IF USER EXISTS` placeholder above with:

```php
$userExists = $this->get->getUserByAddress($address);
```

Testing the application now should let us input a username and then echo it in the console.

![A working user-check](https://bitfalls.com/wp-content/uploads/2020/02/check.gif)

## Offering a Registration

We let the user select a username, but we didn't do anything with it after confirming the input. Let's sign that username with the user's cryptographic key, check that the signature is valid on the server-side, and then store the address in the database if so.

First let's uncomment the placeholders `// registerAndLoginWeb3(newUsername);` and `// loginWeb3(r.payload);`. Then, let's create these functions.

```js
  async function registerAndLoginWeb3(username) {
    console.log("Registering " + username);

    // SIGN THE USERNAME

    // SEND TO BACKEND
  }

  async function loginWeb3(userId) {
    // Nothing here yet...
  }
```

Now let's sign a message containing the username. This will be our proof that _this_ particular address claimed _this_ particular username some time in the past. Replace the `//SIGN THE USERNAME` placeholder above with:

```js
    const address = document.querySelector("#web3accounts").value;
    const web3 = await dappex.web3FromAddress(address);
    const signer = web3.signer;
    const hexUsername = util.stringToHex(username);
    const signed = await signer.signRaw({
      type: 'bytes',
      data: hexUsername,
      address: address
    });
```

We grab the selected address from the account selector, and we create a web3 object from this selected address. Such an object contains web3 interfaces that now relate to this particular address, including a signer object which we use to, well, sign messages. That's what we do in the last two lines - we convert the username to its hex format, and then sign with `address` the message `username`. The signed message (in `signed.signature`) looks something like:

```bash
0x6efaba5d87445291e8ba95119715f215cf0839b7160c609adc1f3015a70cdc507dc2073a119452b23f2fcfebf0fe1d0abf5dc27c8704133bfc2e0535e13ef287
```

You can verify it live in the [Polkadot UI toolbox](https://polkadot.js.org/apps/#/toolbox/verify).

The next step is to submit the address, username, and signature to the back end. The back end needs to check if the username has already been claimed and reject the attempt if so. Otherwise, we create a new user account. Let's replace the `// SEND TO BACKEND` placeholder above with:

```js
    $.post('/action/web3login', {'username': username, 'address': document.querySelector("#web3accounts").value, 'signed': signed, 'act': 'register'}
    ).then(function(r){
      if (r.status == 200) {
          alert("Success! Username registered. Now log in!");
        window.location.replace("/home/login");
      } else {
        alert("Failed to create user :( " + r.payload);
      }
    });
```

This will reload the page when the user has been registered, allowing them to restart the process and log in.

## Login flow

First, we need to modify `post.php`'s `add_user` function. If you look at it, you'll notice it doesn't store the address anywhere while inserting the user. Let's add this part in so that we can actually create users the way we want.

```php
    public function add_user($name, $email, $pass, $votes, $isadmin, $address){
        // ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ ADD THIS ^^^^^^^^

        $pass = $this->hashing->hash($pass);
        // ...

        if($isadmin){
            $data = array(
                'name' => $name,
                // ...
                'banned' => '0',
                'address' => $address // <--- ADD THIS
            );
        }
        else{
            $data = array(
                'name' => $name,
                // ...
                'address' => $address // <--- ADD THIS
            );
        }

        //...
    }
```

The `add_user` function now supports address insertion.

Let's go back and update `web3login()` in `action.php` now.

Replace the `// MORE STUFF HERE` placeholder with:

```php
    if ($_SERVER['REQUEST_METHOD'] === 'POST') {

        $address = $_POST['address'] ?? false;
        if (!$address) {
            $this->jsonReturn(null, false, "No address found!");
        }

        $signature = $_POST['signed'] ?? false;
        if (!$signature) {
            $this->jsonReturn(null, false, "No signed message found!");
        }

        $action = $_POST['act'] ?? false;
        if ($action === 'register') {

            // Registration flow

            $username = $_POST['username'] ?? false;
            if (!$username) {
                $this->jsonReturn(null, false, "No username found!");
            }

            $userExists = (bool)$this->get->getUserIdByUsername($username);
            if ($userExists) {
                $this->jsonReturn(null, false, "Username already taken!");
            }

            // VERIFY SIGNATURE

            $userCreated = $this->post->add_user($username, $address.'@irrelevant.foobar', md5(rand(1,100000)), 14, false, $address);
            if ($userCreated) {
                // return ID
                $user = $this->get->getUserByAddress($address);
                $this->jsonReturn($user->id);
            }
            $this->jsonReturn(null, false, "Failed to create user!");

        } else if ($action === 'login') {

            // Log the user in if verification of signature is successful
            $checkingString = "wannaLogin";

            // VERIFY SIGNATURE

            // Log user in
            session_start();
            $user_id = $this->get->getUserByAddress($address);
            $user = $this->get->getUser($user_id);
            $this->get->setSessionUserValues($user);

            $this->jsonReturn($user_id);

        } else {
            $this->jsonReturn(null, false, "Unknown action: " . $action);
        }
    }
```

Let's break this behemoth down! When the method is `POST` (meaning, a form submission), we check if address and a signed message are present. If not, we error out - both our registration and login flow require them. Then we check which action we're dealing with - registration or login. We'll pass that in as a parameter from JS.

In Registration mode, we grab the selected username, check that it isn't already claimed, and create a user. We return the user ID.

In Login mode, we have a mock string to sign and check (the message is the same in JS and PHP), and once the user is verified to have signed the message we log them in by starting a session and setting the variables needed to persist it. We also return the user ID.

The only thing missing in both is `// VERIFY SIGNATURE` which we'll deal with later.

In `/applications/models/get.php`, we add another function, one that we used in the above code without building it first:

```php
    public function getUserIdByUsername($username) {
        $sql = $this->db->query("SELECT * FROM users WHERE `name`='" . $username . "'");
        if($sql->num_rows() != 0){
            $user = $sql->row();
            return $user->id;
        }
        return false;
    }
```

Now we can fetch the user ID by username.

The `web3login()` function in `application.js` which we previously left empty with the placeholder `// Nothing here yet...` should be modified to look like this:

```js
  async function loginWeb3() {
    const address = document.querySelector("#web3accounts").value;
    const web3 = await dappex.web3FromAddress(address);
    const signer = web3.signer;

    console.log(signer);

    const hexMessage = util.stringToHex("wannaLogin");
    const signed = await signer.signRaw({
      type: 'bytes',
      data: hexMessage,
      address: address
    });

    $.post('/action/web3login', {'address': document.querySelector("#web3accounts").value, 'signed': signed.signature, 'act': 'login'}
    ).then(function(r){
      if (r.status == 200) {
        window.location.replace("/home");
      } else {
        alert("Failed to create user :( " + r.payload);
      }
    });
  }
```

Here we sign a mock message, the one we also have in PHP, and send the signed message and address to the back end with the `login` action. If the login process was successful (i.e. it did not return an error), then we redirect the user home, where they will find that they've been logged in.

You can already test the app even though the signature verification is mocked. If you enter a custom username after selecting an address and sign the username, a new user will be created as long as the username and address are both unique.

Likewise, you can log into the application with a created user if you add a new address into the system. However, we're currently letting anyone log in as anyone without checking the signature. It's time for signature verification.

## Signature Verification

Finally, the **meat** of this tutoral. How to verify these crypto signatures?

There are two caveats to keep in mind.

1. There exists no PHP implementation of Polkadot's APIs, so doing the verification in PHP is not doable right now. We'll have to use JavaScript server-side, and call it from PHP.
2. The easy verification functions we'll be using only exist in the beta versions of the newest `util-crypto` libraries of Polkadot-JS. We'll need to upgrade our dependencies and rebuild our bundle.

Let's do the second goal first. In `package.json` add:

```bash
  "resolutions": {
    "@polkadot/keyring": "^2.6.0-beta.0",
    "@polkadot/util": "^2.6.0-beta.0",
    "@polkadot/util-crypto": "^2.6.0-beta.0"
  }
```

This forces certain versions on some dependencies, even if the master package calling them (`@polkadot/api`) requires another version. Note that this only works with [Yarn](https://classic.yarnpkg.com/).

Then re-run Browserify:

```bash
npx browserify dependencies.js > public/js/bundle.js
```

Our bundle file is now rebuilt, the easy part is done. We have access to new functionality, now let's use it.

### Verifying Signed Messages

We'll:

1. Write a simple NodeJS script to do the verification.
2. Call this script from PHP.
3. Parse the result and reach a conclusion.

The NodeJS script can be placed in the root of the folder, alongside `dependencies.js`. Let's call it `simpleVerify.js`.

```js
let util_crypto = require("@polkadot/util-crypto");

util_crypto.cryptoWaitReady().then( () => {
    const verification = util_crypto.signatureVerify(process.argv[2], process.argv[3], process.argv[4]);
    if (verification.isValid === true) {
        process.exitCode = 0;
    } else {
        process.exitCode = 1;
    }
})
```

We import the crypto utilities which contain the useful `signatureVerify` function, and once the cryptography libraries have initialized (in particular, sr25519 which we're using here needs a piece of WASM to warm up) we process the input and pass it into the function. If the signature is valid the process will exit with a standard `0` for success, or `1` otherwise.

Then, let's replace the `// VERIFY SIGNATURE` placeholders in the PHP code above with:

```php
    $ret = exec("node simpleVerify.js \"".$username."\" ".$signature." ".$address." 2>&1", $out, $err);
    if ($err) {
        $this->jsonReturn(null, false, "Signature mismatch! You cannot register this username");
    }
```

Under the `login` section do the same but replace `$username` with `$checkingString`.

And that's it. If the signature does not match, as returned by the numeric value 1 from the invoked JS script, we emit an error. Otherwise, the flow continues.

Feel free to test the app now!

## Conclusion and Homework

We're done - the user is now logged in an can perform any action a regular PhpBack user would be able to do. As a bonus way to practice, try to tweak the app in the following ways:

1. Hide the web3 buttons if no extension is detected.
2. Improve the account selection - either with a prettier select dropdown or a popup.
3. Remove the danger of SQL injection from the models.
3. Beautify the "select a username" popup from the default JavaScript popup to something fancier. Additionally, make sure the username is unique before allowing a user's submission!
3. [CHALLENGING] Try to integrate [identities](https://wiki.polkadot.network/docs/en/learn-identity) into the account fetching so you grab the username from on-chain!

If you'd like to see how any of the above is done, [let me know](https://twitter.com/bitfalls) and we'll set up a live screencast or write a tutorial.

> For more regular news about Web3.0, sign up for the [DotLeap Newsletter](https://dotleap.substack.com).
