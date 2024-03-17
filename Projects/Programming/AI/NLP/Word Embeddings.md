 Examples of words representations:
 1. Integers: every word corresponds to an 
 2. One hot encoding
 3. Word Embeddings: every word is represented as a vector of numbers


#### Word Embedding methods
##### Classical Methods
- word2vec (Google, 2013)
- **_Continuous bag-of-words (CBOW)_:** the model learns to predict the center word given some context words.
- **_Continuous skip-gram / Skip-gram with negative sampling (SGNS)_:** the model learns to predict the words surrounding a given input word.
- **_Global Vectors (GloVe) (Stanford, 2014)_:** factorizes the logarithm of the corpus's word co-occurrence matrix, similar to the count matrix you’ve used before.
- **_fastText (Facebook, 2016)_:** based on the skip-gram model and takes into account the structure of words by representing words as an n-gram of characters. It supports out-of-vocabulary (OOV) words.

##### Deep learning, contextual embeddings
 In these more advanced models, words have different embeddings depending on their context. You can download pre-trained embeddings for the following models.
- BERT (Google, 2018)
- ELMo (Allen Institute for AI, 2018) 
- GPT-2 (OpenAI, 2018)


### Continuous Bag of Word Model:

We try to predict the center word, given the surrounding words

##### Cleaning and Tokenization
1. convert to lowercase
2. punctuation
3. keep or remove numbers as required
4. special characters - we can usually drop them
5. special word - depends on the problem. we can remove or treat them as a word

##### Transforming words into vectors
To transform the context vectors into one single vector, you can use the following.
![[cbow2.png]]
As you can see, we started with one-hot vectors for the context words and and we transform them into a single vector by taking an average. As a result you end up having the following vectors that you can use for your training.
![[cbow1.png]]

#### Architecture of CBOW:

- Input layer (size V) -> Hidden Layer (size of embedding)  -> Output Layer (size V)
- It is a shallow neural network
![[cbow3.png]]