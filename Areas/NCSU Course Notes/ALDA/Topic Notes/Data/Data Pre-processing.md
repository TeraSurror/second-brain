## Aggregation:
1. Combine 2 or more attributes or objects into a single attribute/object
2. Quantitative values -> take average or sum
3. Qualitative values -> ignored or taken as a set

## **Sampling**:
Used when obtaining the entire set of data is too expensive.
Used when processing the entire set of data is too expensive.

Key points when sampling:
1. sample should work as well as the original data
2. sample should have same properties as the original data.

Types:
1. **Randomized sampling**
	Take random values from the group to form the sample.
	Types are the following
	1. Sampling with replacement
	2. Sampling without replacement
	If sample size is small, the two methods are almost the same.
	Not a good technique when the data has a lot for different properties
2. **Stratified Sampling**
	Take some values from each group to form a sample
	Types:
	1. Same number from each group
	2. Proportional number from each group
	
**Progressive Sampling:**
- Start from a small sample size
- Increase size until you get a sample that can be analysed properly (or till the size is sufficient)
- Reduces the need to find the sample size
- Requires a way to find if the sample size is enough


## Attribute Transformation

Involves a function that maps a value to a new value such that each new value can be mapped to the old value.

Eg -> log functions, exponent, x pow k, mod(x) and so on

Techniques used are:
1. Normalization
2. Standardization


## Feature subset selection

Techniques (remember by bef - w : beef wellingtion)
1. **Brute force:** try out all the combinations of features and select the one that gives the best results for the minimum amount of features
2. **Embedded approach:** Feature selection is part of the data mining algorithm
3. **Filter approach**: feature are selected before the data mining algorithm is run
4. **Wrapper approach:** Data mining is used as the algorithm to decide the features to be used.






