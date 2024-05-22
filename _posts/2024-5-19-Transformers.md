## Intro
* GPT: Generative (bots that generate new text) Pre-trained (model learned from a massive amount of data) *Transformers* (specific kind of NN)
* Original transformer developed by Google in 2017 was for text language translation
* GPT2 -> GPT3 significant improvement from mere increase in model size

* Flow: Tokens (chunks of input) -> Each associated with vector (ex: words wtih similar meanings near each other in N-D space) -> attention block -> multilayer perceptron -> repeat between attention and perceptron blocks -> read last vector probability distributions to figure out next token
* GPT-3 weights categorized into 27k matrices which fall into 8 categories
    * Embedding matrix
    * ... [See next section underlined elements]
    * Un-embedding matrix - one row for each embedding in the "vocabulary". This is the final step before computing *logits* for next token computation

## Attention
* Attention weights make up for 1/3 of the weights: Query, Key, Value, Output matrices
* The goal of attention block layers is to multiply the embedding vectors by weights to enhance them with more meaning on how the token contributes to the entire input.
    * Ex: Tower (vector X), prefixed by Eiffel (x moves to area correlating to France, Eiffel Tower, etc.). Attention blocks move information encodied in one embedding to that of another
* <u>Query</u> vector - so that model is prepared to answer questions (example W_q matrix is weights that represent "What adjectives precede position 4?")
* <u>Key</u> matrix - answering the queries
* Dot product between dot(K,Q) shows how well each key matches each query. Values range from infinity to negative infinity
* Compute softmax across each of the columns of K x Q matrix to normalize -> we've now assigned weights to how relevant the word on the left is to the corresponding value on the top

Attention Pattern:
![AttentionPattern]({{ site.baseurl }}/images/attention.jpg)

Attention(Q, K, V) = softmax(QK^T / []) * V

* **Masking:** We train with weights trying to predict the next token for each input token, so we don't want later tokens to influence earlier ones. In the matrix, this intuitively should look like zero-ing out half of the matrix.

![AttentionPattern]({{ site.baseurl }}/images/attention2.png)

* Attention matrix size is context size squared
* <u>Value</u> matrix W_v: W_v * embedding vector of word x represents what should be added to some other embedding vector y to reflect x
* Multiply weighted matrix across all embeddings, take weighted sum to find sequence of changes, add all of those changes to generate refined embeddings (i.e. E + deltaE = E')
* One set of these sequences is called an *attention head* (i.e. one attention block)

* **Cross attention:** Up until now we discussed self-attention. Cross attention invovles two distinct types of data (one language, or text to speech)

![AttentionPattern]({{ site.baseurl }}/images/attention3.png)
* <u>Output matrix:</u> We want # value parmas = # key params + # value params not gigantic emebdding vectors matrix. Value down matrix (maps embedding space to key query space). Value up matrix (maps back to embedding space). Output matrix is written as all value up matrices associated with entire multi-headed attention block. The value matrix for a given attention head is usually just the value down matrix.

## Perceptron Layer
* <u>Up-projection</u>
* <u>Down-projection</u>

## Questions
1. How do multi-lingual models work? How large do these models get, given the number of tokens in the output distribution is much larger?
2. How does embedding model get trained? Word2Vec is a popular one.
3. Understand attention heads and cross attention
4. How are key, query, value weights computed


## Links
* [Visual intro to Transformers - Chapter 5](https://www.youtube.com/watch?v=wjZofJX0v4M)
* [LLM Visualizer](https://bbycroft.net/llm)
* [Attention - Chapter 6](https://www.youtube.com/watch?v=eMlx5fFNoYc)
