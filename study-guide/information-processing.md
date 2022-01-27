# Information Processing

## Questions

### Distinguish Between data, netadata and information
Data refers to an observation or measurement on a certain scale (for example, 10ºC or 54.2m). Metadata is data about data, such as when or by whom that data was gathered, or which format is being used for representation. Information is data that is interpeted within a specific context (for example, the temperature in Porto yesterday at noon was 11ºC).

### Identify and describe the phases of a typical information lifecycle
The information lifecycle is split into the following phases:
- Occurrence: information is generated or discovered
- Trasmission: information is shared / retrieved / accessed
- Processing / Management: information is refined / validated / filtered / indexed / stored
- Usage: information is explored and used to guide decision-making or as the basis of a system or systems

### Describe typical data processing patterns, pipelines and frameworks, e.g. ETL, EtLT, OSEMN
- ETL, or Extract Transform Load, is a data processing pattern where data is obtained from storage, transformed into a suitable format and subsequently loaded into the desired application.
- For systems that can handle large amounts of data, a new pattern emerged: ELT, where the data is first loaded and then transformation is performed by experts in the domain. This pattern allows for a greater separation of responsibilities. EtLT refers to a variation of ELT where some data transformation is performed before the loading phase.
- OSEMN presents a series of data processing steps (Obtain, Scrub, Explore, Model, Interpret), but for many projects these steps aren't always followed in a linear fashion.

### Describe the challenges associated with data processing
Data processing tackles a variety of challenges, such as:
- Data is available in several different formats, some more structured and well-defined than others
- Data often contains missing or duplicate values, deciding how these should be handled is an important step that frequently demands specific domain knowledge
- Data can contain outliers, which can either be useful data points in some domains or observations that distort statistics and hinder data analysis
- Normalization, discretization and the synthesis of new attributes are often used to increase the usefulness of data
- Data can be of poor quality or outdated and have unsuitable dimensions, requiring filtering or sampling procedures

### Identify the challenges and techniques related to: data cleaning, data preparation, and data presentation
- Data cleaning: missing values, duplicate values, inconsistent or invalid values, outdated values, outliers
- Data preparation: normalization, discretization, synthesis of new data, format conversion
- Data presentation: adjusting how data is presented depending on the target audience (more or less technical), investigating data quality and properties, justifying the existence of certain properties or relationships; many types of visualizations (bar charts, box plots, line plots, scatter plots, histograms)

### Describe the importance of data pipelines and how Makefiles can be used to implement them
Data processing and exploration can sometimes be *ad hoc* procedures where separate 
executions can vary, leading to inconsistencies. These problems can be prevented 
by designing and maintaining a well-documented, versionable and reproducible data
processing pipeline, similarly to how the development of other types of software is
handled.

The Make build tool lets us define targets and rules that should be followed in order
to generate them. Targets can depend on the existence of other files, forming a dependency
graph. In the context of a data processing pipeline, we could have targets for downloading
an HTML file off the web, extracting segments using BeautifulSoup or converting 
between different data formats.