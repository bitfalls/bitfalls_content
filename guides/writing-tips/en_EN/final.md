When writing posts for Bitfalls.com, the following recommendations should be followed for best results. This will lead to quicker editing and turnaround times.

## Titles and Headings

The title of a post will be determined by the editor because SEO takes priority. Feel free to suggest your own titles and they'll be taken into account.

The topmost possible heading in a post is H2 (`##`). In other words, `#` (H1) must not exist, it's reserved for the title. Section titles are `##` (H2), their own subsections `###` (H3) and their own subsection `####` (H4) or bullet point lists (`•`). H4 is also the maximum depth.

Every title **must** have a space character between the symbol and the title. I.e. `##Section` vs. `## Section`.

## Intro and Conclusion

Every (non-news) post should have a short introduction (1 paragraph) explaining what the audience can expect to learn, and what the prerequisite knowledge is. The prerequisites can and should be linked to other Bitfalls posts that cover them.

Every post (especially technical ones dealing with programming and similar topics) should have a conclusion in which a short summary of everything we've learned so far is presented. The conclusion should not have more than 2 paragraphs, and must be an H2 like so: `## Conclusion` (not `Summary` or `To sum up` etc.).

## Links in Markdown

Put links at the bottom of a post, and reference them in the text, like so:

```
This is some markdown text and it has a [link][somelink]. This is a repeat of the [same link][somelink].

...

[somelink]: https://mylink.com
```

This makes handling the links in the text much easier during translation, and improves the readability of the post while it's still in Markdown.

To see an example of this, view the Raw source (button in this UI, top right of this text) of this document and scroll to the bottom.

## Tools

It's recommended you use a dedicated tool for writing Markdown. [Caret][caret] is quite alright, and MacDown on Mac OS is okay too. Good online editors are Stackedit and Dillinger. It's important to have preview mode on during writing, or at least preview once it's written so that you can make sure nothing is broken during the HTML rendering.

To check your grammar and spelling, please use a spellchecker, or even better, a service like Grammarly.

## Images

If a post needs images, please make sure they're public domain (usable for any purpose) or that you have express written permission from the author to use them in an article on Bitfalls.com. Images must be placed inside an `images` folder which gets created alongside the language folders of a post, like so:

    - 01-post/
        - en_EN/
          - final.md
        - images/
          - 01.jpg
          
Images should be named numerically and sequentially based on their position in the post, for easier adding into the article during publication. The main image which will serve as the thumbnail and header should be called `header` and end with one of the following: `.jpg`, `.png`, or `.gif`.

## Article Length and Multi-Page Posts

Optimal article length is (with possible exceptions):

- news: 200 - 500 words
- guide: up to 1200 words
- technical guide or programming tutorial: up to 2000 words

Source code doesn't count.

If an article is exhaustive enough to surpass 2000 words, it's possible to split it into 2 parts. The maximum number of parts an article will ever have is 2. If more is needed, the article will be turned into a series in which every part **must** be as standalone as possible - the modern audiences lose interest when they see too many interdependent articles. These individual articles should then reference others, but not depend on them.

## Linking to Content

Where possible, the author should link to other Bitfalls posts. For example, if an article mentions the blockchain, the author should link to [this post][blockchain]. If an article mentions the bitcoin bubble popping, the author should link to [this post][bubble], etc. It's important to keep the language in mind - link to the language of the post in which you're writing your current post, so English to English, Croatian to Croatian, etc.

When appropriate (not always and not often), mention and link to products from our web shop. We don't want to push it, but keep in mind that successful sales (along with crypto sales and consultation) fund our operation and our author payouts. More sales mean more room to publish posts which means more work for authors.

## Pronouns

Posts should be objective and neutral whenever possible, except in certain circumstances when we're publishing editorials or columns. Hence, please avoid "I" and focus on either "we" or "you", but stick with one. For example, instead of:

_"In this example, I'll show you how to connect to an external API so that you'll know how to do that in your own projects later."_

Say:

_"In this example we'll hook things up to an external API in order to be able to easily do this in our own projects later on."_

Instead of "he" or "she" use the neutral "they". I.e. "Once the user completes the purchase, we can send the tokens to his account." vs "Once the user completes the purchase, we can send the tokens to their account."

For other useful writing advice, please see [this amazing post][guide].

## Source Code

When writing code, you **must** fence it into triple backticks, as explained [here][codefence]. Don't forget the language hint in the first fence.

        ```solidity
        struct Voter {
                uint weight; // weight is accumulated by delegation
                bool voted;  // if true, that person already voted
                address delegate; // person delegated to
                uint vote;   // index of the voted proposal
            }
        ```
        
## What NOT to do

- don't use referral links
- don't ask for donations or put your address into articles
- don't advise people to buy a cryptocurrency directly (i.e. "I think you should buy this because it'll rise in value"). We're not an investment advisor, and all the endorsement we can do is the informal type - reviews through posts on the site.

[caret]: https://caret.io
[blockchain]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[bubble]: https://bitfalls.com/2017/09/06/bitcoin-bubble/
[guide]: https://www.impressivewebs.com/how-to-write-great-web-development-articles-tutorials/
[codefence]: https://help.github.com/articles/creating-and-highlighting-code-blocks/