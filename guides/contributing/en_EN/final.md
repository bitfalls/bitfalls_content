This document describes the process of sending a draft of an article into our content repository. This lets other authors review it (peer review) in order to achieve the highest possible quality of the article before publication.

_Before getting started it's highly recommended you introduce yourself to Git and Github concepts via [Github Guides](https://guides.github.com). While a little more complex than just clicking buttons in an app's user interface, we wholeheartedly recommend using a command line application like [Git bash](https://git-scm.com/downloads) to run the commands below if you're on Windows, or Terminal if you're on Linux or Mac OS - this is so that everyone can follow the same instructions._

## Preparation: Github and the authors team

If you don't have one, please make a Github.com account. Then register as an author for Bitfalls.com via email as described [here][wfu]. After approval, you'll be added to the team and can get started following the steps below.

## Step 1: Fork

If this is the first time you're contributing, you need to make your own fork of the repository. This is done with the Fork button.

![Fork](../images/03.png)

If you already have a fork of the repo, the Fork button will take you to it. In that case, it's possible some new content was added since you last forked, and you'll need to bring the fork in sync with the original repo. This process is described in the Extras section below.

Once fully in sync, your fork can be cloned (downloaded) to your computer using the command line of the operating system you're on (the recommended [Git Bash](https://git-scm.com/downloads) or CMD if on Windows, or Terminal on Linux and Mac OS), or with one of the many desktop apps on offer for Git, like [Github's official app](https://desktop.github.com/).

Here's how that looks when using the command line:

![GIF korištenja Git Bash za kloniranje repozitorija](../images/04.gif)

Here I've cloned the repo to my own computer, used the `cd` command to enter the newly created folder, and used the `ls ` command to `list` the contents of the folder, and of the `authors` subfolder. Had I already downloaded the `bitfalls_content` folder previously, a simple `git pull` command inside it would have been enough to download the latest changes from my own fork on Github.com.

## Step 2: Folder Structure

All submitted articles **must** follow a specific structure:

- in the `authors` folder, you'll find a folder named after your Github username
- for every new post, make a new folder starting with a number that's 1 higher than the previous one and ends with `-title`. For example, if you're writing a post about "Intro to Solidity" and it's the first post you're writing on our platform, you should call the folder `01-intro-to-solidity`.
- every post is currently being published in both Croatian and English. Depending on which language you're sending it in, you need to make the appropriate subfolder: `en_EN` for English, `hr_HR` for Croatian. If the article will need some images, an `images` folder is also required. Note that images can be public domain only - free for use without restriction. No copyrighted or licensed images.
- the content must be written in [Markdown](https://guides.github.com/features/mastering-markdown/) format
- the name of the file that contains the post's actual content must be `final.md`, so that a post with two languages and some images looks kind of like this:
  ![Struktura datoteke nekog članka](../images/02.png)
  
Only **one article per branch**. If you're writing several posts at the same time, use several branches - one for each. Suppose you got approval to write "Intro to Solidity" and "Advanced Solidity". The steps are as follows, if you're using the command line as recommended above:

1. Download your fork's latest copy. If not already on your personal computer, clone with `git clone https://github.com/myusername/bitfalls_content`. Otherwise, go into the `bitfalls_content` folder and execute `git pull`.
2. Create a new branch for the first post: `git checkout -b 00-intro-to-solidity`
3. Write the post as per structure outlined above
4. When the first post is done, the commands `git add -A` and `git commit -am "Adding first post"` will save the progress for sending it online later.
5. Create a new branch for the second post: `git checkout -b 01-advanced-solidity`
6. If during the writing of the second post you remember some edits are needed in the first post, you can save the progress of the second post with `git add -A` and `git commit -am "Saving progress"` and switch to the previous branch with `git checkout 00-intro-to-solidity`. Do the needed changes, save again with `git add -A` and `git commit -am "Saving some changes"`, then come back to the `01-advanced-solidity` branch with `git checkout 01-advanced-solidity`. Do this as many times as necessary.

## Step 3: Sending

When you're ready to send in an article, you have to upload it to your fork on Github.com first. The way to do this via the command line is by executing the following to first save the progress of your branch as described above while in the `bitfalls_content` folder:

```bash
git add -A
git commit -am "adding some article"
```

Make sure you're on the branch you want to send - if unsure, check with `git branch`. After you're certain it's the right one, send it online with:

```bash
git push origin BRANCH
```

(replace BRANCH with your branch name - the name you picked earlier)

If you're using a tool like Github Desktop or Git Tower, follow the instructions of the tool to accomplish the same thing.

After the article is up on Github.com, a new option will appear on your fork's main page: Create Pull Request. Click it, fill the fields if you have something to say or skip them if not, and click the new Create Pull Request button, now under those fields. This will send the article to the original repository where everyone will be able to take a look at it.

## Step 4: Peer Review

Wait for feedback from other authors and pay attention to their comments. Discuss suggestions and don't take feedback personally - we all want to create the best possible content and are working together on making that happen.

While you wait for feedback on your own post, feel free to check the work of other authors and make comments, suggest changes, praise their work, etc. They'll appreciate it and will love the chance to improve.

To find posts in need of peer review, please see the [Peer Review Needed](https://github.com/Swader/bitfalls_content/labels/Peer%20Review%20Needed) label.

## Step 5: Publication and payment

After enough people have taken a look at the post draft or the editor has decided it's in publishable shape, you'll be informed about this via email and your Pull Request will be pulled - absorbed into the main repo. The post will be published and you'll be paid as per prior arrangement.

The article then becomes the intellectual property of Bitfalls d.o.o., but the author stays the author in name and rights and can identify as such in media. To republish the post, the person wanting to republish it - even if it's the author - must ask for and get written permission from Bitfalls d.o.o.

## Rejection

It is possible to have a Pull Request rejected. This will happen if the post is in a state of disrepair such that it is impossible to fix it without a full rewrite, if it is plagiarized, if it states false information, etc. In those cases, you will **not** be paid but we also won't claim intellectual property on it - you can publish it elsewhere if you wish. Please keep this in mind and make sure you produce the best possible content.

## Extras

### Syncing a fork with the original

The process is described in detail [here](https://www.sitepoint.com/quick-tip-sync-your-fork-with-the-original-without-the-cli/) (with pictures!) but in a nutshell:

- open your fork's page on Github.com
- click "New Pull Request" to get to the "Comparing Changes" screen
- there should be a "Switching the base" link in the middle of the text in the center of the screen, as in the picture:
  ![Switching the base](../images/01.png)
- click "Create Pull Request" leaving the input fields empty. Alternatively, type in what's going on, so you have a note for your future self. Click "Create Pull Request" again to finalize this decision.
- click "Merge Pull Request" to finish syncing

### Risk of Content Theft

Many people feel like exposing upcoming content on a public repository like this is naïve, and that competing publications will only steal it to publish it before us. While this is a possibility, we think that the transparency and openness towards a peer review process outweighs this risk, because it leads to higher quality. If someone should steal our content, they'll be easy to identify and call out publicly, and since we're an actual company with intellectual property we'll likely have the means to follow up with legal defenses as well. Hence, we'd rather recommend that competing publications get in touch regarding collaboration - we're quite open about that, too.

### Why so Complicated?

A frequent question is why complicate matters so much with this Github process. The answer is twofold. This process guarantees:

- a basic technical literacy of the authors, which is important when trying to present technical topics to a non-technical audience. Cryptocurrency is, after all, still a technical topic, albeit one which we're trying to make non-technical.
- a public discussion around content in order to improve the quality of the final draft.

These two factors in tandem make sure our published work is of the highest quality, while also preventing editor monopoly.

[wfu]: https://bitfalls.com/write-for-us