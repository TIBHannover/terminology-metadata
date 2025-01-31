# Terminology Metadata Recommendations by TIB

With this repository, *TIB - Leibniz Information Centre for Science and Technology University Library* provides a practical guide for metadata management of ontologies. It gives recommendations on required, recommended and optional metadata for ontologies.

In particular, it addresses ontology engineers who would like to publish their ontologies on the [TIB Terminology Service](https://terminology.tib.eu/ts), the [NFDI4INg Terminology Service](https://terminology.nfdi4ing.de/ts/) or the [NFDI4Chem Terminology Service](https://terminology.nfdi4chem.de/ts/).

An introduction and overview is given in the [Metadata Guide](/MetadataGuide.md).

In addition, we provide SHACL shapes based on these recommendations for three different applications as documented below. The target class of these shapes is owl:Ontology, so that they can only be used to validate entities that declare themselves as an instance of owl:Ontology, and also code generated with these shapes, will declare entities as instances of owl:Ontology.

This repository is archived at Zenodo: <https://www.doi.org/10.5281/zenodo.11103071>

> INFO: This recommendation is still a draft. Approval and discussion by a broader communiuty are required.

## Metadata recommendations in SHACL

### For ontology validation by ontology engineers

In addition to the [MetadataGuide.md](/MetadataGuide.md), we provide SHACL shapes based on these recommendations in [OntoMetadataShape.ttl](/OntoMetadataShape.ttl) which can also be reached via <https://www.purl.org/ontologymetadata/shape>. These shapes can be used in SHACL validators to check whether an ontology meets the recommendations.
They are very fine-grained - each sh:PropertyShape tests a specific set of properties that may occur in an ontology. For each violated constraint, a detailed message adresses how the constraint violation may be fixed. The messages provide examples in Turtle, so that ontology engineers can easily adapt their own code to the recommendation.

For example, the following online SHACL validators are available and have been tested with [OntoMetadataShape.ttl](/OntoMetadataShape.ttl):

* [SHACL Playground](https://shacl.org/playground/)
* [SHACL Playground by Zazuko](https://shacl-playground.zazuko.com/)
* [SHACL Play!](https://shacl-play.sparna.fr/play/validate) (if you are new to SHACL, we recommend this online validator!)

PLEASE NOTE that browser extensions (e.g. Citavi) may interfer when using such validators - they may parse the Turtle code and insert text snippets that make the code unparsable due to syntactic errors. You should switch such extensions off, if you encounter such problems!

See how you can use online validators with our shape:

<https://github.com/user-attachments/assets/c5d6be07-3bfb-44ab-ae65-e3f75b8e883a>

### For ontology validation at TIB Terminology Service

In [OntoMetadataShape4TS.ttl](/OntoMetadataShape4TS.ttl) (also <https://www.purl.org/ontologymetadata/shape4ts>) we provide a version of the recommendations that is adapted to the Ontology Suggestion Feature at [TIB Terminology Service](https://terminology.tib.eu). The messages are adapted to the context of use and the particular use case: The person suggesting an ontology is not necessarily involved in its development. On TIB Terminology Service, they will be asked to provide metadata of the ontology if these are not present in the ontology, and if known to the user. These users are not required to provide the meatdata as code.

See how the shape is used in the suggestion feature:

<https://github.com/user-attachments/assets/847cfd39-0823-4a83-9c8a-0cf3d23d38a7>

### For metadata form generators

In [OntoMetadataShape4Forms.ttl](/OntoMetadataShape4Forms.ttl) (also <https://www.purl.org/ontologymetadata/shape4forms>) you find a version of the shape that is optimized for the [form generator tool by ULB Darmstadt](https://github.com/ULB-Darmstadt/shacl-form). You can try it out on their [live demo instance](https://ulb-darmstadt.github.io/shacl-form/#try-your-own).

The shapes are not as granular as the ones for validation: All constraints are bundled in one shape in order to generate a form, that users can use to enter values. The user input is validated immediately for all criteria and the metadata code is generated. Only the recommended properties will be used to do so: This version of the recommendation does not make use of `sh:alternativePath` constructs, in order to generate valid RDF code with named properties, not anonymous/ blank nodes.

<https://github.com/user-attachments/assets/55cdf44f-5289-4989-9014-5e670fd73418>

## Further reading and sources

* Arndt, S., Borgelt, H. und Strömert, P. (2023) „FAIR Ontology Metadata - Crucial Information for Understanding, Evaluation, and Application“. 2nd Ontologies4Chem Workshop 2023 (Ontologies4Chem 2023), Zenodo, 12 Oktober. doi: 10.5281/zenodo.10117899.
* see complete [list of sources](/MetadataGuide.md#8-sources) in the Metadata Guide
