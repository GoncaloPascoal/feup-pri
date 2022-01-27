# Vector Model

## Questions

### ➡️ What is term frequency, collection frequency, document frequency, inverse document frequency?
- **Term frequency:** number of times a term occurs in a particular document
- **Collection frequency:** number of times a term occurs across the entire collection
- **Document frequency:** how many documents contain a particular term
- **Inverse document frequency:** commonly used in conjunction with term 
    frequency to form tf-idf, idf is given by the formula `log(N / df)`, 
    meaning that the inverse document frequency of a term is higher when that 
    term appears in a lower portion of the documents in the collection.

### ➡️ How to calculate tf-idf weights?
For a given term `t` and a document `d`, the corresponding tf-idf weight is given by:
```
tf(t, d) * log(N / df(t))
```

### ➡️ How do you rank documents in the vector model?
In the vector model, documents and queries are represented as vectors in an n-dimensional
space, and documents are ranked using cosine similarity (the score of each document
is equal to the cosine of the angle between that document's vector and the query
vector, so smaller angles will correspond to a higher score).

## Exercises

**6.9.** A term that occurs in every document will have an idf of `log(1) = 0`. If documents are ranked based on tf-idf, the term will have no impact on the score of the documents (similarly to how stop words can be ignored in an IR system).

**6.10.**
```
tf-idf(car, Doc1) = tf(car, Doc1) * idf(car)
    = 27 * 1.65 = 44.55
tf-idf(car, Doc2) = tf(car, Doc2) * idf(car)
    = 4 * 1.65 = 6.6
tf-idf(car, Doc3) = tf(car, Doc3) * idf(car)
    = 24 * 1.65 = 39.6

tf-idf(auto, Doc1) = tf(auto, Doc1) * idf(auto)
    = 3 * 2.08 = 6.24
tf-idf(auto, Doc2) = tf(auto, Doc2) * idf(auto)
    = 33 * 2.08 = 68.64
tf-idf(auto, Doc3) = tf(auto, Doc3) * idf(auto)
    = 0 * 2.08 = 0

tf-idf(insurance, Doc1) = tf(insurance, Doc1) * idf(insurance)
    = 0 * 1.62 = 0
tf-idf(insurance, Doc2) = tf(insurance, Doc2) * idf(insurance)
    = 33 * 1.62 = 53.46
tf-idf(insurance, Doc3) = tf(insurance, Doc3) * idf(insurance)
    = 29 * 1.62 = 46.98

tf-idf(best, Doc1) = tf(best, Doc1) * idf(best)
    = 14 * 1.5 = 21
tf-idf(best, Doc2) = tf(best, Doc2) * idf(best)
    = 0 * 1.5 = 0
tf-idf(best, Doc3) = tf(best, Doc3) * idf(best)
    = 17 * 1.5 = 25.5
```

**6.11.** Yes, see exercise 6.10 for examples

❓ **6.15.**

Document 1
```
length = sqrt(44.55^2 + 6.24^2 + 21^2) = 49.65
v = (0.897, 0.126, 0, 0.423)
```
Document 2
```
length = sqrt(6.6^2 + 68.64^2 + 53.46^2) = 87.25
v = (0.076, 0.787, 0.613, 0)
```
Document 3
```
length = sqrt(39.6^2 + 46.98^2 + 25.5^2) = 66.52
v = (0.595, 0, 0.706, 0.383)
```

**6.16.** The vectors calculated in exercise 6.15 are normalized (they have length 1), therefore the sum of the squares of their components is 1 (withing rounding error).
```
Doc1: 0.897^2 + 0.126^2 + 0.423^2 = 0.999414
Doc2: 0.076^2 + 0.787^2 + 0.613^2 = 1.000914
Doc3: 0.595^2 + 0.706^2 + 0.383^2 = 0.99915
```

**6.17.1.**

**6.17.2.**