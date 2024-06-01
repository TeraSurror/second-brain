This note is from Data Science from Scratch Chapter


## Central Tendencies

### Mean
Sum of all data points divided by the count.

```python
def mean(x):
	return sum(x) / len(x)
```

### Median
The middle most value or the average of the middle most values.

```python
def median(x):
	n = len(x)
	sorted_v = sorted(x)
	midpoint = n // 2
	if n % 2 == 0:
		return sorted_v[midpoint]
	else:
		lo = midpoint - 1
		hi = midpoint 
		return (sorted_v[lo] + sorted_v[hi]) / 2
```



### Quantile
- Generalization of median
- Represents the value less than which a certain percentile of the data lies
- Median - Value below which 50% of the data lies

```python
# pth percentile
def quantile(x, p):
	p_index = int(p * len(x))
	return sorted(x)[p_index]

# Examples
quantile(some_list, 0.10) # 10th percentile
quantile(some_list, 0.70) # 70th percentile
quantile(some_list, 0.90) # 90th percentile
```

### Mode
Element that occurs the most number of times

```python
def mode(x):
	counts = Counter(x)
	max_count = max(counts_values())
	return [x_i for x_i, count in counts.iteritems() if count == max_count]
```


## Dispersion
- Refers to how spread out the data is
- 0 means not spread out at all and higher value means a lot more spread

### Range

```python
def data_range(x):
	return max(x) - min(x)
```

### Variance and Standard Deviation
Represents spread from mean

```python
def sum_of_squares(x):
	return sum([x_i * x_i] for x_i in x)

def de_mean(x):
	x_bar = mean(x)
	return [x_i - x_bar for x_i in x]

def variance(x):
	n = len(x)
	deviations = de_mean()
	return sum_of squares(deviations) / (n - 1)

def standard_deviation(x):
	return math.sqrt(variance(x))
```

### Interquartile Range
- Range and Std have the problem of outliers
- This is more robust
- Defined as the difference between the 75th and the 25th percentile value

```python
def interquartile_range(x):
	return quantile(x, 0.75) - quantile(x, 0.25)
```


## Correlation
### Covariance
- Paired version of variance
- measures how two variables vary in tandem from their means
- positive covariance means when x increases,  y increases
- negative covariance means when x increases, y decreases

```python
def covariance(x, y):
	n = len(x)
	return dot(de_mean(x), de_mean(y)) / (n - 1)
```

### Correlation
- It is unit-less and always lies between -1 and 1.
- It is affected by outliers

```python
def correlation(x, y):
	stdev_x = standard_deviation(x)
	stdev_y = standard_deviation(y)
	if stdev_x > 0 and stdev_y > 0:
		return covariance(x, y) / stdev_x / stddev_y
	else:
		return 0
```


