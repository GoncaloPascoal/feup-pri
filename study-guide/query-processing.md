# Query Processing

## Questions

### ➡️ Describe and distinguish between the two query processing techniques — document-at-a-time and term-at-a-time
In the document-at-a-time technique, the system calculates the score of 
each document with respect to a given query before moving to the next document.
When using term-at-a-time, the system calculates partial document scores
for each term in the query and then aggregates them to obtain the final scores.
The document-at-a-time approach requires less memory, since the system does not
have to keep track of partial scores, but the term-at-a-time approach can be faster
since the system only has to obtain the postings list of each term once.

### ➡️ In what contexts is query transformation / expansion advantageous?
When there is a vocabulary mismatch between the terms in the user's query and
the terms in the collection's documents, due to factors such as spelling errors or
the usage of synonyms, query transformation / expansion can help improve search
results by providing not only exact matches but other similar matches that the
system thinks could also be relevant. Relevance feedback can be used to improve
the results of ambiguous queries: by providing information on which of the returned
documents were relevant, the search results are shifted in the direction of similar
documents. It also tackles the problem that users may have trouble formulating a
query suitable to their information need, but can easily identify if a document
is relevant to it.

### ➡️ What techniques can be used to apply transformations / expansions to user queries?
- Using a dictionary or thesaurus in order to return results that contain synonyms
    of terms in the query
- Suggest related searches using query log mining (other users also searched for...)
- Correcting spelling mistakes (did you mean...), ASCII / case folding
- Query expansion based on relevance feedback (Rocchio Algorithm in vector space
    model: query vector is moved closer to the documents that were considered
    relevant)
- Implicit relevant feedback based on clickstreams (results that are clicked more
    are considered relevant)

### ➡️ Identify and describe query expansion techniques, such as relevance feedback or pseudo-relevance feedback
- **Relevance feedback:** user issues an initial query and gets a set of results
    from the search system, selects the results that they consider relevant, and
    the system attempts to use that feedback to return documents that are more
    closely related to the user's information need (an adjusted set of search results
    is returned).
- **Pseudo-relevance feedback:** to avoid the need for explicit user interaction,
    the system can automatically consider the top k search results as relevant and
    use those to perform query expansion.

