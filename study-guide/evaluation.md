# Evaluation

## Questions

### ➡️ What is precision, recall, interpolated precision?

- **Precision:** no. of relevant retrieved documents / no. of retrieved documents
- **Recall:** no. of relevant retrieved documents / no. of relevant documents
- **Interpolated precision:** in an interpolated precision-recall graph, for a given recall value R, the interpolated precision is the highest precision value found for any recall value >= R

### ➡️ What is precision at k, R-precision?

- **Precision at k**: precision metric which only considers the top k documents retrieved by the search system
- **R-precision**: precision of the top R documents retrieved, where R is the number of relevant documents for a given query

### ➡️ Name the components of a test collection
A test collection is composed of:
- A document collection
- A set of information needs expressed as queries
- A set of relevance judgements (a binary relevant / nonrelevant classification
    for each query-document pair)

### ➡️ Why is a set of relevance judgements considered a "ground truth" for IR?
A set of relevance judgements are a set of binary statements classifying 
documents as either relevant or nonrelevant with respect to a given information
need and therefore can be referred to as the "ground truth" with which search
results can be evaluated.

### ➡️ Draw a precision-recall curve for capturing the evolution of precision in the ranked list of results for a query

### ➡️ What is an average 11-point precision-recall graph for a set of queries?

### ➡️ What is MAP, and how do you calculate it for a set of queries in a test collection?

Mean average precision is the arithmetic mean of the Average Precision scores for
a given set of queries. The average precision score is the mean of all Precision @ k
scores of positions where a relevant document is retrieved by the search system.

## Exercises

**8.1.**
```
P = 8 / 18 = 0.444
R = 8 / 20 = 0.400
```
**8.4.** The interpolated precision at recall level 0 is equal to the maximum precision at any recall level.

**8.8. a)** Since we are only considering one information need, the MAP of each system is equal to the system's Average Precision for that information need. System 1 has a higher MAP.
```
System 1 MAP = (1.00 + 0.67 + 0.33 + 0.40) / 4 = 0.60
System 2 MAP = (0.50 + 0.40 + 0.50 + 0.57) / 4 = 0.49
```
**b)** In order to obtain a good MAP score, the relevant documents that are retrieved by the search system should be ranked as high as possible in the results list.  
**c)** The R-precision score is higher for System 2.
```
System 1 = 4 / 10 = 0.40
System 2 = 4 / 7 = 0.57
```

**8.9. a)** `6 / 20 = 0.3`  
**b)**
```
P = 0.3
R = 6 / 8 = 0.75

F1 = (2 * P * R) / (P + R) = 0.45 / 1.05 = 0.429
```
**c)** At 25% recall, the system has retrieved a total of 2 documents, and all are relevant therefore the precision at 25% recall is 1.  
**d)** The interpolated precision at 33% recall is 0.36.
Recall (%) | P @ Recall
-----------|-----------
12.5       | 1.00
25.0       | 1.00
37.5       | 0.33
50.0       | 0.36
62.5       | 0.33
75.0       | 0.30

**e)** `MAP = (1.0 + 1.0 + 0.33 + 0.36 + 0.33 + 0.30) / 6 = 0.555`  
**f)** The largest possible MAP would occur if the other 2 relevant documents were ranked 21th and 22nd.
```
MAP_max = (1.0 + 1.0 + 0.33 + 0.36 + 0.33 + 0.30 + 7/21 + 8/22) / 8 = 0.503
```
**g)** The smallest possible MAP would occur if the other 2 relevant documents were ranked 9999th and 10000th.
```
MAP_min = (1.0 + 1.0 + 0.33 + 0.36 + 0.33 + 0.30 + 7/9999 + 8/10000) / 8 = 0.416
```
**h)**
```
error = max(abs(MAP_20 - MAP_min), abs(MAP_20 - MAP_max)) = max(0.052, 0.139) = 0.139
```