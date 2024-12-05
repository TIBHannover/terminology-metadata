# Terminology Metadata Recommendations by TIB

With this repository, *TIB - Leibniz Information Centre for Science and Technology University Library* provides a practical guide for metadata management of ontologies. It gives recommendations on required, recommended and optional metadata for ontologies.

In particular, it addresses ontology engineers who would like to publish their ontologies on the [TIB Terminology Service](https://terminology.tib.eu/ts), the [NFDI4INg Terminology Service](https://terminology.nfdi4ing.de/ts/) or the [NFDI4Chem Terminology Service](https://terminology.nfdi4chem.de/ts/).

An introduction and overview is given in the [Metadata Guide](/MetadataGuide.md).

This repository is archived at Zenodo: <https://www.doi.org/10.5281/zenodo.11103071>

> INFO: This recommendation is still a draft. Approval and discussion by a broader communiuty are required.

## For ontology validation by ontology engineers

In addition to the [MetadataGuide.md](/MetadataGuide.md), we provide SHACL shapes based on these recommendations in [OntoMetadataShape.ttl](/OntoMetadataShape.ttl) which can also be reached via <https://www.purl.org/ontologymetadata/shape>. These shapes can be used in SHACL validators and to check whether an ontology meets the recommendations. For example, the following onlin e SHACL validators are available:

* [SHACL Playground](https://shacl.org/playground/)
* [SHACL Playground by Zazuko](https://shacl-playground.zazuko.com/)
* [SHACL Play!](https://shacl-play.sparna.fr/play/)

They are very fine-grained - each sh:PropertyShape tests a specific set of properties that may occur in an ontology. For each violated constraint, a detailed message adresses how the constraint violation may be fixed. The messages provide examples in Turtle, so that ontology engineers can easily adapt their own code to the recommendation.

See how you can use online validators with our shape:

## For ontology validation at TIB Terminology Service

In [OntoMetadataShape4TS.ttl](/OntoMetadataShape4TS.ttl) we provide a version of the recommendations that is adapted to the Ontology Suggestion Feature at [TIB Terminology Service](https://terminology.tib.eu). The messages are adapted to the context of use and the particular use case: The person suggesting an ontology is not necessarily involved in its development. On TIB Terminology Service, they will be asked to provide metadata of the ontology if these are not present in the ontology, and if known to the user. These users not need to provide the meatdata as code.

## For metadata form generators

In [OntoMetadataShape4Forms.ttl](/OntoMetadataShape4Forms.ttl) you find a version of the shape that is optimized for the [form generator tool by ULB Darmstadt](https://github.com/ULB-Darmstadt/shacl-form). You can try it out on their [live demo instance](https://ulb-darmstadt.github.io/shacl-form/#try-your-own).

The shapes are not as granular as the ones for validation: All constraints are bundled in one shape in order to generate a form, that users can use to enter values. The user input is validated immediately for all criteria and the metadata code is generated. Only the recommended properties will be used to do so: This version of the recommendation does not make use of `sh:alternativePath` constructs, in order to generate valid RDF code with named properties, not anonymous/ blank nodes.

## Further reading and sources

* Arndt, S., Borgelt, H. und Strömert, P. (2023) „FAIR Ontology Metadata - Crucial Information for Understanding, Evaluation, and Application“. 2nd Ontologies4Chem Workshop 2023 (Ontologies4Chem 2023), Zenodo, 12 Oktober. doi: 10.5281/zenodo.10117899.
* see complete [list of sources](/MetadataGuide.md#8-sources) in the Metadata Guide
