[ISDE Metadata - Home](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/README.md) | [Guides](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/README.md) | Dataset Citation

# Dataset Citation

This document outlines steps to gain a citation for a dataset and how to record the citation in ISDE metadata.

- _Author_ [Adam Leadbetter](https://github.com/adamml)
- _Last editied_ 17th February 2021

## Table of Contents

1. [Terminology](#terminology)
2. [Steps to Data Citation](#steps-to-data-citation)
3. [Including a Citation in Metadata Records](#including-a-citation-in-netadata-records)
    1. ISO19139
    1. DCAT
    1. Schema.org
5. [Open Issues](#open-issues)
6. [References / Further Reading](#references--further-reading)

## Terminology

Adapted from Callaghan _et al._ (2012):

- __doi__ A digital object identifier - a persistent identifier to a 
- __Dataset Serving__ Making a dataset available for download on the web
- __Data Publication__ Data avaialble on-line with persistent identification and persistent access.
- __Dataset Citation__ Dataset citation is the method of providing a formal reference to the datasets used in research, reports and publications. A dataset citation includes key descriptive information about the dataset, such as the title, source, and parties responsible for creating the dataset. 

## Steps to Data Citation

Adapted from Leadbetter _et al._ (2013):

Before you can begin minting dois:

1. __Ensure you can persistently serve a dataset__. Generally, data citation requires that the data do not change (i.e. are a static version of the dataset) so that the cited dataset is reproducible. A decadal timescale for this reproducibility is expected. Before progressing with the the data citation process establishing a trategy to address this is required. Some doi providers may provide storage options to meet this requirement.
2. __Choose a doi provider__. Options include [Datacite](https://datacite.org/); [Dryad](https://datadryad.org/); [Figshare](https://figshare.com/); [Zenodo](https://zenodo.org/)

When minting a doi for a dataset:

1. __Establish the dataset authorship__. It is important at the outset to establish who needs to be on the author list for a dataset, and what the order of the authors should be. It is also good practice for the organisation responsible for publishing the dataset and minting the doi to ensure all authors are happy with their names being made public in association with the dataset.
2. __Create the metadata record for the dataset__. A full ISDE metadata record should be created for the record. However, the doi provider might also require a metadata record in their own profile. For example, Datacite has a metadata kernel decribed [here](https://schema.datacite.org/) which uses a minimal set of elements to describe a doi and to connect the doi to the full metadata record and its URL.


## Including a Citation in Metadata Records

## Open Issues

1. Citation of dynamic datasets
2. How to choose a doi provider

## References / Further Reading
S. Callaghan, S. Donegan, S. Pepler, M. Thorley, N. Cunningham, P. Kirsch, L. Ault, P. Bell, R. Bowie, A. Leadbetter, R. Lowry, G. Moncoiffe, K. Harrison, B. Smith-Haddon, A. Weatherby, D. Wright (2012). Making Data a First Class Scientific Output: Data Citation and Publication by NERC’s Environmental Data Centres. _International Journal of Digital Curation_ 7(1):107-113. [https://doi.org/10.2218/ijdc.v7i1.218](https://doi.org/10.2218/ijdc.v7i1.218)

A. Leadbetter, L. Raymond, C. Chandler, L. Pikula, P. Pissierssens, E. Urban (2013). _Ocean Data Publication Cookbook_ Paris: UNESCO, 41 pp. & annexes. (Manuals
and Guides. Intergovernmental Oceanographic Commission, 64), (IOC/MG/64)
