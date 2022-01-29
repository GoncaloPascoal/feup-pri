# Entity-Oriented Search

## Questions

### ➡️ What is entity-oriented search? What is necessary to implement it?
In entity oriented search, the retrieval units are named entities, such as people,
organizations, places or media, instead of the documents typical in most
information retrieval systems. Implementing entity-oriented search requires
having a knowledge base, which is a large, structured repository of information
regarding entities and the relationships between them.

### ➡️ Describe the challenges and techniques associated with: building entity descriptions, entity ranking, entity linking
- **Building entity descriptions:** when our main goal is to select entities that
    match an *ad hoc*, textual query, we can approach the problem similarly to
    document retrieval by constructing documents that aggregate all existing
    information about entities and applying the indexing and ranking techniques
    used in document retrieval. There are several techniques for constructing entity
    descriptions depending on the type of data:
    - **Unstructured data:** manually annotate mentions to specific entities or
    use automated entity linking.
    - **Semi-structured data:** identify specific segments of the document using the
    markup structure (HTML scraping / parsing) which then map to fields in the
    entity descritpion; include a catch-all field which concatenates the content
    of all other fields.
    - **Structured data:** consider the immediate vicinity of a node (statements
    where it appears as subject or object); for knowledge bases with a large number
    of attributes, collapse attributes or relationships of the same type into a 
    single field or consider only the most important predicates.
- **Entity ranking:** process of ranking entities that match a particular query;
    we can build entity descriptions, consider these as documents and use
    retrieval models for document ranking such as vector space, probabilistic and
    language models.
- **Entity linking:** process of identifying mentions to specific entities in 
    text and linking it to entities stored in a knowledge base. NLP can be used
    to automatically detect entity mentions. An entity linking system tackles
    three main challenges: mention detection (detecting potential entity mentions),
    candidate selection (selecting potential entities the mention could be referring to)
    and disambiguation (using context information to choose the correct entity).
    A possible approach is to build a dictionary containing entity surface forms
    (name variants), checking all the document's n-grams against this dictionary
    and filtering out undesired entities.

### ➡️ Describe the data sources typically required for entity oriented search and their characteristics
Knowledge bases store assertions about entities, commonly in the form of RDF
(Resource Description Framework) statements. URIs (Uniform Resource Identifier),
are used to uniquely identify entities (or resources in RDF). An RDF statement is
a triple, composed of a subject (a URI identifying a resource), a predicate (a
URI referring to the relationship or property that statement is conveying) and
an object (either a URI referring to another resource or a literal value). This 
way of storing information about entities showcases the strong ties between
Entity-Oriented Search and the Property Graph Model and Triplestore Databases.
