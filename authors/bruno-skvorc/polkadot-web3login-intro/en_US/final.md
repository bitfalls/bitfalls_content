This tutorial is part 1 of the process of adding web 3.0 login to a legacy web 2.0 PHP application.

---

_If you would just like to download the final state of the [Part 1 Crowdcast](https://www.crowdcast.io/e/web3-logins-workshop?utmsource=profile&utmmedium=profileweb&utmcampaign=profile), that is, the final result of this tutorial, clone the `part-1-done` branch of [swader/phpback](https://github.com/swader/phpback) and modify the `config/database.php` file to match your database setup._

---

Important notes:

- the PHP application is open source and thus hackable. This process cannot be applied to an app you do not control or cannot modify.
- adding Web 3.0 logins in this case does not make the PHP app a "dapp" (decentralized app). Instead, it merely allows people to register and log in using their crypto wallet rather than a username and password combination. This essentially turns a user's crypto identity into a single-sign-on experience if other apps adopt the same or similar login flow.

## Prerequisites

- PHP with [Composer](https://getcomposer.org/) installed.
- MySQL installed and running.
- [NodeJS](https://nodejs.org) with [Yarn 1](https://classic.yarnpkg.com/lang/en/) available globally on your machine. Preferably via [NVM](https://github.com/nvm-sh/nvm) so you can switch versions at will.

_Alternatively, use a Vagrant box such as [Laravel Homestead](https://laravel.com/docs/6.x/homestead). It comes with all of this pre-installed and configured for you and results in a much cleaner development environment._

You also need to have a MySQL user `phpback` configured with all permissions on an empty `phpback` database ([MySQL Workbench](https://www.mysql.com/products/workbench/) is a useful tool to have installed).

## PhpBack

The application we'll be upgrading is [PhpBack](https://phpback.org). It's an open source version of [UserVoice](https://uservoice.com) built on an outdated version of the CodeIgniter framework. It wasn't exactly developed with best practices in mind, which is perfect for us since our implementation is also a hack 🙃

Let's install PhpBack.

```bash
git clone https://github.com/swader/phpback
cd phpback
composer install
php -S localhost:8085
```

This will start a PHP server and host the application for local use. If you hit that URL now, the app should be there - you should be greeted by the install step.

![Install screen](https://bitfalls.com/wp-content/uploads/2020/02/01.jpg)

Fill out all the information. On the second screen, leave recaptcha empty and put any information (valid or not) into the email configuration fields - we won't be sending any emails so this doesn't matter.

The PhpBack app is now installed. Feel free to explore its various screens, try out the features, look through the admin dashboard (you created the admin account on the first installation screen), and more. Once you're comfortable with what the app does, proceed to the next step.

## Adding Web3 Libraries

The plan is to let users sign into the application by selecting one of their Web3 accounts and providing a username if they haven't yet registered, or just signing in by signing that username cryptographically, proving they own it.

### The Extension

We'll make an assumption that our user will have the [Polkadot{.js} extension](https://github.com/polkadot-js/extension) installed. This extension manages Polkadot-related Web3 accounts for users. In other words, this is your browser-based stash of accounts which you can then use to interact with any Web 3.0 enabled system. If you do not have it installed, please install it now into at least one of your browsers.

### The JS Libraries

To interact with Web3 accounts managed by the above extension, we need the following libraries:

- [@polkadot/api](https://github.com/polkadot-js/api)
- [@polkadot/extension-dapp](https://github.com/polkadot-js/extension/tree/master/packages/extension-dapp)

The former is a collection of JS utilities to interact with Substrate-based blockchains like Polkadot, Kusama, Edgeware or generic Substrate. It's what allows us to interact with the "web 3.0 layer".

The latter is a convenience library which connects the former to the browser extension we previously installed. In short, with this combination we have JS-level access to Web3 accounts in the browser, and can interact with desired Web3 nodes running our blockchain of choice.

However, since we're upgrading a PHP application and these libraries are very much NodeJS oriented, we need to package them up into a single file we can include in the template of our application.

Browserify is a tool for exactly that, and we can run it without installing it using `npx` which comes bundled `npm` and tools.

```bash
yarn init # Initializes the project, creates package.json file - asks you questions
```

Pressing _Enter_ after each question posed by `init` is good enough. Then:

```bash
yarn add @polkadot/api @polkadot/extension-dapp
```

Then we'll create a file `dependencies.js` in the same folder with the following content:

```js
let api = require("@polkadot/api");
let util = require("@polkadot/util");
let util_crypto = require("@polkadot/util-crypto");
let dappex = require("@polkadot/extension-dapp");

window.api = api;
window.util = util;
window.util_crypto = util_crypto;
window.dappex = dappex;
```

Finally, we run:

```bash
npx browserify dependencies.js > public/js/bundle.js
```

This will take all the JavaScript packages we required in `dependencies.js` and package them up for us into `bundle.js` which we can just include into any web page, not just a NodeJS project.

### Adding Bundle.js to PhpBack

_Note: when modifying a PHP application, it helps to be familiar with it. This application uses an old version of the CodeIgniter framework so exploring it manually and looking at the files is essential to figuring out what's what. Feel free to look (and poke) around!_

The main layout of the app consists of three parts: the header, found in `\application\views\_templates\header.php`, the core of the page which contains the content, and the footer, found in `\application\views\_templates\footer.php`.

The footer will have what we need - included JavaScript files. Let's add our `bundle.js` file there so it looks like this:

```html
    ...
    <script src="<?php echo base_url(); ?>public/js/jquery.tagsinput.js"></script>
    <script src="<?php echo base_url(); ?>public/js/jquery.placeholder.js"></script>
    <!-- -------↓↓↓↓ ADD THIS LINE ↓↓↓↓------ -->
    <script src="<?php echo base_url(); ?>public/js/bundle.js"></script>
    <!-- -------↑↑↑↑ ADD THIS LINE ↑↑↑↑------ -->
    <script src="<?php echo base_url(); ?>public/bootstrap/js/application.js"></script>
    <script>
        $('.popover-with-html').popover({ html : true });
        $('.contentdiv').css('width', '100%').css('width', '-=400px');
    </script>
    ...
```

If we refresh the PhpBack application in our browser now (it should still be running at `localhost:8085`), we should be able to interact with our Polkadot Web3 libraries from the browser console. Try opening the dev tools, enter the console, and input `dappex.isWeb3Injected`, which should return true. Then try `dappex.web3Enable()`, which should bring up a popup asking you to authorize the application to access the Polkadot JS browser extension as in the image below.

![Dappex popup](https://bitfalls.com/wp-content/uploads/2020/02/03.jpg)

Let's explain what's going on.

Dappex is the variable we picked for the `dapp-extension` utility package we installed via `dependencies.js` earlier. It lets us access the extension and any accounts inside it. By including `bundle.js` in the web page, we have access to `dappex` which lets us query for web3 availability (returns true because we installed PolkadotJS into the browser), and lets us request authorization to access accounts in the extension, which summons the popup. Once confirmed, other options become available, like `dappex.web3Accounts()` which returns all accounts in a particular extension.

One more thing to do before we start hacking. To be able to interact with web3, we'll need somewhere to put our scripts. There exists an `application.js` file among the files, but for some reason it's not included in the footer. Modify the footer to include it:

```html
    <script src="<?php echo base_url(); ?>public/js/jquery.tagsinput.js"></script>
    <script src="<?php echo base_url(); ?>public/js/jquery.placeholder.js"></script>
    <script src="<?php echo base_url(); ?>public/js/bundle.js"></script>
    <script src="<?php echo base_url(); ?>public/bootstrap/js/application.js"></script>
    <!-- -------↓↓↓↓ ADD THIS LINE ↓↓↓↓------ -->
    <script src="<?php echo base_url(); ?>public/js/application.js"></script>
    <!-- -------↑↑↑↑ ADD THIS LINE ↑↑↑↑------ -->
    <script>
        $('.popover-with-html').popover({ html : true });
        $('.contentdiv').css('width', '100%').css('width', '-=400px');
    </script>
```

## Modifying the Database

To store the association between a user's crypto address and their username, we'll need to alter the database slightly. In MySQL workbench or any other tool you're using to manage your databases, modify the `phpback.users` table so that it contains an additional `address` field, type VARCHAR(50), nullable (because we want to support non-crypto users) and unique (one username per address). The full alter query is:

```sql
ALTER TABLE `phpback`.`users` ADD COLUMN `address` VARCHAR(50) NULL AFTER `banned`, ADD UNIQUE INDEX `address_UNIQUE` (`address` ASC) VISIBLE;
```

## Offering Accounts

Let's load and offer the user their web3 accounts when they try to log in or register now.

### Buttons and Select Boxes

The view screens we have to change are `login.php` and `register.php`, found in `/application/views/home`. At the bottom of the views under the closing `form` tag, we put the following:

<script src="https://gist.github.com/Swader/da49a60ff97161d70c8f544826179d69.js"></script>

Refreshing the app should now produce the buttons on the login and registration screen.

### Grabbing and Showing Web3 Accounts

The rest of the tasks we have to accomplish are:

- ask for PolkadotJS access and get web3 accounts
- show web3 accounts to user, prompting a selection
- once selected, the user should confirm selection with an additional button (prevent fat-fingering the wrong account)

#### Asking for Access

Let's open up `public/js/application.js` and edit it. We'll add two event listeners to our newly added buttons.

```js
  document.querySelector("#web3login").addEventListener('click', initWeb3Login);
  document.querySelector("#web3loginConfirm").addEventListener('click', checkUser);
```

First things first, the `initWeb3Login` flow needs to be created before we `checkUser`.

```js
  function initWeb3Login() {
    dappex.web3Enable().then(function(){
      if (!dappex.isWeb3Injected) {
        alert("You need a Web3 enabled browser to log in with Web3. The easiest solution is probably to install the Polkadot{js} extension.");
      } else {

        dappex.web3Accounts().then( async (accounts) => {
          showPicker(accounts);
        } );
      }
    });
  }
```

_Note: the above can be added just above the closing `jQuery` line in the JS file._

This function asks for app-to-extension access with `web3Enable()`. If the extension isn't installed in a browser, an alert pops up, prompting the user to install the extension.

_Bonus task: hide the Log in with Web3 button if the extension is not detected!_

We then request the accounts with `web3Accounts()` and as soon as we get them we call an as of yet non-existent `showPicker` function.

#### Showing the Accounts

```js
  function showPicker(accounts) {
    let options = '';
    accounts.forEach(element => {
      options += '<option value="'+ element.address +'">'+ element.meta.name + ' - ' + element.address +'</option>';
    });
    let selector = document.querySelector("#web3accounts")
    selector.innerHTML = options;
    selector.style.display = "inline-block";
    document.querySelector("#web3loginConfirm").style.display = 'block';
  }
```

This function consumes the accounts we provided in the last step, iterates through them, and builds a rudimentary set of select options for the `select` element we built in the Buttons and Select Boxes step above. Testing the `Log in with Web3` button should now produce some results:

![](https://bitfalls.com/wp-content/uploads/2020/02/04.jpg)

We can select our accounts by name and address. The caveat is that at this moment, the extension only gives us [Substrate-type addresses](https://wiki.polkadot.network/docs/en/learn-accounts), regardless of which network we're using in the extension. This has no implication on our implementation, but might affect other use cases. It's [being worked on](https://github.com/polkadot-js/extension/issues/250).

The user can now click the "Confirm Login" button, but nothing will happen.

## Conclusion

This brings us to the end of Part 1. In the next part, we'll:

1. Check if the selected address is already in our database.
2. Ask the user to pick a username and sign it if not, or to sign the username if yes.
3. Log the user in as a regular user, allowing them to perform all the usual actions.
