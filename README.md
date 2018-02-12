[Hacker News](https://news.ycombinator.com) is a community where users can submit articles, and other users can upvote those articles. The articles with the most upvotes make it to the front page, where they're more visible to the community.

Our data set consists of submissions users made to Hacker News from 2006 to 2015. Developer Arnaud Drizard used the Hacker News API to scrape the data, which you can find in one of [his GitHub repositories](https://github.com/arnauddri/hn). We've sampled 3000 rows from the data randomly, and removed all of the extraneous columns. Our data only has four columns:

* `submission_time` - When the article was submitted
* `upvotes` - The number of upvotes the article received
* `url` - The base URL of the article
* `headline` - The article's headline

**Goal:** to train a linear regression algorithm that predicts the number of upvotes a headline would receive. To do this, we'll need to convert each headline to a numerical representation. We'll use the **bag of words** appraoch where:
>a text (such as a sentence or a document) is represented as the bag (multiset) of its words, disregarding grammar and even word order but keeping multiplicity ~Wiki

The first step in creating a bag of words model is tokenization. In tokenization, we break a sentence up into disconnected words.
