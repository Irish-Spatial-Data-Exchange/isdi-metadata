[ISDE Metadata - Home](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/README.md) | [Guides](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/guides/README.md) | Abstracts

# Abstracts

This document outlines recommended best practices for writing a metadata abstract for ISDE.

- _Author_ [Adam Leadbetter](https://github.com/adamml)
- _Last edited_ 18th February 2021
- _Created_ 17th February 2021

## Table of Contents

1. [General Recommendations](#general-recommendations)
1. [Specific Recommendations](#specific-recommendtions)
1. [Examples](#examples)
1. [Including an Abstract in Metadata Records](#including-an-abstract-in-metadata-records)
    1. ISO19115/19139
    1. DCAT
    1. Schema.org
1. [References](#references)

## General Recommendation

Adapted from NOAA(2020):

- Write using plain English that is easily understood by the general public (think a leaving cert level student). Whilst some terminology from a specific discipline or domain may be necssary in the abstract overly technical or scientific language and jargon should be avoided.
- The abstract for a metadata record is not the same as an abstract for a scientific paper or article.
- The abstract for a metadata record should be limited to describing the dataset that the metadata record is for.
- The abstract for a metadata record should provide descriptive information about the dataset in a clear, concise human readable manner.
- Any acronyms included in anabstract should be fully expanded on their first use to avoid ambiguity - unless they are well known to the general public. 
- In general, an abstract should be written in the present or past tense. Avoid the future tense where possible.
- Do not use any formatting (HTML, Markdown, Comma Separated Values (CSV), tables) in an abstract. Limit the content to plain text.
- Do not include web links as URLs in an abstract. URLs are prone to change and to breaking and in general link checkers do not work on the abstract element of a metadata record.
- Do not copy an abstarct from a scientific journal article or report. This can lead to copyright issues. Additionally, an abstract from a scientifci journal is not intended as a dataset description and does not meet this requirements of this guideline.
- Do not include peristent identifiers to the dataset, such as digital object identifiers, or journal articles referencing the dataset in the abstract as these should be included elsewhere in the metadata (see [Dataset Citation](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/guides/DATASET_CITATION.md))

## Specific Recommendations

Contextual information to support the dataset is important to ensure the proper reuse of the dataset. This should include, but is not necessarily limited to:

- __Who__ Which organisations were resposnsible for collecting or creating the dataset; and which organisations were responsible for processing the dataset.
- __What__ A brief overview of what parameters the dataset contains. Keywords elsewhere in the metadata record can be used to add more specific paramter defintions from controled vocabularies.
- __When__ A generalised description of the time period covered by the dataset. Exact time periods can be specified elsewhere in the metadata.
- __Where__ A generalised description of the geographical area covered by the dataset. A geographical feature can be more precisely defined elseehere in the metadata by a spatial coverage field, and keywords can be used elsewhere in the metdata to link a dataset to specific gazetteer entries.
- __Why__ An outline as to why the dataset was collected or created and as to why it is distinct from other, similar datasets.
- __How__ A brief and generalised description of how the dataset was collected or created and any processing steps the dataset has been through.
- __Limitations__ Are there any applications for which the dataset may not be suitable? What other limitations are there on the dataset (e.g. is the quality of the data compromised in some way)?
- __Formats__ What format(s) is/are the dataset available in?
- __Recommended Tools__ Are there any recommended software tools for analysing, furthere processing or reusing the dataset?

## Examples



## Including an Abstract in Metadata Records



## References

NOAA (2020). Abstract Oher /recommendations. _National Geophysical Data Center Wiki_. https://ngdc.noaa.gov/wiki/index.php/Abstract_Other_Recommendations Accessed 18th February 2020.