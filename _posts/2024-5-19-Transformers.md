# Transformers
## Intro
* GPT: Generative (bots that generate new text) Pre-trained (model learned from a massive amount of data) *Transformers* (specific kind of NN)
* Original transformer developed by Google in 2017 was for text language translation
* GPT2 -> GPT3 significant improvement from mere increase in model size

* Flow: Tokens (chunks of input) -> Each associated with vector (ex: words wtih similar meanings near each other in N-D space) -> attention block -> multilayer perceptron -> repeat between attention and perceptron blocks -> read last vector probability distributions to figure out next token
* GPT-3 weights categorized into 27k matrices which fall into 8 categories
    * Embedding matrix
    * ...
    * Un-embedding matrix - one row for each embedding in the "vocabulary". This is the final step before computing *logits* for next token computation

## Questions
1. How does embedding model get trained?
2. The result is a probability distribution over tokens, is there an entry for each token though?

## Links
* [Visual intro to Transformers](https://www.youtube.com/watch?v=wjZofJX0v4M)