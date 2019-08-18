---
title: Word embeddings
---

* distributional hypothesis + distributional semantics
* SVD-based word embeddings
* word2vec and GloVe
* connection with SVD-PPMI

What are word embeddings?

In the literal sense, they are an *embedding* of *words* into some kind of space, typically Euclidean space. What exactly does this mean? We have some initial space of words - a collection of words, and some additional mathematical structure upon them - and we find a representation of them as a subset of some more palatable space that is easier to handle, perhaps a vector representation, that (approximately) preserves that structure.

So what is this structure? If we take the view that word embedding should capture some inherent notion of similarity or distance between words, this naturally suggests that we would like to embed between metric spaces. Then for our embeddings to fully capture the semantics of words, said semantic content of a word should be fully characterized by its relationship to other words in the original space.