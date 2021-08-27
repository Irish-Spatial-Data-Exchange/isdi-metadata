[ISDE Metadata - Home](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/README.md) | [Guides](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/guides/README.md) | Lineage Statements

# Lineage

This document outlines recommended best practices for writing a lineage statement for ISDE.

- _Author_ [Adam Leadbetter](https://github.com/adamml)
- _Last edited_ 27th August 2021
- _Created_ 26th August 2021

## Table of Contents

1. [Definitions](#definitions)
1. [General Recommendations](#general-recommendations)
1. [Specific Recommendations](#specific-recommendations)
1. [Examples](#examples)
1. [Including a Lineage Statement in Metadata Records](#including-an-abstract-in-metadata-records)
    1. ISO19115/19139
    1. DCAT
    1. Schema.org
1. [References](#references)

## Definitions

Gartner's 2021 Planning Guide for Data Management notes that data lineage describes the journey of the data from its source  to its current state. As the Data Management Association (DAMA) note in their Data Management Body of Knowledge, it is critical to track the flow of data across systems and individuals in order to maintain a 'chain of custody.' Detailed lineage can also include the rules by which the data are changed and the frequency of changes. Data lineage can also aid downstream data integration and interoperability.

Taking these statements into account, a lineage statement in ISDI metadata should provide enough information to end users of the dataset to understand the source(s) of the data have been processed to create the dataset in question.

## General Recommendation
 
- The [abstract](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/guides/ABSTRACTS.md) may contain generalised descriptions of lineage and is generally targetted at a wider audience. The lineage statement can be used for more specific or technical information and is targetted at a more specialist audience.
- The lineage statement is not regarded as a piece of _discovery_ metadata, but is an important piece of _usage_ metadata.
- The lineage statement is best written by, or in conjunction with, data stewards rather than relying on data managers to write it as it should be generated as close to the data source as possible. This recommendation reflects that of Gartner's 2021 Planning Guide for Data Management which encourages the formalisation of data lineage processes as part of data governance progrmames.

## Specific Recommendations

- A lineage statement must reference any and all datasets used to synthesise the dataset in question. Where possible the following information regarding the source dataset(s) should also be included in the lineage statement.
    - Accuracy of the source dataset
	- Spatial scale of the source dataset
- If links to other websites are used to describe the lineage of a dataset, these must be frequently checked in order to ensure the links remain active and valid.
- If more expressive lineage statements with detailed processing steps are required, a model such as the World Wide Web Consortium's (W3C) Provenance Data Model (PROV) should be considered to allow the information to be disseminated in a structured manner.

## Examples



## Including a Lineage Statement in Metadata Records

### ISO19115/19139

ISO19115/1939 have a gmd:LI_Lineage type which allows for a lineage statement, but also for the formal encoding of process steps (gmd:processStep) and sources (gmd:source).

### DCAT

Using the W3C's PROV ontology, the DCAT vocabulary entails the dcat:Dataset class to be a prov:Entity, allowing the use of the prov:wasGeneratedBy property to connect the metadata describing a dataset with its provenance chain.

### Schema.org



## References

Data Management Association (2017). _Data Management Body of Knowledge (2nd Edition)_ Technical Publications, Basking Ridge, New Jersey. 

Groth, Paul and Moreau, Luc (2013). _PROV Overview: An Overview of the PROV Family of Documents._ W3C Working Group Note. World Wide Web Consortium. https://www.w3.org/TR/prov-overview/ accessed 27th August 2021.
 
Mohan, Sanjeev and Maguire, Jow (2020). 2021 Planning Guide for Data Management. _Gartner Research Note G00729003._