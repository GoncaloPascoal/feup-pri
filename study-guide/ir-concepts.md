# IR Concepts

## Questions

### ➡️ What is a document, collection, term, bag of words?
- **Document:** data that is organized into a self-contained, usually unstructured
    or semi-structured instance; units that are returned by an IR system in 
    response to a query
- **Collection:** the set of documents used by an IR system
- **Term:** indexed units that form a document (usually words)
- **Bag of words:** representation of a document as a set of words, disregarding
    their frequency or relative position

### ➡️ Define stemming
Stemming is the reduction of inflected words to root forms, usually through
heuristic methods specific to each language.

### ➡️ What is an inverted index, a vocabulary, a postings list?
- **Inverted index:** mapping of terms to the documents where those terms occur;
    additional information such as frequency or positions can also be stored.
- **Vocabulary:** list of terms present in the documents in the collection
- **Postings list:** list of documents where a term appears (can contain information
    about the position of term occurrences inside each document)

### ➡️ What is an information need, a query, a results list?
- **Information need:** a topic that a user of the IR system wishes to know more
    about / a question they need the answer to
- **Query:** translation of the information need to the syntax of the IR system
- **Results list:** ranked list of documents in the collection which match a 
    particular query

### ➡️ What is a relevant result in a results list?
A relevant result is a result that answers or contributes to answering the 
information need that corresponds to a certain query, not necessarily a 
result which contains all the terms of the query.