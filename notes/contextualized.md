---
title: Contextualized word embeddings
---

Regular [word embeddings](/notes/embeddings.html) operate on the assumption that there's a single representation that captures the meaning of a word. But this is a pretty big assumption!

Consider the following two sentences: "It was nice out this morning when I ran to the park" and "Yesterday afternoon I ran some more significance tests". Clearly 'ran' means something different in these two contexts - but the structure of static word embeddings doesn't give us the ability to distinguish between the two.

Rather than assigning a single vector to each word intended to represent the entirety of its usage, contextualized embeddings assign a vector to each *instance* of a word. Specifically, contextualized embedding models take the *context* that a word occurs in (usually a sentence - or two), and output a representation for each word that depends on the entire context.

So how do they do this?

Sure, bigger and heftier models keep coming out, but for brevity's sake we'll restrict ourselves to the Sesame Street family here: ELMo[^1] and BERT[^2].

In essence, ELMo uses parallel forward and backward LSTM components to process context, whereas BERT uses stacked Transformer[^3] layers.

* what are contextualized embeddings?
* ELMo overview
* BERT overview
* ELMo and BERT architectures
* analysis

[^1]: [Deep contextualized word representations](https://aclweb.org/anthology/papers/N/N18/N18-1202). Matthew Peters, Mark Neumann, Mohit Iyyer, Matt Gardner, Christopher Clark, Kenton Lee and Luke Zettlemoyer. NAACL 2018.
[^2]: [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://www.aclweb.org/anthology/N19-1423). Jacob Devlin, Ming-Wei Chang, Kenton Lee and Kristina Toutanova. NAACL 2019.
[^3]: [Attention is All You Need](https://papers.nips.cc/paper/7181-attention-is-all-you-need.pdf). Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan Gomez, Lukasz Kaiser and Illia Polosukhin. NeurIPS 2017.