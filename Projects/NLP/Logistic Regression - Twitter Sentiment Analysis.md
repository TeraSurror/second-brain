### Supervised ML (training)
- train predictions with labels
- there is "ground truth"

## Representing Text as a vector
### Vocabulary
- All the unique words in your data set. Assume size to be V
- every sentence will be converted to a vector of size V, where each element will be 1 if it appears in the sentence.
- Eg. I am Harsh will be -> [1,1,1,0,0,0,0,0] if the vocabulary is [I, am, Harsh, Mike, Cash, One, Two, Three]
- Problems: Large training time and large prediction time.

### Positive and Negative Frequencies
We create a table the contains the vocabulary and the freq of each words in each classes.
For Eg.

| Vocabulary | Pos Freq | Neg Freq |
| ---- | ---- | ---- |
| I | 3 | 3 |
| am | 3 | 3 |
| happy | 2 | 0 |
| because | 1 | 0 |
| learning | 1 | 1 |
| NLP | 1 | 1 |
| sad | 0 | 2 |
| not | 0 | 1 |
### Feature Extraction
We encode each tweet as a vector in the following way - 

X =[1, sum of all freq in positive class, sum of all freq in negative class]

Eg:
I am sad, I am not learning NLP -> [1, 3 + 3 + 1 + 1 + 0 + 0, 3 + 3 + 1 + 1 + 2 + 1] -> [1, 8, 11]
This helps in reducing the number of parameters we have to train


### Preprocessing
#### Stop Words
- words that do not have significant meaning in the sentence.
- conjunctions
- punctuation marks

#### Stemming and lowercasing
- tuning GREAT AI model -> tun great ai model
- Stemming - Converting every word to its stem. Tuning is converted to tun



### Algo for logistic regression

Repeat {
	theta = theta - alpha * (derivative of cost function)
}



