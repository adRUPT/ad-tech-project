# Mic Ad Tech Programming Exercise

Hiya! Thanks for getting here. We hope that the following exercise will not be too painful. We're just trying to get a basic understanding of your skills without the stress of white boarding or live coding challenges. This exercise shouldn't take more than a few hours. We understand you have a life outside of interviewing!

## Conversational Assessment

Our goal here is to learn more about the thought process behind your work. You should write this code like you are part of our team. We are interested in the decisions you made, why you made them, and how you would explain these choices and the architecture so your team can understand it. We will be asking questions like the following:

* What was the first thing you did after reading the exercise?
* Why did you chose this approach?
* Tell us more about this architecture?
* What specific syntax decisions did you make?
* Were there interesting optimizations you discovered?
* What was the most difficult part of this exercise?
* What did you do when you got stuck?
* Did you learn anything new during this project?

Additionally, pretend we work together:

* What does your teammate need to know about it?
* Did you structure it in a way that is understandable to others?
* Is it sufficiently documented?
* Given more time, what would you do next to improve the project that you didn't have time for here?

# FAQ About Exercise

* **Can I use jQuery, React, lodash, or other external libraries?** – Use whatever makes you feel comfortable, but try to consider performance.

* **Who can I send my questions to?** – Stuck on something? Send us an email! Dan (dphillips@mic.com) or Lisa (ellell@mic.com)

# THE EXERCISE: Mid Article Ad Injection using javascript

The team has been tasked with increasing the revenue for each article page view.
We've decided to place ads in the article body, but there are a few specific rules to keep in mind so that we maintain a decent user experience.

1. Place an ad every 400 words (after the paragraph containing the 400th word).
2. Don't place an ad directly before or after an `<img />`, move it up a paragraph if possible.
3. Don't place an ad at the end of an article.
4. If the article has any words contained in the blacklist (case insensitive), don't append any ads.

You'll want to fill out the function `injectMidContentAds` that takes one argument, `article`, which is an object that contains the properties `html` and `blacklist`. The function should return an html string with the appended ads.

For the sake of simplicity, the injected ad element can just be an empty `div` with a class of `ad`


### Simple Example

```js
  const article = {
    html: `
      <article>
        <p>... 210 words ... </p>
        <p>... 430 words ... </p>
        <p>... 650 words ... </p>
        <p>... 802 words ... </p>
      </article>
    `,
    blacklist: [],
  }

  ;
  const result = injectMidContentAds(article);
  console.log(result)

  /*
  <article>
    <p>... 210 words ... </p>
    <p>... 430 words ... </p>

    <div class="ad"></div>

    <p>... 650 words ... </p>
    <p>... 802 words ... </p>
  </article>
  */
```
## Notes about the project
To make things easy, we bootstrapped the project for you. It contains the main file `inject-mid-content-ads.js` which is pretty much the only file you'll need to touch.

To get started run `yarn` in the root directory of this project. (If you don't have yarn you can use npm instead)

There's also a `test.js` spec file that runs a few tests, if those all pass.. that means you got it working correctly! You can run the test by running `yarn test` or `yarn watch` (which will auto run the test file when you save).

In the data folder, you'll find both the `articles.js` and `expected-articles.js`. You should always test against `articles.js` but we provided you the expected result so that you can check what the result should actually look like.