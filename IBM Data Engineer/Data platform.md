[[Data Ecosystem]]

**The architecture of a data platform** can be seen as a set of layers, or functional components, each one performing a set of specific tasks. These layers include:

- **Data Ingestion or Data Collection Layer**, responsible for bringing data from source systems into the data platform. 
	 [[Data Collection]]
- **Data Storage and Integration Layer**, responsible for storing and merging extracted data.(Depend on how you extract and process data, you need to choose suitable Data Storage and suitable solution )
    [[Data Repositories, Data Pipelines, and Data Integration Platforms]] 
    [[Data Wrangling]]
- **Data Processing Layer**, responsible for validating, transforming, and applying business rules to data.
    [[Data Wrangling]]
- **Analysis and User Interface Layer**, responsible for delivering processed data to data consumers.
	[[Querying Data, Performance Tuning, and Troubleshooting]]
- **Data Pipeline Layer**, responsible for implementing and maintaining a continuously flowing data pipeline. 
![[DataPlatformIllustration.png]]

A well-designed data repository is essential for building a system that is scalable and capable of performing during high workloads. The choice or design of a data store is influenced by the type and volume of data that needs to be stored, the intended use of data, and storage considerations. The privacy, security, and governance needs of your organization also influence this choice.
The **CIA, or Confidentiality, Integrity, and Availability** triad are three key components of an effective strategy for information security. The CIA triad is applicable to all facets of security, be it infrastructure, network, application, or data security.

