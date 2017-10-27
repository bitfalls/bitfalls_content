The following tips will, when applied, dramatically speed up editing times because of less back-and-forth communication being required between the editor and author. Please take them into consideration and make them a part of your writing habit.

## Tip 1: Titles and Headings

The title of a post will be determined by the editor because SEO takes priority. Feel free to suggest your own titles and they'll be taken into account.

The topmost possible heading in a post is H2 (`##`). In other words, `#` (H1) must not exist, it's reserved for the title. Section titles are `##` (H2), their own subsections `###` (H3) and their own subsection `####` (H4) or bullet point lists (`•`). H4 is also the maximum depth.

Every title **must** have a space character between the symbol and the title. I.e. `##Section` vs. `## Section`.

## Tip 2: Intro and Conclusion

Every (non-news) post should have a short introduction (1 paragraph) explaining what the audience can expect to learn, and what the prerequisite knowledge is. The prerequisites can and should be linked to other Bitfalls posts that cover them.

Every post (especially technical ones dealing with programming and similar topics) should have a conclusion in which a short summary of everything we've learned so far is presented. The conclusion should not have more than 2 paragraphs, and must be an H2 like so: `## Conclusion` (not `Summary` or `To sum up` etc.).

## Tip 3: Links in Markdown

Put links at the bottom of a post, and reference them in the text, like so:

```
This is some markdown text and it has a [link][somelink]. This is a repeat of the [same link][somelink].

...

[somelink]: https://mylink.com
```

This makes handling the links in the text much easier during translation, and improves the readability of the post while it's still in Markdown.

To see an example of this, view the Raw source (button in this UI, top right of this text) of this document and scroll to the bottom.

## Tip 4: Tools

It's recommended you use a dedicated tool for writing Markdown. [Caret][caret] is quite alright, and MacDown on Mac OS is okay too. Good online editors are Stackedit and Dillinger. It's important to have preview mode on during writing, or at least preview once it's written so that you can make sure nothing is broken during the HTML rendering.

[Grammarly](https://www.grammarly.com/) can be a good service for checking your grammar.

## Tip 5: Images

If a post needs images, please make sure they're public domain (usable for any purpose) or that you have express written permission from the author to use them in an article on Bitfalls.com. Images must be placed inside an `images` folder which gets created alongside the language folders of a post, like so:

    - 01-post/
        - en_EN/
          - final.md
        - images/
          - 01.jpg
          
Images should be named numerically and sequentially based on their position in the post, for easier adding into the article during publication. The main image which will serve as the thumbnail and header should be called `header` and end with one of the following: `.jpg`, `.png`, or `.gif`.

## Tip 6: Article Length and Multi-Page Posts

Optimal article length is (with possible exceptions):

- news: 200 - 500 words
- guide: up to 1200 words
- technical guide or programming tutorial: up to 2000 words

Source code doesn't count.

If an article is exhaustive enough to surpass 2000 words, it's possible to split it into 2 parts. The maximum number of parts an article will ever have is 2. If more is needed, the article will be turned into a series in which every part **must** be as standalone as possible - the modern audiences lose interest when they see too many interdependent articles. These individual articles should then reference others, but not depend on them.

## Tip 7: & vs. and

When writing, never use `&` in text. `&` can be used for brand names, but is not a linguistic construct that looks good when reading. Instead of "I went for a drink & a kebab", write "I went for a drink and a kebab".

## Tip 8: Spell out numbers up to 10 

All numbers under 10 should be written out, unless expressing an amount of something that's meant only in a numeric sense, like currency. For example:

- "I ate three whole sandwiches" is better than "I ate 3 whole sandwiches".
- "I bought 2 Eth" is better than "I bought two Eth".

## Tip 9: Linking to Content

Where possible, the author should link to other Bitfalls posts. For example, if an article mentions the blockchain, the author should link to [this post][blockchain]. If an article mentions the bitcoin bubble popping, the author should link to [this post][bubble], etc. It's important to keep the language in mind - link to the language of the post in which you're writing your current post, so English to English, Croatian to Croatian, etc.

When appropriate (not always and not often), mention and link to products from our web shop. We don't want to push it, but keep in mind that successful sales (along with crypto sales and consultation) fund our operation and our author payouts. More sales mean more room to publish posts which means more work for authors.

### External content links

It's a necessity to link to sources when quoting facts. But did you know it's also possible to link to specific parts of a text? Use an extension like [TLDRify](https://chrome.google.com/webstore/detail/tldrify/dbphpdgmhigmaepjklmklmlcoinihjdo/reviews?hl=en) to link to specific text parts and show the reader *exactly* what you meant.

When possible, also link to archived versions of content using a service like [Archive.is](http://archive.is/). This is especially handy when dealing with project promises, potential scams, etc. - content that might be edited after the fact.

## Tip 10: Pronouns

Posts should be objective and neutral whenever possible, except in certain circumstances when we're publishing editorials or columns. Hence, please avoid "I" and focus on either "we" or "you", but stick with one. For example, instead of:

_"In this example, I'll show you how to connect to an external API so that you'll know how to do that in your own projects later."_

Say:

_"In this example we'll hook things up to an external API in order to be able to easily do this in our own projects later on."_

Instead of "he" or "she" use the neutral "they". I.e. "Once the user completes the purchase, we can send the tokens to his account." vs "Once the user completes the purchase, we can send the tokens to their account."

For other useful writing advice, please see [this amazing post][guide].

## Tip 11: Source Code

When writing code, you **must** fence it into triple backticks, as explained [here][codefence]. Don't forget the language hint in the first fence.

        ```solidity
        struct Voter {
                uint weight; // weight is accumulated by delegation
                bool voted;  // if true, that person already voted
                address delegate; // person delegated to
                uint vote;   // index of the voted proposal
            }
        ```
        
## Tip 12: Oxford Comma

When making lists, the use of the Oxford comma is obligatory.

- "A cop and the pope, a rapist and a murderer walk into a bar".

This implies that the pope is a rapist and a murderer, and that the cop escorted him into a bar. It's a fun idea, but it doesn't send the correct message.

- "A cop and the pope, a rapist, and a murderer walk into a bar."

In this set-up, the joke has four people.

That's the difference an Oxford comma can make.

## Tip 13: Be serious

Serious doesn't mean boring, it just means not childish. Rather than write WTF and similar abbreviations, think of an alternative.

- "So Bitcoin Silver is coming out. WTF is that you wonder? We'll tell you."

This sentence would be fine for a publication like Buzzfeed or Boredpanda, but the texts we're trying to expose people to need a more serious note. Induce curiosity in people without making yourself look like a 12 year old.

- "Bitcoin Silver is soon coming out. You may be wondering where it comes from, why, and who's pushing it, and we're here to break it down."

This mildly journalistic tone triggers more curiosity in the average person (our intended audience) than the millennial "wtf" approach. It inspires confidence in a publication, making it seem like more effort was invested into writing (and it was), rather than just hastily cobbled together reposts of news from Reddit (which most modern publications really are).

## Tip 14: The rule of three

When getting ready to submit drafts, you should do the following to proofread them:

1. read the whole post carefully
2. if you encounter any edit point (missing comma, typo, rephrasing needed on a sentence, missing image caption), edit it and start reading from the beginning.
3. `while (number of reads < 3) { goto 1 }`

In other words, until you can read the post 3 times in a row from start to finish **without making a single edit**, do not submit it as a draft because it's not ready yet.

Remember, a lot of people are reading your work. Be your own worst critic.

**Extra tip:** For best results, take a break between full reads. Oftentimes when re-reading something your brain will auto-skip a part because it knows it, and won't read it carefully. See [this](https://cogsci.stackexchange.com/questions/13946/why-does-the-brain-skip-over-repeated-the-words-in-sentences) for such brain tricks.
        
## What NOT to do

- don't use referral links
- don't ask for donations or put your address into articles
- don't advise people to buy a cryptocurrency directly (i.e. "I think you should buy this because it'll rise in value"). We're not an investment advisor, and all the endorsement we can do is the informal type - reviews through posts on the site.

[caret]: https://caret.io
[blockchain]: https://bitfalls.com/2017/08/20/blockchain-explained-blockchain-works/
[bubble]: https://bitfalls.com/2017/09/06/bitcoin-bubble/
[guide]: https://www.impressivewebs.com/how-to-write-great-web-development-articles-tutorials/
[codefence]: https://help.github.com/articles/creating-and-highlighting-code-blocks/
