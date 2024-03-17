
Just like in logistic regression, we create a freq count table for each unique word wrt the class

| Vocabulary | Pos Freq | Neg Freq | Pos Prob | Neg Prob | L pos prob | L neg prob |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| I | 3 | 3 | 0.24 | 0.25 | 0.19 | 0.20 |
| am | 3 | 3 | 0.24 | 0.25 | 0.19 | 0.20 |
| happy | 2 | 1 | 0.15 | 0.08 | 0.14 | 0.10 |
| because | 1 | 0 | 0.08 | 0 | 0.10 | 0.05 |
| learning | 1 | 1 | 0.08 | 0.08 | 0.10 | 0.10 |
| NLP | 1 | 1 | 0.08 | 0.08 | 0.10 | 0.10 |
| sad | 1 | 2 | 0.08 | 0.17 | 0.10 | 0.15 |
| not | 1 | 2 | 0.08 | 0.17 | 0.10 | 0.15 |
| **Total** | 13 | 13 |  |  | 1 | 1 |
|  |  |  |  |  |  |  |

To find sentiment for "I am happy today; I am learning."

multiply over 1 to m -> ( P(word | positive) / P(word | negative) )

I = 0.2 / 0.2, am = 0.2 / 0.2, happy = 0.15 / 0.10 and so on...
we multiply all the probabilities for the words in the sentence and multiply them.
If the result is greater than 1, we say the sentiment is positive

#### Laplacian Smoothing
we use additional terms in the prob definition to make sure it doesn't end up being 0
P (wi | class) = freq(wi, class) + 1 / Nclass + V
V: no of unique words in the vocabulary


