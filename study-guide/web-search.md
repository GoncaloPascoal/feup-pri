# Web Search

## Questions

### ➡️ What are informational, transactional, and navigational information needs?
- **Informational:** user wishes to obtain more information about a given topic,
    by viewing several different sources
- **Navigational:** user wants to locate a specific website or page
- **Transactional:** user wants to perform a transaction, such as purchasing a 
    product or downloading a file

### ➡️ Name some differences between web search and enterprise search
- The web is of a much larger scale compared to most enterprise search systems
- Documents on the web vary wildly in terms of language, format, quality, accuracy
- In web search, we have to deal with search manipulation, spam, misleading documents
- Web search users are of a wide variety of backgrounds: queries normally focused 
    on full text search rather than a more technical syntax

### ➡️ How do you index images?
Alternate text (or `alt`, which is essentially a description for the image being
displayed to improve accessibiliy), as well as file names could be used to index
images.

### ➡️ Give examples of ranking signals used by search engines
- Time of day
- Search location
- Link analysis signals such as PageRank or HITS
- Previous searches
- Number of clicks

### ➡️ What are the SCC, IN and OUT components in the view of the web as a bowtie?
- **SCC:** Strongly Connected Component, the pages in this component form a connected
    graph, meaning that within the SCC we can reach any page from any other page
- **IN:** Pages that link to pages in the SCC. Generally contains newer pages that
    haven't been referenced much yet.
- **OUT:** Pages that are linked to by pages in the SCC, but don't link back to
    the SCC. Generally contains older pages, pages that are no longer updated...