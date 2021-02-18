[ISDE Metadata - Home](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/README.md) | [Guides](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/guides/README.md) | Dataset Citation

# Dataset Citation

This document outlines steps to gain a citation for a dataset and how to record the citation in ISDE metadata.

- _Author_ [Adam Leadbetter](https://github.com/adamml)
- _Last edited_ 17th February 2021
- _Created_ 

## Table of Contents

1. [Terminology](#terminology)
2. [Steps to Data Citation](#steps-to-data-citation)
3. [Including a Citation in Metadata Records](#including-a-citation-in-netadata-records)
    1. [ISO19115/ISO19139](#iso1911519139)
    1. [DCAT](#dcat)
    1. [Schema.org](#schemaorg)
5. [Open Issues](#open-issues)
6. [References / Further Reading](#references--further-reading)

## Terminology

Adapted from Callaghan _et al._ (2012):

- __doi__ A digital object identifier - a persistent identifier to a digital object (document, article, dataset etc...) consisting of a series of letters, numbers and symbols and linking to that object on the Web
- __Minting__ The act of creating an individual doi
- __Dataset Serving__ Making a dataset available for download on the Web
- __Data Publication__ Data avaialble on-line with persistent identification and persistent access.
- __Dataset Citation__ Dataset citation is the method of providing a formal reference to the datasets used in research, reports and publications. A dataset citation includes key descriptive information about the dataset, such as the title, source, and parties responsible for creating the dataset. 

## Steps to Data Citation

Adapted from Leadbetter _et al._ (2013):

Before you can begin minting dois:

1. __Ensure you can persistently serve a dataset__. Generally, data citation requires that the data do not change (i.e. are a static version of the dataset) so that the cited dataset is reproducible. A decadal timescale for this reproducibility is expected. Before progressing with the the data citation process establishing a trategy to address this is required. Some doi providers may provide storage options to meet this requirement.
2. __Choose a doi provider__. Options include [Datacite](https://datacite.org/); [Dryad](https://datadryad.org/); [Figshare](https://figshare.com/); [Zenodo](https://zenodo.org/)

When minting a doi for a dataset:

1. __Establish the dataset authorship__. It is important at the outset to establish who needs to be on the author list for a dataset, and what the order of the authors should be. It is also good practice for the organisation responsible for publishing the dataset and minting the doi to ensure all authors are happy with their names being made public in association with the dataset.
2. __Create the metadata record for the dataset__. A full ISDE metadata record should be created for the record. However, the doi provider might also require a metadata record in their own profile. For example, Datacite has a metadata kernel decribed [here](https://schema.datacite.org/) which uses a minimal set of elements to describe a doi and to connect the doi to the full metadata record and its URL. Following Buneman _et al._ (2020), the metadata record should include the following information:
    1. A title containing the version of the dataset being cited.
    2. An author list with affiliations.
    3. A short descriptiion of the dataset (see the ISDE [Abstracts](https://github.com/Irish-Spatial-Data-Exchange/isdi-metadata/blob/main/guides/ABSTRACTS.md) guideline for comprehensive details). This may optionally include a rationale for creating the dataset citation.
    4. A link to download the dataset.
    5. Details of the organisation repsonble for publishing the dataset. This is the organisation repsonsible for monting and maintainfg the doi.
    6. Any citations required to support the dataset (e.g. other datasets used in creating this dataset; papers used in creating the dataset processing methods).
    7. The doi of the dataset.
4. __Publish the dataset to the Web__. In general, data with a citation should be publically, openly available.
5. __Link the metadata record to the published data__.
6. __Assign a doi suffix for the dataset__. The doi prefix will be assigned by your doi provider. It may be unique to your organisation as a data publisher, or to the doi provider dependeding on the service you choose and how it is implemented. It is good practice to use a unique identifier scheme for yur suffix, such as a Univerally Unique ID (UUID). UUIDs can be programatically generated in daatabases or in a large number of coding languages, or from a service such as ["Online UUID Generator"](https://www.uuidgenerator.net/).
7. __Mint the doi__. This step will require following the specific instructions providd by your doi provider
8. __Create a short doi__. This step is not required, but is considered best practice. Use the shortDOI service [here](https://shortdoi.org/).
9. __Update your metadata record for the doi, short doi and citation text__.

## Including a Citation in Metadata Records

### ISO19115/19139

The `CI_Citation` block is used to carry all citation details for an ISO19115 metadata record.

`MD_Identifier` blocks are used to associate both the full and short doi with a dataset. The `gmd:authority` is used to distinguish between the full and short doi, but not to distinguish the suthority through whom the doi was issued which is against the principles of the doi system.

The `otherCitationDetails` element is used to carry the suggested citation text. More detail on the authors and their affiliations and the dataset publisher can be provided in the powerful `CI_ResponsibleParty` block, connected via a `citedResponsibleParty` element.

```xml
<gmd:MD_Metadata>
    ...
    <gmd:identificationInfo>
        <gmd:MD_DataIdentification>
            <gmd:citation>
                <gmd:CI_Citation>
                    ...
                    <gmd:identifier>
                        <gmd:MD_Identifier>
                            <gmd:authority>
                                <gmd:CI_Citation>
                                    <gmd:title>
                                        <gco:CharacterString>International DOI Foundation</gco:CharacterString>
                                    </gmd:title>
                                    <gmd:date>
                                        <gmd:CI_Date>
                                            <gmd:date>
                                                <gco:Date>2018-07-24</gco:Date>
                                            </gmd:date>
                                            <gmd:dateType>
                                                <gmd:CI_DateTypeCode codeList="https://data.noaa.gov/resources/iso19139/schema/resources/Codelist/gmxCodelists.xml#CI_DateTypeCode" value="creation">creation</gmd:CI_DateTypeCode>
                                            </gmd:dateType>
                                        </gmd:CI_Date>
                                    </gmd:date>
                                </gmd:CI_Citation>
                            </gmd:authority>
                            <gmd:code>
                                <gco:CharacterString>https://doi.org/10.20393/f0257b6e-c55e-4aff-9a68-1c755e3dd8ed</gco:CharacterString>
                            </gmd:code>
                        </gmd:MD_Identifier>  
                    </gmd:identifier>
                    <gmd:identifier>
                        <gmd:MD_identifier>
                            <gmd:authority>
                                <gmd:CI_Citation>
                                    <gmd:title>
                                        <gco:CharacterString>shortDOI.org</gco:CharacterString>
                                    </gmd:title>
                                    <gmd:date>
                                        <gmd:CI_Date>
                                            <gmd:date>
                                                <gco:Date>2018-07-24</gco:Date>
                                            </gmd:date>
                                            <gmd:dateType>
                                                <gmd:CI_DateTypeCode codeList="https://data.noaa.gov/resources/iso19139/schema/resources/Codelist/gmxCodelists.xml#CI_DateTypeCode" value="creation">creation</gmd:CI_DateTypeCode>
                                            </gmd:dateType>
                                        </gmd:CI_Date>
                                    </gmd:date>
                                </gmd:CI_Citation>
                            </gmd:authority>
                            <gmd:code>
                                <gco:CharacterString>http://doi.org/csgf</gco:CharacterString>
                            </gmd:code>
                        </gmd:MD_identifier>  
                    </gmd:identifier>
                    <gmd:otherCitationDetails>
                        <gco:CharacterString>de Eyto, Elvira (1); Dillane, Mary (1); Cooney, Joseph (1); Hughes, Pat (1); Murphy, Michael (1); Nixon, Pat (1); Sweeney, David (1); Poole, Russell (1); Rouen, Martin (2); Ryder, Elizabeth (1); Daly, Sile (3); Ó'Catháin, Donncha (1); Archer, Lorraine (4). (2018) Midnight profiles of chlorophyll fluorescence data from Lough Furnace, 2009-2014 and associated phytoplankton and descriptive data. Marine Institute, Ireland. 10/csgf . (1) Marine Institute; Ireland; (2) Lakeland Instrumentation Ltd; United Kingdom; (3) University College Dublin; Ireland; (4) Institute of Technology Sligo; Ireland.</gco:CharacterString>
                   </gmd:otherCitationDetails>
                </gmd:CI_Citation>
            </gmd:citation>
        </gmd:MD_DataIdentification>
    </gmd:identificationInfo>
</gmd:MD_Metadata>
```

### DCAT

The example below follows the patterns of Albertoni _et al._ (2020) for the use of the DCAT vocabulary for data citations. This pattern adds connections between the authors and affiliated organisations using both `foaf:member` and `prov:actedOnBehalfOf` predicates.

```ttl
@prefix adms: <https://www.w3.org/ns/adms#>.
@prefix dcat: <http://www.w3.org/ns/dcat#>.
@prefix dct: <http://purl.org/dc/terms/>.
@prefix foaf: <http://xmlns.com/foaf/0.1/>.
@prefix prov: <http://www.w3.org/ns/prov#>.
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>.
@prefix skos: <http://www.w3.org/2004/02/skos/core#>.
@prefix xsd: <http://www.w3.org/2001/XMLSchema#>.

@base <http://data.marine.ie/geonetwork/srv/api/records/ie.marine.data:dataset.2740>.

<> a dcat:dataset;
	dct:creator _:johnSmith, _:joeBloggs; 
    dct:identifier _:doi, _:shortDOI;
    dct:issued "2018-07-24"^^xsd:date;
    dct:publisher _:marineInstitute.

_:doi a adms:Identifier;
	skos:notation "https://doi.org/10.20393/f0257b6e-c55e-4aff-9a68-1c755e3dd8ed"^^xsd:anyURI;
	adms:schemaAgency "International DOI Foundation";
	dct:creator _:internationalDoiFoundation.

_:shortDoi a adms:Identifier;
	skos:notation "https://doi.org/csgf"^^xsd:anyURI;
	adms:schemaAgency "International DOI Foundation";
	dct:creator _:internationalDoiFoundation.

_:johnSmith a foaf:Person, prov:Agent;
	foaf:name "John Smith";
	prov:actedOnBehalfOf _:marineInstitute.

_:johnSmithOrcid a adms:Identifier;
	skos:notation "https://orcid.org/0000-0000-0000-0000"^^xsd:anyURI ;
	adms:schemaAgency "ORCID".

_:joeBloggs a foaf:Person, prov:Agent;
	foaf:name "Joe Bloggs";
	prov:actedOnBehalfOf _:marineInstitute.

_:joeBloggsOrcid a adms:Identifier;
	skos:notation "https://orcid.org/0000-0000-0000-0001"^^xsd:anyURI ;
	adms:schemaAgency "ORCID".

_:internationalDoiFoundation a foaf:Organization, foaf:Group, prov:Agent;
	foaf:name "International DOI Foundation";
	rdfs:label "International DOI Foundation";
	foaf:homepage <https://www.doi.org/>;.

_:marineInstitute a foaf:Organization , foaf:Group, prov:Agent;
	foaf:name "Marine Institute";
	rdfs:label "Marine Institute";
	foaf:homepage <http://www.marine.ie>;
	foaf:member _:joeBloggs, _:johnSmith.

```

### Schema.org

Following Jones _et al._ (2021):
- the identifier block is used to encode the full doi
- the sameAs property is used to add the short doi

```json
{
    "@context": {
        "@vocab": "https://schema.org",
        "@type": "Dataset",
        "identifier":{
            "@id": "https://doi.org/10.20393/f0257b6e-c55e-4aff-9a68-1c755e3dd8ed",
            "@type": "PropertyValue",
            "name": "DOI: 10.20393/f0257b6e-c55e-4aff-9a68-1c755e3dd8ed",
            "propertyID": "https://registry.identifiers.org/registry/doi",
            "value": "doi:10.20393/f0257b6e-c55e-4aff-9a68-1c755e3dd8ed",
            "url": "https://doi.org/10.20393/f0257b6e-c55e-4aff-9a68-1c755e3dd8ed"
        },
        "sameAs": "http://doi.org/csgf"
    }
}
```

## Open Issues

1. Citation of dynamic datasets
2. How to choose a doi provider

## References / Further Reading
R. Albertoni, D. Browning, S. Cox , A. G. Beltran, A. Perego, P. Winstanley (2020). _Data Catalog Vocabulary (DCAT) - Version 3
W3C First Public Working Draft 17 December 2020_ World Wide Web Consortium. Accessed 18th February 2021 [https://www.w3.org/TR/2020/WD-vocab-dcat-3-20201217/](https://www.w3.org/TR/2020/WD-vocab-dcat-3-20201217/)

P. Buneman, G. Christie, J. A. Davies, R. Dimitrellou, S. D. Harding, A. J. Pawson, J. L. Sharman, Y. Wu (2000). Why data citation isn't working, and what to do about it. _Database_ 2020:baaa022. [https://doi.org/10.1093/databa/baaa022](https://doi.org/10.1093/databa/baaa022)

S. Callaghan, S. Donegan, S. Pepler, M. Thorley, N. Cunningham, P. Kirsch, L. Ault, P. Bell, R. Bowie, A. Leadbetter, R. Lowry, G. Moncoiffe, K. Harrison, B. Smith-Haddon, A. Weatherby, D. Wright (2012). Making Data a First Class Scientific Output: Data Citation and Publication by NERC’s Environmental Data Centres. _International Journal of Digital Curation_ 7(1):107-113. [https://doi.org/10.2218/ijdc.v7i1.218](https://doi.org/10.2218/ijdc.v7i1.218)

M. B. Jones, S. Richard, D. Vieglais, A. Shepherd, R. Duerr, D. Fils, L. McGibbney. (2021). Science-on-Schema.org v1.2.0 (Version 1.2.0). Zenodo. https://doi.org/10.5281/zenodo.4477164

A. Leadbetter, L. Raymond, C. Chandler, L. Pikula, P. Pissierssens, E. Urban (2013). _Ocean Data Publication Cookbook_ Paris: UNESCO, 41 pp. & annexes. (Manuals
and Guides. Intergovernmental Oceanographic Commission, 64), (IOC/MG/64). [http://iode.org/mg64](http://iode.org/mg64)
