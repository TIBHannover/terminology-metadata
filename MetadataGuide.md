# Ontology metadata recommendations by TIB

Document status: **DRAFT**

Modification date: 2024-05-02

Creators and contributors:

<!-- * [Last name, First Name  (Affiliation)](https://orcid.org/) -->
* [Arndt, Susanne  (Technische Informationsbibliothek)](https://orcid.org/0000-0002-1019-9151)
* [Ganske, Anette  (Technische Informationsbibliothek)](https://orcid.org/0000-0003-1043-4964)
* [Hauschke, Christian  (Technische Informationsbibliothek)](https://orcid.org/0000-0003-2499-7741)
* [Strömert, Philip  (Technische Informationsbibliothek)](https://orcid.org/0000-0002-1595-3213)
* [Vogt, Lars (Technische Informationsbibliothek)](https://orcid.org/0000-0002-8280-0487)

License: [CC BY 4.0 Deed Attribution 4.0 International ](https://creativecommons.org/licenses/by/4.0/)

Zenodo archive: <https://www.doi.org/10.5281/zenodo.11103071>

<div style="page-break-after: always;"></div>

## Table of contents

0. [Executive summary](#0-executive-summary)
1. [Why Ontology Metadata?](#1-ontology-metadata)
    * [1.1 How to provide ontology metadata](#11-how-to-provide-ontology-metadata)
    * [1.2 Why ontology metadata?](#12-why-ontology-metadata)
2. [How to read this document](#2-how-to-read-this-document)
    * [2.1 Chapter structure and wording](#21-chapter-structure-and-wording)
    * [2.2 Metadata validation with SHACL](#22-metadata-validation-with-shacl)
    * [2.3 Prefixes used in this document](#23-prefixes-used-in-this-document)
    * [2.4 Acronyms](#24-acronyms)
3. [Mandatory Metadata](#3-mandatory-metadata)
    * [3.1 Ontology title](#31-ontology-title)
    * [3.2 Preferred ontology prefix/ acronym](#32-preferred-ontology-prefix-acronym)
    * [3.3 Ontology license](#33-ontology-license)
    * [3.4 Ontology creator(s)](#34-ontology-creators)
    * [3.5 Ontology version IRI](#35-ontology-version-iri)
    * [3.6 Ontology creation date](#36-ontology-creation-date)
    * [3.7 Ontology abstract](#37-ontology-abstract)
    * [3.8 Ontology issue tracker](#38-ontology-issue-tracker)
    * [3.9 Ontology documentation](#39-ontology-documentation)
4. [Recommended Metadata](#4-recommended-metadata)
    * [4.1 Ontology contributor(s)](#41-ontology-contributors)
    * [4.2 Ontology funder](#42-ontology-funder)
    * [4.3 Ontology funding](#43-ontology-funding)
    * [4.4 Ontology audience description](#44-ontology-audience-description)
    * [4.5 Ontology subject(s)](#45-ontology-subjects)
    * [4.6 Ontology annotation language(s)](#46-ontology-annotation-languages)
    * [4.7 Applied logical framework](#47-applied-logical-framework)
    * [4.8 Ontology serialization/ file format](#48-ontology-serialization-file-format)
    * [4.9 Ontology status](#49-ontology-status)
    * [4.10 Ontology code repository](#410-ontology-code-repository)
    * [4.11 Ontology distributions/ products](#411-ontology-distributions-products)
    * [4.12 Application example](#412-application-example)
    * [4.13 Related resource(s)](#413-related-resources)
    * [4.14 Citation suggestion](#414-citation-suggestion)
    * [4.15 Ontology sources (derived from)](#415-ontology-sources-derived-from)
    * [4.16 Ontology root classes](#416-ontology-root-classes)
5. [Optional Metadata](#5-optional-metadata)
    * [5.1 Ontology description](#51-ontology-description)
    * [5.2 Alternative ontology title](#52-alternative-ontology-title)
    * [5.3 Alternative ontology prefix/ acronym](#53-alternative-ontology-prefix-acronym)
    * [5.4 Related version/ version history](#54-related-version-version-history)
        * [5.4.1 Prior ontology version](#541-prior-ontology-version)
        * [5.4.2 Related ontology version](#542-related-ontology-version)
        * [5.4.4 Compatible ontology version](#543-compatible-ontology-version)
        * [5.4. Incompatible ontology version](#544-incompatible-ontology-version)
    * [5.5 Social media](#55-social-media)
    * [5.6 KOS type](#56-kos-type)
    * [5.7 Example ontology identifier](#57-example-ontology-identifier)
    * [5.8 Ontology identifier pattern](#58-ontology-identifier-pattern)
    * [5.9 Ontology homepage](#59-ontology-homepage)
    * [5.10 Ontology publisher](#510-ontology-publisher)
    * [5.11 Ontology comments](#511-ontology-comments)
    * [5.12 Example ontology class](#512-example-ontology-class)
    * [5.13 Ontology mailing list](#513-ontology-mailing-list)
    * [5.14 Ontology logo/ depictions/ related visualization](#514-ontology-logo-depiction-related-visualizations)
    * [5.15 Related identifiers](#515-related-identifiers)
    * [5.16 Development environment](#516-development-environment)
    * [5.17 Alignments/ mappings](#517-alignments-mappings)
        * [5.17.1 Aligned resources](#5171-aligned-resources)
        * [5.17.2 Alignment files/ mapping files](#5172-alignment-files-mapping-files)
    * [5.18 Competency questions](#518-competency-questions)
    * [5.19 Applied methodology](#519-applied-methodology)
    * [5.20 Preferred ontology namespace](#520-preferred-ontology-namespace)
    * [5.21 Ontology issue date](#521-ontology-issue-date)
    * [5.22 Modification date](#522-modification-date)
    * [5.23 Textual version information](#523-textual-version-information)
    * [5.24 Version notes](#524-version-notes)
6. [Tabular overview - recommendations](#6-tabular-overview)
7. [Relations to related work](#7-relations-to-related-work)
8. [Sources](#8-sources)

<div style="page-break-after: always;"></div>

## 0. Executive summary

The number of ontology registries, archives and catalogues has increased over time. There are multiple services that list and also index ontologies. The registry entries of such services usually require the metadata of the ontologies they index, in order to make the ontologies findable and to provide users with general introductory information about the ontologies and their reuse. Registries currently face several problems, though:

* It is not yet standard procedure to provide rich ontology metadata despite efforts towards increasing the FAIRness of semantic resources [[1]](#source1), [[2]](#source2), in particular legacy ontologies may not be updated with rich metadata.
* Metadata may be provided in unstructured form outside of the ontology source which makes their collection difficult.
* Different registries may provide structured, open metadata documents for the same ontology which may at some point become incongruous with the source data.
* Currently, no standard metadata schema for ontologies exists.

In order to avoid these problems, metadata management should be part of the ontology engineering process: The metadata of an ontology should be part of the ontology's code base or the ontology itself. This would make the ontology resp. its code base the single source of truth for its own metadata.

It is therefore mandatory that an ontology provides its own metadata with machine-understandable semantics and established terms from metadata ontologies and controlled vocabularies. The metadata need to be as or even more persistent than the ontology itself. [Principle R1][FAIR Principles R1] of the FAIR principles [[1]](#source2) furthermore recommends to not just provide metadata that allow the discovery of an ontology (e.g. title, ontology prefix, authors), but to add metadata that richly describe the contents of the ontology and the conditions of its creation and use (cf. [1.2 Why ontology metadata?](#12-why-ontology-metadata)).

With this document, *TIB - Leibniz Information Centre for Science and Technology University Library* provides a practical guide for metadata management of ontologies. It gives recommendations on required, recommended and optional metadata for ontologies. As there are currently several recommendations available (cf. [[13]](#source13), [[14]](#source14), [[15]](#source15), [[16]](#source16), [[17]](#source17), [[18]](#source18), [[19]](#source19), [[20]](#source20), [[21]](#source21), [[22]](#source22), [[23]](#source23)), this guide will provide recommendations on ontology metadata that particularly adress the publishing of ontologies on the [TIB Terminology Service][TIB TS].

In addition, we provide shapes for SHACL validators based on these recommendations (cf. [2.2 Metadata validation with SHACL](#22-metadata-validation-with-shacl)).

## 1 Ontology metadata

### 1.1 How to provide ontology metadata?

Ontology metadata must be provided in a machine-understandable format. We therefore recommend to provide them as a part of the ontology itself: The metadata should be statements about the ontology that use dedicated annotation, object or data properties, to guarantee a good level of granularity and distinguishability of the metadata.

If you provide metadata that are here considered as *recommended* or *optional* in a single file, you may add a statement using rdfs:seeAlso to point to that document. Ideally, this document should then be etrievable with a persistent identifier (PID) - e.g. a DOI or a PURL. However, we do not recommend this, especially if that document is not machine-understandable.

### 1.2 Why ontology metadata?

Providing rich, machine-understandable metadata for an ontology has many advantages for their users (cf. [[1]](#source1), [[2]](#source2)), e.g.:

* They give a rich description about the ontology including its provenance, scope and purpose.
* They allow automatic extraction and indexing of the ontology by different services and reduce the effort of manual curation.
* They enable others to reuse the ontology or its terms and apply them for their own purposes.
* They indicate the current status of an ontology, distinguishing whether an ontology is still maintained by an active community or whether it is dormant.
* They allow referencing other Web resources with persistent identifiers (e.g. resources with identifiers like [DOI][doi], [ROR][ror], [ORCiD][orcid], [RAiD][raid], etc.).
* They allow detailed requests about ontologies on the web.
* They enable comparability and automated comparisons of ontologies.
* They can be retrieved via APIs and used in many different services.

<div style="page-break-after: always;"></div>

## 2 How to read this document

### 2.1 Chapter structure and wording

This guide tries to use clear wording to distinguish absolute requirements (*must*, *required*, *mandatory*) from either recommendations (*should*, *recommended*) or optional metadata (*may*, *can*, *could*, *optional*). The sub-sections will each give

* a short introduction to the metadatum
* recommend a property
* recommend controlled vocabularies where appropriate
* provide examples in text/turtle serialization
* list alternative properties that may also be used to provide the metadatum
* specify SHACL validation rules (cf. section [2.2 Metadata validation with SHACL](#22-metadata-validation-with-shacl))

Subproperties to any properties mentioned will not be implied, but explicitly listed in the "alternative properties" part of each section.

### 2.2 Metadata validation with SHACL

This guide is a human-readable specification. In addition, we also provide a SHACL specification of these recommendations that can be used for data validation.

The shape can be used with SHACL validators to test ontologies for any violations of required metadata at [TIB Terminology Service][TIB TS] and to get suggestions for recommended metadata. We recommend the online SHACL validators [SHACL Playground][shacl-playground], [SHACL Playground by Zazuko](https://shacl-playground.zazuko.com/) or [SHACL Play!](https://shacl-play.sparna.fr/play/) for performing evaluations. Turtle or json-ld are common input format. SHACL Play! also allows to use IRIs for shapes and ontologies.

The shape is available in a single file at <https://www.purl.org/ontologymetadata/shape>.

The shape can also be used to evaluate metadata of instances of skos:ConceptScheme. The instances of skos:ConceptScheme need to be declared as instances of owl:Ontology to trigger the shapes (cf. also section [4.6.2. SKOS Concept Schemes and OWL Ontologies](https://www.w3.org/TR/skos-reference/#L1170) of the [SKOS Reference document](https://www.w3.org/TR/2009/REC-skos-reference-20090818/)).

### 2.3 Prefixes used in this document

Code examples will usually provide full IRIs of statement subjects and objects. Properties will be presented in prefixed notation. The table provides the prefix definitions:

|prefix|namespace|
|-|-|
|adms|<http://www.w3.org/ns/adms#>|
|bibo|<http://purl.org/ontology/bibo/>|
|dcat|<http://www.w3.org/ns/dcat#>|
|dcterms|<http://purl.org/dc/terms/>|
|doap|<http://usefulinc.com/ns/doap#>|
|foaf|<http://xmlns.com/foaf/0.1/>|
|idot|<http://identifiers.org/idot/>|
|mod|<https://w3id.org/mod#>|
|obo|<http://purl.obolibrary.org/obo/>|
|omv|<http://omv.ontoware.org/2005/05/ontology#>|
|owl|<http://www.w3.org/2002/07/owl#>|
|pav|<http://purl.org/pav/>|
|premis|<http://www.loc.gov/premis/rdf/v3/>|
|rdf|<http://www.w3.org/1999/02/22-rdf-syntax-ns#>|
|rdfs|<http://www.w3.org/2000/01/rdf-schema#>|
|schema|<https://schema.org/>|
|sh|<http://www.w3.org/ns/shacl#>|
|vann|<http://purl.org/vocab/vann/>|
|void|<http://rdfs.org/ns/void#>|
|xsd|<http://www.w3.org/2001/XMLSchema#>|

### 2.4 Acronyms

|Acronym|Full form|
|-|-|
|DOI|Digital Object Identifier|
|IRI|International Resource Identifier|
|PID|Persistent Identifer|
|ROR|Research Organization Identifier|

<div style="page-break-after: always;"></div>

## 3 Mandatory metadata

Metadata in this section are mandatory for publishing an ontology at [TIB Terminology Service][TIB TS]. Ontologies missing these metadata will not be accepted.

### 3.1 Ontology title

Ontologies must state their own title. The title will be displayed on [TIB Terminology Service](https://terminology.tib.eu/ts), e.g. on each [ontology's landing page](https://terminology.tib.eu/ts/ontologies/bfo), in [search results](https://terminology.tib.eu/ts/search?q=ontology&page=1&type=ontology) or in [ontology lists][TIB TS ontology list]. The ontology must have at most one title per language. Ontology titles should be tagged for language.

Recommended property: <http://purl.org/dc/terms/title>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:title "Some Ontology"@en .
```

Alternative properties:

* <http://purl.org/dc/elements/1.1/title>
* <https://schema.org/name>
* <https://schema.org/headline>

SHACL validation rules:

* `sh:datatype rdf:langString`
* `sh:minCount 1`
* `sh:uniqueLang true`

### 3.2 Preferred ontology prefix/ acronym

The ontology must declare its preferred, unique prefix or a short acronym. The prefix/ acronym will be used on TIB Terminology Service's [ontology list][TIB TS ontology list] as a short name for the ontology. It must not contain hyphens or other special characters and should be written in lowercase.

You can check whether an ontology prefix is already in use on services like [prefix.cc][prefix.cc] or [Bioregistries][Bioregistries].

Recommended property: <http://purl.org/vocab/vann/preferredNamespacePrefix>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    vann:preferredNamespacePrefix "so"^^xsd:string .
```

Alternative properties:

* <http://identifiers.org/idot/preferredPrefix>
* <https://w3id.org/mod#acronym>

SHACL validation rules:

* `sh:datatype xsd:string`

### 3.3 Ontology license

Ontologies must declare their license, referring to their license document via PID. The license text helps others to evaluate how they may reuse the ontology. Only ontologies with an open license will be published on [TIB Terminology Service][TIB TS]. Consider, for example, the [list of licenses][Open Definition license list] that are conformant with the [Open Definition][Open Definition 2.1].

Recommended property: <http://purl.org/dc/terms/license>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:license <http://creativecommons.org/licenses/by/4.0/> .
```

Alternative properties:

* <https://schema.org/license>
* <http://creativecommons.org/ns#license>
* <http://dbpedia.org/ontology/license>

SHACL validation rules:

* value must be from defined list of accepted licenses
* value must not be from defined list of unaccepted licences
* `sh:maxCount 1`
* `sh:minCount 1`

### 3.4 Ontology creator(s)

The ontology must list its creators, i.e. the people or institutions who were responsible for its development. It is recommended to refer to a creator with a PID (e.g. [ORCiD][orcid], [Wikidata][wikidata]-ID, or [ROR][ror]-ID). Plain name strings can be provided in addition for readability. If an ontology is developed by a larger group, it is recommended to give the organization or project identifier as the creator and list individual persons as contributors. If no project or organisation PID is available, the respective name (rdf:langString) will also be accepted.

Recommended property: <http://purl.org/dc/terms/creator>

Example 1 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:creator <https://orcid.org/0000-0000-0000-0000> .
```

Example 2 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> <http://purl.org/dc/terms/creator> <https://orcid.org/0000-0000-0000-0000>.

<https://orcid.org/0000-0000-0000-0000> rdf:type foaf:Person ; 
    <http://xmlns.com/foaf/0.1/firstName> "Max" ;
    <http://xmlns.com/foaf/0.1/lastName> "Muster" .
```

Alternative properties:

* <http://purl.org/dc/elements/1.1/creator>
* <https://schema.org/creator>
* <http://purl.org/pav/createdBy>
* <http://www.w3.org/ns/prov#wasAttributedTo>
* <https://schema.org/accountablePerson>
* <https://schema.org/author>

SHACL validation rules:

* `sh:minCount 1`
* `sh:nodeKind sh:IRI`

### 3.5 Ontology version IRI

Since the PURL of an ontology usually only points to the latest version of an ontology, each ontology must state its version IRI. A version IRI is a persistent identifier for a version of an ontology and is used to reliably retrieve this earlier version of the ontology. We recommended to use [semantic versioning][semver] or OBO style date-based versioning [[3]](#source3).

Recommended property: <http://www.w3.org/2002/07/owl#versionIRI>

Example 1 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    owl:versionIRI <https://www.purl.org/SomeOntology/1.0.0> .
```

Example 2 (text/turtle)

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    <http://www.w3.org/2002/07/owl#versionIRI> <https://www.purl.org/SomeOntology/2019-12-31> .
```

Example 3 (text/turtle):

```Turtle
<http://purl.obolibrary.org/obo/pco.owl> rdf:type owl:Ontology ;
    owl:versionIRI <http://purl.obolibrary.org/obo/pco/releases/2021-05-03/pco.owl> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:maxCount 1`
* `sh:minCount 1`
* `sh:nodeKind sh:IRI`

### 3.6 Ontology creation date

The ontology must state the date of its first creation.

Recommended property: <http://purl.org/dc/terms/created>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:created "2020-11-19T00:00:00"^^xsd:dateTime.
```

Alternative properties:

* <http://purl.org/pav/createdOn>
* <https://schema.org/dateCreated>
* <http://www.w3.org/ns/prov#generatedAtTime>

SHACL validation rules:

* `sh:datatype xsd:dateTime`
* `sh:maxCount 1`
* `sh:minCount 1`

### 3.7 Ontology abstract

The ontology must describe its own contents and scope with a few words or sentences in order to inform human users what the ontology tries to accomplish. The abstract is displayed in the [TIB Terminology Service ontology list][TIB TS ontology list] and on the landing page of each ontology - we therefore recommend to keep it short. You can also provide abstracts in several languages (as an rdf:langString). You may provide only one abstract per language. Each abstract may be up to 500 characters long including spaces. We do not recommend to use markups (html, markdown) in the abstract since these are not supported by [TIB Terminology Service][TIB TS]. If you want to include a longer text about the ontology, you should include a description [5.1 Ontology description](#51-ontology-description). For an extensive discussion about further aspects of the ontology (e.g. ontology creation, ontology use, ontology structure, etc.) we recommend the publication of a detailed documentation (cf. [3.9 Ontology documentation](#39-ontology-documentation)) or traditional academic article (cf. [4.13 Related resources](#413-related-resources)).

Recommended property: <http://purl.org/dc/terms/abstract>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:abstract "SomeOntology defines a range of classes and properties which can be applied to do stuff in a particular domain."@en , "SomeOntology definiert eine Reihe von Klassen und Properties, die in einer bestimmten Domäne verwendet werden können, um etwas damit zu tun."@de .
```

Alternative properties:

* <https://schema.org/abstract>

SHACL validation rules:

* `sh:datatype rdf:langString`
* `sh:maxLength 500`
* `sh:minCount 1`
* `sh:uniqueLang true`

### 3.8 Ontology issue tracker

The ontology must point to the issue tracker of its own development environment so that others may report bugs or suggestions to the developers. Ideally, the development process of an ontology is open and takes place on platforms like GitLab.com that allow for version management with version control software like git.

Recommended property: <http://usefulinc.com/ns/doap#bug-database>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    doap:bug-database <https://github.com/SomeOrganisation/SomeOntology/issues> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:maxCount 1`
* `sh:minCount 1`
* `sh:nodeKind sh:IRI`

### 3.9 Ontology documentation

To familiarize interested others with the concepts and scope of your ontology, some kind of documentation must be provided. This is usually an external online document that should be referenced by the ontology via an IRI or more persistently with a PID. A relatively easy way to do this is to use the tool Widoco [[4]](#source4), [[5]](#source5). It generates the documentation from the ontology and a resulting html-document can be published, for example with [GitLab Pages][gitlab pages]. This auto-generated document can contain customized passages that provide users with a deeper understanding of the ontology. There are, however, other forms of ontology documentations: scientific articles, well-curtated README files in repositories, Wikis etc. Here, we recommend to choose the form which is most easily attainable by your working group or project. Here are some examples for ontology documentation:

* PROV Ontology: <https://www.w3.org/TR/2013/REC-prov-o-20130430/>
* GND Ontology: <https://d-nb.info/standards/elementset/gnd>
* Gene Ontology - Relations: <https://geneontology.org/docs/ontology-relations/>
* CHEBI User Manual: <https://docs.google.com/document/d/1_w-DwBdCCOh1gMeeP6yqGzcnkpbHYOa3AGSODe5epcg/>
* CHEBI Developer Manual: <https://docs.google.com/document/d/11G6SmTtQRQYFT7l9h5K0faUHiAaekcLeOweMOOTIpME/>

The documentation of an ontology offers a lot of room to describe the ontology and provide detailed information about it to its readers. In fact, you may wonder whether it would be sufficient to provide a well-structured and well-readable text document - containing all the metadata suggested in this guide. Here, our answer is a clear no: Providing the metadata of your ontology in a machine-readable format, makes them much more re-usable (cf. sections [0. Executive summary](#0-executive-summary) and [1.2 Why ontology metadata](#12-why-ontology-metadata)).

Recommended property: <http://www.loc.gov/premis/rdf/v3/documentation>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    premis:documentation <https://www.purl.org/SomeOntology/Documentation> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:maxCount 1`
* `sh:minCount 1`
* `sh:nodeKind sh:IRI`

<div style="page-break-after: always;"></div>

## 4 Recommended Metadata

In addition to mandatory metadata, we recommend providing a number of further helpful metadata.

### 4.1 Ontology contributor(s)

If you had help in developing the ontology, you should indicate this by listing contributors so that all participants receive proper credit for their efforts. If an ontology is developed by a larger group, it is recommended to give the organization or project identifier as the creator and list individual persons as contributors. Persons and organisations shpuld be listed via PID, e.g. ORCiD or ROR.

Recommended property: <http://purl.org/dc/terms/contributor>

Example 1 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:contributor <https://orcid.org/0000-0000-0000-0000> .
```

Example 2 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:contributor <https://orcid.org/0000-0000-0000-0000>.

<https://orcid.org/0000-0000-0000-0000> rdf:type foaf:Person ;
    foaf:firstName "Max" ;
    foaf:lastName "Muster" .
```

Alternative properties:

* <http://purl.org/dc/elements/1.1/contributor>
* <https://schema.org/contributor>
* <http://purl.org/pav/contributedBy>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.2 Ontology funder

The development of an ontology may rely on external funding and take place in a third-party funding project. Since funding institutions usually want to be credited, we highly recommend mentioning them in your ontology. The best way to do so is by referring to their [ROR ID][ror].

Recommended property: <https://schema.org/funder>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    schema:funder <https://ror.org/018mejw64> .
```

Alternative properties:

* <http://rdf-vocabulary.ddialliance.org/discovery#fundedBy>
* <http://xmlns.com/foaf/0.1/fundedBy>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.3 Ontology funding

In addition to referencing the funding institution, you may be required to point to the specifc grant that enables the work on the ontology. We recommend to provide this information as an IRI, ideally a PID. We are aware, though, that PIDs for grants are not common, yet.  We therefore also accept this information in the form of acknowledgement statements (rdf:langString) containing the grant number provided by the funding institution.

<!-- später auf funding IDs eingehen, siehe Wiki: PIDs für Projekte, Grants, Awards (https://wiki.tib.eu/confluence/pages/viewpage.action?pageId=303800663) -->

Recommended property: <https://schema.org/funding>

Example 1 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    schema:funding <https://doi.org/00.00000/000000000> .
```

Example 2 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    schema:funding "The authors (Some Ontology Workgroup) would like to thank the Government of Some Country or Some Other Funding Institution for their funding and support within Some Funding Program (project number 123456789)."@en .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.4 Ontology audience description

Defining the target group of your ontology might be useful information for others when evaluating if and how they could reuse your ontology. You should describe the intended audience of the ontology. The audience description should be a short, language-tagged text.

Recommended property: <http://usefulinc.com/ns/doap#audience>

Examples (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    doap:audience "This ontology is intended for researchers in derivational morphology, a branch of linguistics. [...]"@en .   
```

See also [audience description of NMRC at TIB Terminology Service][nmrc-tib-ts] or the [audience description of CROPUSAGE at AgroPortal][cropusage-agroportal].

Alternative properties:

* <https://schema.org/audience>
* <http://purl.org/dc/terms/audience>

SHACL validation rules:

* `sh:datatype rdf:langString`
* `sh:maxCount 1`

### 4.5 Ontology subject(s)

We recommend tagging the ontology with a subject from a controlled vocabulary to indicate which domain it belongs to or which subject it deals with. This information is helpful for terminology service and ontology registry providers: Subject tags from controlled vocabularies can be mapped to other controlled vocabularies that are the basis of filters and browsing functionalities of such services. Subject tags can help to make your ontology better findable and available for a wider audience.

Recommended property: <http://purl.org/dc/terms/subject>

Recommended controlled vocabularies:

* <https://purl.org/linsearch>
* <https://terminology.tib.eu/ts/ontologies/bk>
* <https://terminology.tib.eu/ts/ontologies/dfgfo>
* <https://explore.gnd.network/> (remember: the identifiers need to start with <http://d-nb.info/gnd/>!)

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:subject <https://d-nb.info/gnd/4067537-3>, <https://d-nb.info/gnd/4070177-3>, <http://uri.gbv.de/terminology/bk/42.15>, <https://github.com/tibonto/dfgfo/201-03>.
```

The [TIB Terminology Service][TIB TS] applies [LinSearch][linsearch] labels for subject values, e.g.:

```Turtle
<https://www.purl.org/SomeOntology> dcterms:subject "Chemistry"^^xsd:string .
```

Alternative properties:

* <http://purl.obolibrary.org/obo/IAO_0000136>
* <https://schema.org/about>
* <https://schema.org/keywords>
* <http://www.w3.org/ns/dcat#keyword>
* <http://purl.org/dc/terms/coverage>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.6 Ontology annotation language(s)

If your ontology does not only provide formal semantics but also multi-lingual annotations for entities, you should provide information about the ontology annotation languages (e.g. for term labels, term definitions, etc.) in its metadata. At least one language should be provided, since at least one set of annotations is expected in a well-documented ontology. You should only claim that the ontology uses an annotation language, if all ontology elements or an extensive part of the ontology is annotaed in that languge.

Recommended property: <http://purl.org/dc/terms/language>

Recommended controlled vocabulary: <http://id.loc.gov/vocabulary/iso639-2>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:language <http://id.loc.gov/vocabulary/iso639-2/eng>, <http://id.loc.gov/vocabulary/iso639-2/tgl> .
```

Alternative properties:

* <https://schema.org/inLanguage>

SHACL validation rules:

* `sh:nodeKind sh:IRI`
* `sh:pattern "(^http://id.loc.gov/vocabulary/iso639-2/[a-z]{3}$|^https://id.loc.gov/vocabulary/iso639-2/[a-z]{3}$)"`

### 4.7 Applied logical framework

You should state which logical framework the ontology applies. The information can be given as a text, referring to the Semantic Web Standard (e.g. 'OWL 2') and possibly the OWL profile (e.g. 'OWL 2 EL profile').

Recommended property: <https://w3id.org/mod#hasFormalityLevel>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    mod:hasFormalityLevel "OWL version 2, EL profile"@en .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:datatype rdf:langString`
* `sh:maxCount 1`

### 4.8 Ontology serialization/ file format

You should state the ontology's serialization/ file format. The value should be provided as an IRI from the Media Types list of the Internet Assigned Number Authority (IANA) [[6]](#source6) or from the W3C resource Unique URIs for File Formats [[7]](#source7).

Recommended property: <http://omv.ontoware.org/2005/05/ontology#hasOntologySyntax>

Recommended controlled vocabularies:

* <https://www.w3.org/ns/formats>
* <https://www.iana.org/assignments/media-types/media-types>

In order to publish your ontology on the the [TIB Terminology Service][TIB TS] you must providde the ontology as one of the following media types:

* <https://www.iana.org/assignments/media-types/application/rdf+xml> resp. <http://www.w3.org/ns/formats/RDF_XML>
* <https://www.iana.org/assignments/media-types/text/turtle> resp. <http://www.w3.org/ns/formats/Turtle>
* OBO format (cf. <http://purl.obolibrary.org/obo/oboformat/spec.html>)

Currently, there is no registered media type for obo format.

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    omv:hasOntologySyntax <http://www.w3.org/ns/formats/Turtle> .
```

Alternative properties:

* <http://purl.org/dc/terms/format>
* <http://purl.org/dc/elements/1.1/format>
* <https://schema.org/encodingFormat>

SHACL validation rules:

* value must be from a defined list
* `sh:maxCount 1`
* `sh:nodeKind sh:IRI`

### 4.9 Ontology status

You should declare the current maintenance status of the ontology. You could use an English label to do so. We recommend using one of the values suggested by the OBO Foundry [[8]](#source8). Ontologies are prone to link rot and sometimes left abandoned. If you cannot keep up the work on an ontology, this needs to be documented: Is your ontology retired? Is it still a draft? Or is it maintained by an active community?

Recommended property: <http://purl.org/ontology/bibo/status>

Recommended controlled vocabulary: <https://obofoundry.org/docs/OntologyStatus.html>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    bibo:status "inactive"@en .

```

Alternative properties:

* <https://schema.org/creativeWorkStatus>

SHACL validation rules:

* `sh:datatype rdf:langString`
* `sh:maxCount 1`

### 4.10 Ontology code repository

A code repository (e.g. on [GitLab.com][gitlab] or [GitHub.com][github]) should be the development environment of your ontology. It should contain the source code of your ontology but may also be used to host your documentation, your issue tracker and may contain related resources like different distributions of your ontology, versions of your ontology, application examples, competency questions, discussions and decisions - in short: the entire history of your ontology should be located in a code repository.

Recommended property: <http://usefulinc.com/ns/doap#repository>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    doap:repository <https://github.com/SomeOrganisation/SomeOntology> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:maxCount 1`
* `sh:nodeKind sh:IRI`

### 4.11 Ontology distributions/ products

There are different serializations available for ontologies but not all are parsable by any system: For example an ontology tool may be well prepared for rdf/xml but not so much for json-ld. It may help users of your ontology, if you provided IRIs to available alternative serializations or distributions of your ontology.

Recommended property: <http://www.w3.org/ns/dcat#distribution>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology;
     dcat:distribution <https://www.purl.org/SomeOntology.owl>, <https://www.purl.org/SomeOntology.json>, <https://www.purl.org/SomeOntology.ttl> .
```

Alternative properties:

* <https://schema.org/distribution>
* <http://purl.org/dc/terms/hasFormat>
* <http://purl.org/dc/terms/isFormatOf>
* <https://schema.org/associatedMedia>
* <https://schema.org/encoding>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.12 Application example

How to use an ontology is often helpfully demonstrated by application examples and visualizations that give a glimpse about how the ontology can be used to structure actual data. If you have such application examples, these might be better found, if you link to them from the ontology. These application examples could be part of the ontology documentation, formal serializations applying the ontology or even technical applications that make use of the ontology.

Recommended property: <https://vocab.org/vann/example>

Example (text/turtle):

```Turtle
<http://www.w3.org/ns/dcat> rdf:type owl:Ontology ;
    vann:example <https://www.w3.org/TR/vocab-dcat-2/#collection-of-examples> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.13 Related resource(s)

Resources related to the ontology could be publications discussing the ontology, applications of the ontology or mapping files (see also section [5.17 Alignments/ mappings](#517-alignments-mappings)). If any such resources exist, you should mention them in the ontology. You may also point to other related resources, for example resources that are cited or were otherwise used to inform the ontology. We recommend using a permanent identifier, such as a DOI, of the referenced resource.

Recommended property: <http://purl.org/dc/terms/references>

Example:

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:references <http://doi.org/10.00000/some0.ontolo> .
```

Alternative properties:

* <https://schema.org/citation>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.14 Citation suggestion

You could give information on how you would like others to cite your ontologies. You may even provide structured metadata ready for import into citation management tools like Bibtex etc. Currently, there is no citation standard considering the citation of ontologies. We therefore recommend to provide at least the creators, the year of publication, the ontology title and to give the versionIRI as the access URL. In addition, you could also provide references to citable publications (cf. section [4.13 Related resources](#413-related-resources)).

Recommended property: <http://purl.org/dc/terms/bibliographicCitation>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:bibliographicCitation "Last name, first name; last name, first name et al. (YYYY): Ontology title. URL: https://w3id.org/SomeOntology/1.1.6 (last accessed: DD.MM.YYYY)"^^@en .
```

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology;
    dcterms:bibliographicCitation "@misc{SomeOntology, title = \"Some Ontology\", author = \"Last name, first name and Last name, first name\", url = \"https://w3id.org/SomeOntology/1.1.6\",year = \"YYYY\",}"^^xsd:string .
```

Alternative properties: n/a

SHACL validation rules: n/a

### 4.15 Ontology sources (derived from)

You should specify whether and from which other ontologies your ontology has been derived. The reference should be made by an owl:versionIRI of the ontology from which the current ontology has been derived.

Recommended property: <http://purl.org/pav/derivedFrom>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology;
    pav:derivedFrom <https://www.purl.org/SomeOtherOntology> .
```

Alternative properties:

* <http://www.w3.org/ns/prov#wasDerivedFrom>
* <https://schema.org/isBasedOn>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 4.16 Ontology root classes

You should explicitly declare the ontology's preferred root classes. Display tools like the [TIB Terminology Service][TIB TS] and other OLS-based services [[9]](#source9), [[10]](#source10) can pick specific, user-defined classes for rendering the ontology class hierarchy. This is especially helpful, when an ontology imports a lot of classes from other ontologies. The repsective classes need to be provided via their identifier.

Recommended property: <http://purl.obolibrary.org/obo/IAO_0000700>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    obo:IAO_0000700 <https://www.purl.org/SomeOntology/class12345654544545> .
```

Alternative properties:

* <http://rdfs.org/ns/void#rootResource>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

<div style="page-break-after: always;"></div>

## 5 Optional metadata

The metadata of an ontology can contain much more information than what has been suggested in sections [3 Mandatory metadata](#3-mandatory-metadata) and [4 Recommended metadata](#4-recommended-metadata) so far. Perhaps, you will also find the following categories useful or informative enough to include them into your metadata.

At [TIB Terminology Service][TIB TS] all additional metadata will be displayed on the ontology landing page if available.

### 5.1 Ontology description

If you want to provide more information about the ontology than the few characters that fit into the [ontology abstract](#37-ontology-abstract), you may also provide a longer descriptive text. In a longer description you may, for example, provide more information about how and why the ontology was created, where it is used, how it will be updated and the like. For extensive discussions about further aspects of the ontology (e.g. ontology creation, ontology use, ontology structure, etc.) we recommend the publication of a detailed documentation (cf. [3.9 Ontology documentation](#39-ontology-documentation)) or traditional academic article (cf. [4.13 Related resources](#413-related-resources)), instead of an ontology description.

Recommended property: <https://schema.org/description>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology; 
    schema:description "Free text describing the ontology and how it came to be. Basically everything you might want to add and which does not fit into the abstract."@en .
```

Alternative properties:

* <http://purl.org/dc/terms/description>
* <http://purl.org/dc/elements/1.1/description>

SHACL validation rules:

* `sh:datatype rdf:langString`
* `sh:nodeKind sh:Literal`
* `sh:uniqueLang true`

### 5.2 Alternative ontology title

An alternative title for the ontology may provided, for example a former working title the ontology has been known by.

Recommended property: <http://purl.org/dc/terms/alternative>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:alternative "My Ontology"@en .
```

Alternative properties:

* <https://schema.org/alternateName>
* <https://schema.org/alternativeHeadline>

SHACL validation rules:

* `sh:datatype rdf:langString`

### 5.3 Alternative ontology prefix/ acronym

An alternative prefix for the ontology.

Recommended property: <http://identifiers.org/idot/alternatePrefix>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:Type owl:Ontology ;
    idot:alternatePrefix "mo"^^xsd:string .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:datatype xsd:string`

### 5.4 Related version/ version history

When ontologies are developed on collaborative development platforms with version management software like [GitLab.com][gitlab] or [GitHub.com][github], it is relatively easy to maintain and keep all development and release versions of an ontology. Ontologies may therefore have multiple resolvable version IRIs. The different versions can relate to each other in different ways as discussed in the following sections.

#### 5.4.1 Prior ontology version

An ontology may point back to one or more versions that were valid before the current version.

Recommended property: <http://www.w3.org/2002/07/owl#priorVersion>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    owl:priorVersion <https://www.purl.org/SomeOntology/1.1.6> .
```

Alternative properties:

* <http://www.w3.org/ns/adms#prev>
* <http://purl.org/pav/previousVersion>
* <http://www.w3.org/ns/prov#wasRevisionOf>
* <http://purl.org/dc/terms/replaces>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

#### 5.4.2 Related ontology version

A related resource of which the described resource is a version, edition, or adaptation. The contents of related versions of an ontology are not identical.

Recommended property: <http://purl.org/dc/terms/hasVersion>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:hasVersion <https://www.purl.org/SomeOntology/1.1.6> .
```

Alternative properties:

* <http://purl.org/pav/hasCurrentVersion>
* <https://schema.org/version>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

#### 5.4.3 Compatible ontology version

For application developers and other users, it may be useful to know whether a new version of your ontology is backward compatible with an older version of your ontology.

Recommended property: <http://www.w3.org/2002/07/owl#backwardCompatibleWith>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    owl:versionIRI <https://www.purl.org/SomeOntology/1.1.7> ;
    owl:backwardCompatibleWith <https://www.purl.org/SomeOntology/1.1.6> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:nodeKind sh:IRI`

#### 5.4.4 Incompatible ontology version

For application developers and other users, it may be useful to know whether a new version of your ontology is incompatible with an older version of your ontology.

Recommended property: <http://www.w3.org/2002/07/owl#incompatibleWith>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    owl:versionIRI <https://www.purl.org/SomeOntology/1.1.7> ;
    owl:incompatibleWith <https://www.purl.org/SomeOntology/1.1.6> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 5.5 Social media

If you toot about or otherwise promote your ontology on social media, it might be interesting for users to see on which platforms you are having accounts to follow your updates.

Recommended property: <http://xmlns.com/foaf/0.1/holdsAccount>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology/1.1.7> rdf:type owl:Ontology ;
    foaf:holdsAccount "myOnto@ontology.social"^^xsd:string .
```

Alternative properties: n/a

SHACL validation rules: n/a

### 5.6 KOS type

You may want to additionally classify your ontology with a controlled value from the NKOS type vocabulary [[11]](#source11).

Recommended property: <http://purl.org/dc/terms/type>

Recommended controlled vocabulary: <https://nkos.dublincore.org/nkostype/nkostype.rdf>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology/1.1.7> rdf:type owl:Ontology ;
    dcterms:type <http://w3id.org/nkos/nkostype#ontology> .
```

Alternative properties: n/a

SHACL validation rules:

* value must be from a defined list
* `sh:maxCount 1`
* `sh:nodeKind sh:IRI`

### 5.7 Example ontology identifier

Give an example for identifiers used in your ontology.

Recommended property: <http://identifiers.org/idot/exampleIdentifier>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    idot:exampleIdentifier <https://www.purl.org/SomeOntology/1234-XY> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 5.8 Ontology identifier pattern

Identifiers for ontology classes, properties and individuals usually follow one specific pattern that can be summarized with a regular expression. In registries like [Bioregistry][Bioregistries] this is usually provided as part of the ontology metadata.

Recommended property: <http://identifiers.org/idot/identifierPattern>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    idot:identifierPattern "^\\d{4}-[A-Z]{2}$"^^xsd:string .
```

Alternative properties:

* <https://bioregistry.io/schema/#0000008>

SHACL validation rules:

* `sh:datatype xsd:string`
* `sh:maxCount 1`

### 5.9 Ontology homepage

The official homepage of your ontology. This is not necessarily the documentation website, but could be a general info page, which may also include documentation about the ontology.

Recommended property: <http://xmlns.com/foaf/0.1/homepage>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology;
    foaf:homepage <https://www.example.com/SomeOntologyInfo> .
```

Alternative properties:

* <http://xmlns.com/foaf/0.1/page>

SHACL validation rules:

* `sh:maxCount 1`
* `sh:nodeKind sh:IRI`

### 5.10 Ontology publisher

The official publisher of the ontology. This might be the institution you are affiliated to. We recommend to refer to the institution via PIDs (e.g. [ROR][ror], [ISNI][isni], [GND][gnd] ID).

Recommended property: <http://purl.org/dc/terms/publisher>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:publisher <https://isni.org/isni/0000000121746694> .
```

Alternative properties:

* <http://purl.org/dc/elements/1.1/publisher>
* <https://schema.org/publisher>

SHACL validation rules:

* `sh:nodeKind sh:IRI`
* `sh:pattern "https://d-nb.info/gnd/(|(1[012]?[0-9]{7}[0-9X]|[47][0-9]{6}-[0-9]|[1-9][0-9]{0,7}-[0-9X]|3[0-9]{7}[0-9X]))$"`
* `sh:pattern "https://isni.org/isni/[0]{4}[0-9]{4}[0-9]{4}[0-9]{3}[0-9X]"`
* `sh:pattern "https://ror.org/([a-z0-9]{9})"`

### 5.11 Ontology comments

Any comments you would like to make about your ontology.

Recommended property: <http://www.w3.org/2000/01/rdf-schema#comment>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    rdfs:comment "SomeOntology does not actually exist."@en .
```

Alternative properties:

* <https://schema.org/comment>

SHACL validation rules:

* `sh:datatype rdf:langString`

### 5.12 Example ontology class

You could provide an example class that is representative for the entities described in the ontology, for example demonstrating typical term annotations, editorial notes or axiomatic statements, deprecation notes etc.

Recommended property: <http://rdfs.org/ns/void#exampleResource>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    void:exampleResource <https://www.purl.org/SomeClass> .
```

Alternative properties:

* <http://www.w3.org/2004/02/skos/core#example>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 5.13 Ontology mailing list

Communication about the ontology may take place over a mailing list, e.g. regarding updates. If this is your way to communicate, the info should be part of your ontology.

Recommended property: <http://usefulinc.com/ns/doap#mailing-list>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    doap:mailing-list <someontology@list.de> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:maxCount 1`

### 5.14 Ontology logo/ depiction/ related visualizations

Links to official ontology logo or other visualizations/ diagrams of ontology elements online, e.g. WebVOWL visualizations and other graph views.

Recommended property: <http://xmlns.com/foaf/0.1/logo>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    foaf:logo <https://www.example.com/MyOntoLogo.jpg>
```

Alternative properties:

* <https://schema.org/logo>
* <http://xmlns.com/foaf/0.1/depiction>
* <https://w3id.org/mod#depiction>
* <https://schema.org/image>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 5.15 Related identifiers

If your ontology has been published at an archive, you may want to declare these related identifiers in the ontology metadata.

Recommended property: <http://purl.org/dc/terms/identifier>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:identifier <https://doi.org/10.5281/zenodo.0000000> .
```

Alternative properties:

* <http://purl.org/ontology/bibo/doi>
* <https://schema.org/identifier>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

### 5.16 Development environment

The software that was used to create the ontology.

Recommended property: <http://purl.org/pav/createdWith>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    pav:createdWith "Protégé 4.8.8"^^xsd:string .
```

Alternative properties:

* <https://w3id.org/mod#createdWith>

SHACL validation rules: n/a

### 5.17 Alignments/ mappings

#### 5.17.1 Aligned resources

The ontology may indicate to which other resource(s) it has been aligned or contains equivalences to.

Recommended property: <https://w3id.org/mod#hasEquivalencesWith>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    mod:hasEquivalencesWith <https://www.purl.org/SomeOtherOntology> .
```

Alternative properties:

* <http://w3id.org/nkos#alignedWith>

SHACL validation rules:

* `sh:nodeKind sh:IRI`

#### 5.17.2 Alignment files/ Mapping files

Alignments and mappings may not be included in the ontology document itself, but in a related resource (e.g. when following the SSSOM paradigm [[12]](#source12)). Accordingly, we recommend to treat mapping sets like related resources. The mapping set should be referenced via a PID or a version IRI.

Recommended property: <http://purl.org/dc/terms/references>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:references <https://www.purl.org/SomeOntology/MappingSet1>.
```

Alternative properties: n/a

SHACL validation rules:

* `sh:nodeKInd sh:IRI`

### 5.18 Competency Questions

Which competency questions does the ontology address? For which use case was it developed?

Recommended property: <https://w3id.org/mod#competencyQuestion>

Example 1 (text/turtle)

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    mod:competencyQuestion "Who developed an ontology?"@en .
```

Example 2 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    mod:competencyQuestion <https://www.example.com/SomeOntologyInfo/Questions#Q1>
```

Alternative properties: n/a

SHACL validation rules:

* `sh:xone ([sh:nodeKind sh:IRI ;] [sh:datatype rdf:langString ;])`

### 5.19 Applied methodology

A name or description of the steps taken to develop the ontology. This should describe the overall organisation of the ontology development process.

Recommended property: <http://omv.ontoware.org/2005/05/ontology#usedOntologyEngineeringMethodology>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    omv:usedOntologyEngineeringMethodology "Methontology" .
```

Alternative properties: n/a

SHACL validation rules: n/a

### 5.20 Preferred ontology namespace

The preferred namespace URI of an ontology is the URI which is to be used when referencing its terms.

Recommended property: <http://purl.org/vocab/vann/preferredNamespaceUri>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    vann:preferredNamespaceUri <https://w3id/Example/SomeOntology> .
```

Alternative properties: n/a

SHACL validation rules:

* `sh:maxCount 1`
* `sh:nodeKind sh:IRI`

### 5.21 Ontology issue date

The date the ontology was officially published.

Recommended property: <http://purl.org/dc/terms/issued>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:issued "2023-11-21"^^xsd:dateTime .
```

Alternative properties:

* <https://schema.org/dateIssued>
* <https://schema.org/datePublished>

SHACL validation rules:

* `sh:datatype xsd:dateTime`
* `sh:maxCount 1`

### 5.22 Modification date

Since ontologies are updated over time, it would be helpful to provide the date when the ontology has been last modified.

Recommended property: <http://purl.org/dc/terms/modified>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    dcterms:modified "2020-11-19T00:00:00"^^xsd:dateTime .
```

Alternative properties:

* <https://schema.org/dateModified>
* <http://purl.org/pav/curatedOn>
* <http://purl.org/pav/lastUpdateOn>

SHACL validation rules:

* `sh:datatype xsd:dateTime`
* `sh:maxCount 1`

### 5.23 Textual version information

Some ontologies make use of semantic versioning and employ strings like 1.0.0 as a tag to distinguish one version of their ontology from a successor. Others employ the modification date, e.g. 2022-12-21. If you use such textual version information but do not use/have a Version URI, then we strongly recommend to also mint a version URI in which you use the textual version information as variable.

Recommended property: <http://www.w3.org/2002/07/owl#versionInfo>

Example 1 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    owl:versionInfo "2023-01-01"^^xsd:string .
```

Example 2 (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    owl:versionInfo "1.0.0"^^xsd:string .
```

Alternative properties:

* <http://purl.org/pav/version>

SHACL validation rules:

* `sh:datatype xsd:string`
* `sh:maxCount 1`

### 5.24 Version notes

Version information may also be accompanied by a description about changes between one version of the ontology and its predecessor.

There are several ways for an automatic generation of change notes. When using GitHub and properly atomic PRs for the implementation of each change, you could copy the notes that are created when preparing a release based on tags, which will list all the PRs that have been merged since the last tag. Another approach could be to use the output of the ROBOT diff command.

Recommended property: <http://www.w3.org/ns/adms#versionNotes>

Example (text/turtle):

```Turtle
<https://www.purl.org/SomeOntology> rdf:type owl:Ontology ;
    adms:versionNotes "Changes from 2000-01-12: add annotation properties: familyName [...] "@en .
```

Alternative properties:

* <https://vocab.org/vann/changes>

SHACL validation rules:

* `sh:datatype rdf:langString`
* `sh:nodeKind sh:Literal`

<div style="page-break-after: always;"></div>

## 6 Tabular overview

| section | metadatum                                        | Preferred property                                                            | Mandatory | Recommended | Optional | Cardinality |
|---------|--------------------------------------------------|-------------------------------------------------------------------------------|-----------|-------------|----------|-------------|
| 3.1     | Title                                            | <http://purl.org/dc/terms/title>                                              | x         |             |          | 1…*         |
| 3.2     | Preferred ontology prefix/ acronym               | <http://purl.org/vocab/vann/preferredNamespacePrefix>                         | x         |             |          | 1           |
| 3.3     | License                                          | <http://purl.org/dc/terms/license>                                            | x         |             |          | 1           |
| 3.4     | Creator                                          | <http://purl.org/dc/terms/creator>                                            | x         |             |          | 1…*         |
| 3.5     | Version IRI                                      | <http://www.w3.org/2002/07/owl#versionIRI>                                    | x         |             |          | 1           |
| 3.6     | Creation date                                    | <http://purl.org/dc/terms/created>                                            | x         |             |          | 1           |
| 3.7     | Abstract                                         | <http://purl.org/dc/terms/abstract>                                           | x         |             |          | 1…*         |
| 3.8     | Issue tracker                                    | <http://usefulinc.com/ns/doap#bug-database>                                   | x         |             |          | 1           |
| 3.9     | Documentation                                    | <http://www.loc.gov/premis/rdf/v3/documentation>                              | x         |             |          | 1           |
| 4.1     | Contributor(s)                                   | <http://purl.org/dc/terms/contributor>                                        |           | x           |          | 0…*         |
| 4.2     | Funder                                           | <https://schema.org/funder>                                                   |           | x           |          | 0…*         |
| 4.3     | Funding (grant)                                  | <https://schema.org/funding>                                                  |           | x           |          | 0…*         |
| 4.4     | Audience description                             | <http://usefulinc.com/ns/doap#audience>                                       |           | x           |          | 0...1       |
| 4.5     | Subject(s)                                       | <http://purl.org/dc/terms/subject>                                            |           | x           |          | 0…*         |
| 4.6     | Annotation language(s)                           | <http://purl.org/dc/terms/language>                                           |           | x           |          | 0…*         |
| 4.7     | Applied logical framework                        | <https://w3id.org/mod#hasFormalityLevel>                                      |           | x           |          | 0...1       |
| 4.8     | Serialization/ file format                       | <http://omv.ontoware.org/2005/05/ontology#hasOntologySyntax>                  |           | x           |          | 0...1       |
| 4.9     | Status                                           | <http://purl.org/ontology/bibo/status>                                        |           | x           |          | 0...1       |
| 4.10    | Code repository                                  | <http://usefulinc.com/ns/doap#repository>                                     |           | x           |          | 0...1       |
| 4.11    | Distributions/ products                          | <http://www.w3.org/ns/dcat#distribution>                                      |           | x           |          | 0…*         |
| 4.12    | Application example                              | <https://vocab.org/vann/example>                                              |           | x           |          | 0…*         |
| 4.13    | Related resource(s)                              | <http://purl.org/dc/terms/references>                                         |           | x           |          | 0…*         |
| 4.14    | Citation suggestion                              | <http://purl.org/dc/terms/bibliographicCitation>                              |           | x           |          | 0…*         |
| 4.15    | Ontology sources (derived from)                  | <http://purl.org/pav/derivedFrom>                                             |           | x           |          | 0…*         |
| 4.16    | Root classes                                     | <http://purl.obolibrary.org/obo/IAO_0000700>                                  |           | x           |          | 0…*         |
| 5.1     | Description                                      | <https://schema.org/description>                                              |           |             | x        | 0…*         |
| 5.2     | Alternative ontology title                       | <http://purl.org/dc/terms/alternative>                                        |           |             | x        | 0…*         |
| 5.3     | Alternative ontology prefix/ acronym             | <http://identifiers.org/idot/alternatePrefix>                                 |           |             | x        | 0…*         |
| 5.4.1   | Prior ontology version                           | <http://www.w3.org/2002/07/owl#priorVersion>                                  |           |             | x        | 0…*         |
| 5.4.2   | Related ontology version                         | <http://purl.org/dc/terms/hasVersion>                                         |           |             | x        | 0…*         |
| 5.4.3   | Compatible ontology version                      | <http://www.w3.org/2002/07/owl#backwardCompatibleWith>                        |           |             | x        | 0…*         |
| 5.4.4   | Incompatible ontology version                    | <http://www.w3.org/2002/07/owl#incompatibleWith>                              |           |             | x        | 0…*         |
| 5.5     | Social media                                     | <http://xmlns.com/foaf/0.1/holdsAccount>                                      |           |             | x        | 0…*         |
| 5.6     | KOS type                                         | <http://purl.org/dc/terms/type>                                               |           |             | x        | 0…1         |
| 5.7     | Example ontology identifier                      | <http://identifiers.org/idot/exampleIdentifier>                                    |           |             | x        | 0…*         |
| 5.8     | Ontology identifier pattern                      | <http://identifiers.org/idot/identifierPattern>                                    |           |             | x        | 0…1         |
| 5.9     | Ontology homepage                                | <http://xmlns.com/foaf/0.1/homepage>                                          |           |             | x        | 0…1         |
| 5.10    | Publisher                                        | <http://purl.org/dc/terms/publisher>                                          |           |             | x        | 0…*         |
| 5.11    | Ontology comments                                | <http://www.w3.org/2000/01/rdf-schema#comment>                                |           |             | x        | 0…*         |
| 5.12    | Example ontology class                           | <http://rdfs.org/ns/void#exampleResource>                                     |           |             | x        | 0…*         |
| 5.13    | Ontology mailing list                            | <http://usefulinc.com/ns/doap#mailing-list>                                   |           |             | x        | 0…1         |
| 5.14    | Ontology logo/ depiction/ related visualizations | <http://xmlns.com/foaf/0.1/logo>                                              |           |             | x        | 0…*         |
| 5.15    | Related identifiers                              | <http://purl.org/dc/terms/identifier>                                         |           |             | x        | 0…*         |
| 5.16    | Development environment                          | <http://purl.org/pav/createdWith>                                             |           |             | x        | 0…*         |
| 5.17.1  | Aligned resources                                | <https://w3id.org/mod#hasEquivalencesWith>                                    |           |             | x        | 0…*         |
| 5.17.2  | Alignment files/ mapping files                   | <http://purl.org/dc/terms/references>                                         |           |             | x        | 0…*         |
| 5.18    | Competency questions                             | <https://w3id.org/mod#competencyQuestion>                                     |           |             | x        | 0…*         |
| 5.19    | Applied methodology                              | [<http://omv.ontoware.org/2005/05/ontology#<br>usedOntologyEngineeringMethodology>](http://omv.ontoware.org/2005/05/ontology#usedOntologyEngineeringMethodology) |           |             | x        | 0…*         |
| 5.20    | Preferred ontology namespace                     | <http://purl.org/vocab/vann/preferredNamespaceUri>                            |           |             | x        | 0…1         |
| 5.21    | Ontology issue date                              | <http://purl.org/dc/terms/issued>                                             |           |             | x        | 0…1         |
| 5.22    | Modification date                                | <http://purl.org/dc/terms/modified>                                           |           |             | x        | 0…1         |
| 5.23    | Textual version information                      | <http://www.w3.org/2002/07/owl#versionInfo>                                   |           |             | x        | 0…1         |
| 5.24    | Version notes                                    | <http://www.w3.org/ns/adms#versionNotes>                                      |           |             | x        | 0…*         |

<div style="page-break-after: always;"></div>

## 7 Relations to related work

The following table shows the relation of the recommendations in this guide to related works. If these works recommend the same metadatum for an ontology, the corresponding cell will be marked as *true*, if the metadatum could not be identified in the source, the corresponding cell will be marked as *false*.

| section | metadatum                                        | [[13]](#source13) | [[14]](#source14) | [[15]](#source15) | [[16]](#source16) | [[17]](#source17) | [[18]](#source18) | [[19]](#source19) | [[20]](#source20) | [[21]](#source21) | [[22]](#source22) | [[23]](#source23) |
|---------|--------------------------------------------------|-------------------|-------------------|-------------------|-------------------|-------------------|-------------------|-------------------|-------------------|-------------------|-------------------|-------------------|
| 3.1     | Title                                            | true              | true              | true              | true              | true              | true              | true              | false             | false             | true              | true              |
| 3.2     | Preferred ontology prefix/ acronym               | true              | true              | true              | false             | true              | true              | true              | false             | false             | true              | false             |
| 3.3     | License                                          | true              | true              | true              | true              | true              | true              | true              | true              | true              | true              | true              |
| 3.4     | Creator                                          | true              | true              | true              | true              | true              | true              | true              | true              | true              | false             | true              |
| 3.5     | Version IRI                                      | false             | false             | false             | false             | true              | true              | true              | true              | true              | false             | true              |
| 3.6     | Creation date                                    | true              | true              | false             | false             | true              | true              | true              | true              | true              | false             | true              |
| 3.7     | Abstract                                         | false             | true              | false             | true              | true              | true              | true              | false             | false             | true              | true              |
| 3.8     | Issue tracker                                    | true              | true              | false             | true              | false             | false             | true              | false             | false             | false             | true              |
| 3.9     | Documentation                                    | false             | false             | false             | false             | false             | false             | false             | false             | true              | false             | false             |
| 4.1     | Contributor(s)                                   | false             | true              | true              | true              | true              | true              | true              | true              | false             | false             | true              |
| 4.2     | Funder                                           | true              | true              | false             | false             | true              | false             | true              | false             | false             | false             | true              |
| 4.3     | Funding (grant)                                  | false             | false             | false             | false             | true              | false             | false             | false             | false             | false             | true              |
| 4.4     | Audience description                             | true              | true              | false             | true              | false             | false             | true              | false             | false             | false             | true              |
| 4.5     | Subject(s)                                       | true              | true              | false             | true              | false             | false             | true              | false             | true              | true              | true              |
| 4.6     | Annotation language(s)                           | true              | true              | false             | false             | false             | false             | true              | false             | false             | false             | true              |
| 4.7     | Applied logical framework                        | false             | true              | false             | true              | false             | false             | true              | false             | false             | false             | false             |
| 4.8     | Serialization/ file format                       | true              | true              | false             | false             | false             | false             | true              | false             | false             | false             | true              |
| 4.9     | Status                                           | true              | false             | false             | true              | true              | true              | true              | true              | true              | true              | true              |
| 4.10    | Code repository                                  | false             | true              | false             | true              | false             | false             | true              | false             | false             | true              | false             |
| 4.11    | Distributions/ products                          | true              | true              | false             | false             | false             | false             | true              | false             | true              | false             | true              |
| 4.12    | Application example                              | false             | true              | false             | true              | false             | false             | true              | false             | false             | false             | false             |
| 4.13    | Related resource(s)                              | true              | true              | false             | false             | true              | true              | true              | false             | true              | true              | true              |
| 4.14    | Citation suggestion                              | false             | true              | false             | false             | true              | true              | true              | true              | false             | false             | true              |
| 4.15    | Ontology sources (derived from)                  | true              | true              | false             | true              | true              | true              | true              | true              | true              | false             | true              |
| 4.16    | Root classes                                     | false             | true              | false             | false             | false             | false             | true              | false             | false             | false             | false             |
| 5.1     | Description                                      | true              | true              | true              | true              | true              | true              | true              | false             | true              | true              | true              |
| 5.2     | Alternative ontology title                       | false             | true              | false             | false             | false             | false             | true              | false             | false             | false             | true              |
| 5.3     | Alternative ontology prefix/ acronym             | true              | true              | false             | false             | false             | false             | false             | false             | false             | true              | false             |
| 5.4.1   | Prior ontology version                           | false             | true              | false             | false             | true              | true              | true              | true              | true              | false             | false             |
| 5.4.2   | Related ontology version                         | false             | true              | false             | false             | false             | false             | true              | false             | false             | false             | false             |
| 5.4.3   | Compatible ontology version                      | false             | false             | false             | false             | true              | true              | true              | true              | false             | false             | false             |
| 5.4.4   | Incompatible ontology version                    | false             | false             | false             | false             | true              | true              | true              | true              | false             | false             | false             |
| 5.5     | Social media                                     | true              | false             | false             | false             | false             | false             | false             | false             | false             | true              | false             |
| 5.6     | KOS type                                         | false             | false             | false             | false             | false             | false             | false             | false             | false             | false             | true              |
| 5.7     | Example ontology identifier                      | true              | true              | false             | false             | false             | false             | true              | false             | false             | true              | false             |
| 5.8     | Ontology identifier pattern                      | true              | true              | false             | true              | false             | false             | true              | false             | false             | true              | false             |
| 5.9     | Ontology homepage                                | true              | true              | false             | false             | false             | false             | true              | false             | false             | true              | false             |
| 5.10    | Publisher                                        | true              | true              | true              | false             | true              | true              | true              | false             | false             | false             | true              |
| 5.11    | Ontology comments                                | true              | true              | true              | false             | false             | false             | true              | false             | false             | true              | false             |
| 5.12    | Example ontology class                           | true              | true              | false             | false             | true              | false             | true              | false             | false             | false             | true              |
| 5.13    | Ontology mailing list                            | true              | true              | false             | true              | false             | false             | true              | false             | false             | false             | false             |
| 5.14    | Ontology logo/ depiction/ related visualizations | true              | true              | false             | true              | true              | true              | true              | false             | false             | true              | false             |
| 5.15    | Related identifiers                              | true              | true              | false             | false             | true              | true              | true              | false             | false             | true              | true              |
| 5.16    | Development environment                          | true              | true              | false             | true              | false             | true              | true              | false             | false             | false             | false             |
| 5.17.1  | Aligned resources                                | false             | true              | false             | false             | false             | false             | true              | false             | true              | false             | false             |
| 5.17.2  | Alignment files/ mapping files                   | false             | false             | false             | false             | false             | false             | false             | false             | true              | false             | false             |
| 5.18    | Competency questions                             | false             | true              | false             | true              | false             | false             | true              | false             | false             | false             | false             |
| 5.19    | Applied methodology                              | true              | true              | false             | true              | false             | false             | true              | false             | false             | false             | false             |
| 5.20    | Preferred ontology namespace                     | true              | true              | true              | false             | true              | true              | true              | false             | false             | false             | true              |
| 5.21    | Ontology issue date                              | false             | true              | true              | false             | true              | true              | false             | false             | false             | false             | false             |
| 5.22    | Modification date                                | false             | true              | true              | false             | true              | true              | true              | true              | false             | false             | true              |
| 5.23    | Textual version information                      | false             | true              | true              | false             | true              | true              | true              | true              | false             | true              | true              |
| 5.24    | Version notes                                    | false             | true              | true              | false             | false             | true              | false             | true              | false             | false             | false             |

## 8 Sources

1. <a name="source1"></a> GO FAIR (n/a): FAIR Principles. URL: <https://www.go-fair.org/fair-principles/> (last access: 28 April 2023).

2. <a name="source2"></a> Yann Le Franc, Luiz Bonino, Hanna Koivula, Jessica Parland-von Essen, & Robert Pergl (2022): D2.8 FAIR Semantics Recommendations Third Iteration (V1.0). Zenodo. URL: <https://doi.org/10.5281/zenodo.6675295> (last access: 04 April 2024).

3. <a name="source3"></a> OBO Foundry (n/a): Principle: Versioning (principle 4). URL: <http://obofoundry.org/principles/fp-004-versioning.html> (last acchess: 04 April 2024).

4. <a name="source4"></a> Garijo, Daniel (2017): WIDOCO: a wizard for documenting ontologies. In: International Semantic Web Conference (Proceedings), 94-102. Springer, Cham. DOI: 10.1007/978-3-319-68204-4_9. URL: <http://dgarijo.com/papers/widoco-iswc2017.pdf> (last access: 04 April 2024).

5. <a name="source5"></a> Daniel Garijo et al. (2023): WIzard for DOCumenting Ontologies (WIDOCO) - Code Repository. URL: <https://github.com/dgarijo/Widoco/tree/v1.4.21> (last access: 04 April 2024).

6. <a name="source6"></a> Internet Assigned Numbers Authority (2024): Media Types. URL <https://www.iana.org/assignments/media-types/media-types.xhtml> (last access: 04 April 2024).

7. <a name="source7"></a> World Wide Web Consortium (W3C) (2015): Unique URIs for File Formats. URL: <https://www.w3.org/ns/formats/> (last access: 04 April 2024).

8. <a name="source8"></a> OBO Foundry (n/a): Ontology status. URL: <https://obofoundry.org/docs/OntologyStatus.html> (last access: 04 April 2024).

9. <a name="source9"></a> Samples, Phenotypes and Ontologies (SPOT) at EMBL-EBI (2022): Ontology Lookup Service (OLS) Version 3 - Code Repository - Release 3.2.5. URL: <https://github.com/EBISPOT/OLS/releases/tag/v3.2.5-main-test> (last access: 04 April 2024).

10. <a name="source10"></a> Samples, Phenotypes and Ontologies (SPOT) at EMBL-EBI (2024): Ontology Lookup Service (OLS) - Version 4 - Code Repository - Latest Release. URL: <https://github.com/EBISPOT/ols4> (last access: 04 April 2024).

11. <a name="source11"></a> Marcia Zeng & Maja Žumer (2019): KOS Type Vocabulary. URL: <https://nkos.dublincore.org/nkos-type.html>, <https://nkos.dublincore.org/nkostype/nkostype.rdf> (last access: 04 April 2024).

12. <a name="source12"></a> Nicolas Matentzoglu et al. (2024): Simple Standard for Sharing Ontological Mappings (SSSOM) - Editors Draft version 0.15.2. URL: <https://github.com/mapping-commons/sssom/tree/0.15.2> (last access: 04 April 2024).

13. <a name="source13"></a> OBO Foundry (2021): Derived registry files - context file for the generation of rdf-based ontology metadata. URL: <http://purl.obolibrary.org/meta/context.jsonld>, <https://github.com/OBOFoundry/OBOFoundry.github.io/blob/5ba7e5db94565691853db7b476637fd303c4fb94/registry/context.jsonld> (last access: 04 April 2024).

14. <a name="source14"></a> Dutta, B., Toulet, A., Emonet, V. and Jonquet, C. (2017): New Generation Metadata vocabulary for Ontology Description and Publication. In E. Garoufallou, S. Virkus, R. Siatri and D. Koutsomiha (eds.): *Communications in Computer and Information Science (CCIS) 755, proceedings of 11th Metadata and Semantics Research Conference (MTSR 2017), November 28 - December 1, 2017, Tallinn, Estonia*. Springer Nature, pp. 173-185. URL: <https://w3id.org/mod/2.0> (last access: 04 April 2024).

15. <a name="source15"></a> Pierre-Yves Vandenbussche & Bernard Vatant (2021): Metadata Recommendations For Linked Open Data Vocabularies - Version 1.1. URL: <https://lov.linkeddata.es/Recommendations_Vocabulary_Design.pdf> (last access: 04 April 2024).

16. <a name="source16"></a> Robert Stevens et al. (2017): MIRO – Minimum Information for Reporting of an Ontology. URL: <https://github.com/owlcs/miro/blob/master/miro.md> (last access: 04 April 2024).

17. <a name="source17"></a> Daniel Garijo & María Poveda-Villalón (2023): A checklist for complete vocabulary metadata - Revision 1.0.2. URL: <https://w3id.org/widoco/bestPractices> (last access: 04 April 2024).

18. <a name="source18"></a> Daniel Garijo & María Poveda-Villalón (2020): Best Practices for Implementing FAIR Vocabularies and Ontologies on the Web. *ArXiv.org.* URL: <https://doi.org/10.48550/arXiv.2003.13084> (last access: 04 April 2024).

19. <a name="source19"></a> E. Amdouni, S. Bouazzouni, C. Jonquet (2022): O'FAIRe: Ontology FAIRness evaluator - FAIR questions. URL: <https://github.com/agroportal/fairness/commit/f5767d417465bcb2602f5400cf921169c5f10a65> (last access: 04 April 2024).

20. <a name="source20"></a> Cox, Simon J. D. et al. (2021): Ten simple rules for making a vocabulary FAIR. *PLOS Computational Biology 17(6)*, pp. 1-15. URL: <https://doi.org/10.1371/journal.pcbi.1009041> (last access: 04 April 2024).

21. <a name="source21"></a> Fuqi Xu et al. (2022): Features of a FAIR vocabulary. In: Katy Wolstencroft et al. (eds.): *Proceedings of the 13th International Conference on Semantic Web Applications and Tools for Health Care and Life Sciences (SWAT4HCLS)* (= CEUR Workshop Proceedings 3127). Aachen, 118-148. URL: <http://ceur-ws.org/Vol-3127/#paper-15> (last access: 04 April 2024).

22. <a name="source22"></a> Charles Tapley Hoyt (2024): Bioregistry JSON Schema. URL (latest): <https://bioregistry.io/schema.json>, URL (v0.10.190): <https://github.com/biopragmatics/bioregistry/blob/v0.10.190/src/bioregistry/schema/schema.json>  (last access: 04 April 2024).

23. <a name="source23"></a> Schema.Org Community Group (n/a): DefinedTermSet. A Schema.org Type. URL: <https://schema.org/DefinedTermSet> (last access: 04 April 2024).

<!-- 24. <a name="source24"></a>  -->

<!-- Reference style links -->

[Bioregistries]: <https://bioregistry.io/registry/> "Hoyt, C. T., et al. (2022) The Unifying the identification of biomedical entities with the Bioregistry. Nature Scientific Data, <https://doi.org/10.1038/s41597-022-01807-3>. Last accessed: 22 April 2024."
[cropusage-agroportal]: <https://agroportal.lirmm.fr/ontologies/CROPUSAGE> "Audience description of Cropusage at AgroPortal. URL: https://agroportal.lirmm.fr/ontologies/CROPUSAGE. Last accessed: 22 April 2024."
[doi]: <https://www.doi.org/> "DOI Foundation Homepage. URL: https://www.doi.org/. Last accessed: 22 April 2024."
[FAIR Principles R1]: <https://www.go-fair.org/fair-principles/r1-metadata-richly-described-plurality-accurate-relevant-attributes/> "FAIR Principles. Principle R1. GO FAIR. URL: <https://www.go-fair.org/fair-principles/>. Last accessed: 28 April 2023."
[github]: <http://GitHub.com> "GitHub.com. Last accessed: 22 April 2024."
[gitlab pages]: <https://docs.gitlab.com/ee/user/project/pages/> "GitLab Documentation: GitLab Pages. URL: https://docs.gitlab.com/ee/user/project/pages/. Last accessed: 22 April 2024."
[gitlab]: <http://GitLab.com> "GitLab.com. Last accessed: 22 April 2024."
[gnd]: <https://explore.gnd.network/> "Gemeinsame Normdatei (GND) - GND Explorer. URL: https://explore.gnd.network/. Last accessed: 22 April 2024."
[isni]: <https://isni.org/> "International Standard Name Identifier Homepage. URL: https://isni.org/. Last accessed: 22 April 2024."
[linsearch]: <https://purl.org/linsearch> "Technische Informationsbibliothek: Fachsystematik LinSearch. URL: https://purl.org/linsearch. Last accessed: 22 April 2024."
[nmrc-tib-ts]: <https://terminology.tib.eu/ts/ontologies/nmrc> "Audience description of NMRC at TIB Terminology Service. URL: https://terminology.tib.eu/ts/ontologies/nmrc. Last accessed: 22 April 2024."
[Open Definition 2.1]: <https://opendefinition.org/od/2.1/en/> "Open Knowledge (n/a): Open Definition. Defining Open in Open Data, Open Content and Open Knowledge. URL: https://opendefinition.org/od/2.1/en/. Last accessed: 22 April 2024."
[Open Definition license list]: <https://opendefinition.org/licenses/> "Open Knowledge (n/a): Open Definition. Defining Open in Open Data, Open Content and Open Knowledge. List of Conformant Licensess. URL: https://opendefinition.org/licenses/. Last accessed: 22 April 2024."
[orcid]: <https://orcid.org/> "Open Researcher and Contributor ID (ORCiD) Homepage. URL: https://orcid.org/. Last accessed: 22 April 2024."
[prefix.cc]: <https://prefix.cc> "Prefix.cc. Namespace Lookup for RDF Developers.URL: https://prefix.cc/. Last accessed: 22 April 2024."
[raid]: <https://raid.org/> "RAiD Research Activity Identifier Service. URL: https://raid.org/. Last accessed: 22 April 2024."
[ror]: <https://ror.org/> "Research Organization Registry Homepage. URL: https://ror.org/. Last accessed: 22 April 2024."
[semver]: <https://semver.org/> "Tom Preston Werner (n/a): Semantic Versioning 2.0.0. URL: https://semver.org/. Last accessed: 22 April 2024."
[shacl-playground]: <https://shacl.org/playground/> "Holger Knublauch (n/a): SHACL Playground. URL: https://shacl.org/playground/. Last accessed: 22 April 2024."
[TIB TS ontology list]: <https://terminology.tib.eu/ts/ontologies> "TIB Terminology Service - Ontologies list. URL: https://terminology.tib.eu/ts/ontologies. Last accessed: 22 April 2024."
[TIB TS]: <https://terminology.tib.eu/ts> "TIB Terminology Service. URL: https://terminology.tib.eu/. Last accessed: 22 April 2024."
[wikidata]: <https://www.wikidata.org/wiki/Wikidata:Main_Page> "Wikidata. URL: https://www.wikidata.org/wiki/Wikidata:Main_Page. Last accessed: 22 April 2024."
<!-- []: <> "tbd" -->