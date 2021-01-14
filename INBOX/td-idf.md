---
aliases:
tags:
---
Link:

# td-idf
**TF**\-**IDF** is a statistical measure that evaluates how relevant a word is to a document in a collection of documents. This is done by multiplying two metrics: how many times a word appears in a document, and the inverse document frequency of the word across a set of documents.

When it comes identifying words or phrases that are unique to a text, a measure like tf-idf does a good job. But because of the way tf-idf is calculated, it cannot distinguish between words that are used in all texts.

 The “idf” in tf-idf stands for “inverse document frequency”. When a word is in all the texts, tf-idf is zero for all of them.
