- Represent words as vectors
- Represents relations between the words

#### Word by Word
- Number of times words occur together within a certain distance k
Eg:
I like simple data
I prefer simple raw data
k = 2

|  | simple | raw | like  | I |
| ---- | ---- | ---- | ---- | ---- |
| data | 2 | 1 | 1 | 0 |


#### Word by Document
- number of times a word occurs within a certain category

|  | Entertainment | Economy | Machine Learning |
| ---- | ---- | ---- | ---- |
| data | 500 | 6620 | 9320 |
| film | 7000 | 4000 | 1000 |
