### N-Grams
**It is a sequence of N-words**

Corpus: I am happy because I am learning
Uni-grams: {I, am, happy, because, learning}
Bi-grams: {I am, am happy, happy because, because I, am learning}
Tri-grams: {I am happy, am happy because, ...}

Note: all words have to be consecutive in the corpus.

#### **Sequence notation:**
Corpus: This is great ... teacher drinks tea          m=500 (size of corpus)
This: w<sub>1</sub>  is: w<sub>2</sub> great: w<sub>3</sub>      teacher: w<sub>498</sub> ...
w<sub>1</sub><sup>m</sup> = w<sub>1</sub> w<sub>2</sub> ... w<sub>m</sub>
The above notation means words from 1 to m

#### **Probability of N-gram**

P(w<sub>N</sub> | w<sub>1</sub><sup>N-1</sup>) = C (w<sub>1</sub><sup>N-1</sup>  w<sub>N</sub>) / C(w<sub>1</sub><sup>N-1</sup>) 
C (w<sub>1</sub><sup>N-1</sup>  w<sub>N</sub>)  = C(w<sub>1</sub><sup>N</sup>)

#### Sequence Probability
Conditional Probability: P(A, B, C, D) = P(A) * P(B | A) * P(C | A, B) * P(D | A, B, C)

So the probability of the statement: "The teacher drinks tea" will be
P(the teacher drinks tea) = P(the) P(teacher | the) P(drinks | the teacher) P(tea | the teacher drinks)
An issue here is that the probability of the teacher drinks will be close to 0 and it will drive the entire probability down. So we make an assumption that only the last words will matter.

So: P(w<sub>1</sub><sup>n</sup>) approx= P(w<sub>1</sub>) P(w<sub>2</sub> | w<sub>1</sub>) ... P(w<sub>n</sub> | w<sub>n - 1</sub>) -> For Bigram

#### N-Gram Language model

1. Count Matrix
		Rows: unique N-1 grams
		 Columns: unique corpus words

2. Probability Matrix
		Divide each cell in count matrix by its row sum

3. Language Model
		Find sentence probability from the prob matrix
		P(<'s'>I learn</s'>) = P(learn | <'s'>) P(learn | I) P(</'s'> | learn)

