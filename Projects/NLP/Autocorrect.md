
Algorithm:
1. Identify a misspelled word
2. Find strings n edit distance away
3. Filter candidates
4. calculate word probabilities

##### Identify misspelled word
Just check if the word is in the vocabulary or not

##### Find strings n edit distance away
we use the following edits:
2. add letter
3. delete letter
4. switch letters
5. replace letter
n is usually 2-3

##### Filter candidates
Out of all the words filter the words that are actually in the vocabulary

##### Calculate word probabilities
1. Find the freq of all the words in the corpus
2. Probability is count of word divided by the total number of words in the corpus
3. Select the word with the highest probability.
4. This word is the auto-correct result.


#### Min edit distance
This is the same as the leetcode problem.