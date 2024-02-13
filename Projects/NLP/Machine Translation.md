To translate from English to French we do the following:
1. Find words embeddings in English and French
2. Find embedding for a word in English and corresponding French word
3. Find a way to transform the English word embedding to French embedding

#### Transformation

Let X be English embedding and Y be French Embedding

we need to find an R such that,

X **.** R = Y (approx)
##### Loss function (L) = || XR - Y ||<sub>F</sub> (Frobenius norm)
Steps to find R:
1. initialize R
2. loop till epochs
	1. find L
	2. find gradient of Loss
	3. update => R = R - alpha * g

We take square, cuz derivative is easy
#### Frobenius norm
For any given matrix we find it by taking all squaring all elements, adding them up and finally taking the square root of the sum.



