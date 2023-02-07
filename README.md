# Datenzee RDF Template

This template automates the process of creating RDF from a Knowledge Model to make it more efficient and accurate. To automatically get the RDF from your KM, you need to attach `rdfType` and `rdfRelation` annotations to your questions.

The template considers only `Value Questions` and `List of Items Questions`. Other types of questions will not be taken into account in the output RDF. Each of the questions should have the `rdfType` on which we want to transform the question. To interconnect the `List Of Items Question` with its children, please use the `rdfRelation` annotation.

Here is an example of the Knowledge Model to clarify what the result Knowledge Model should look like. Or you can import the knowledge model ([datenzee_simple-dmp_1.0.0.km](https://raw.githubusercontent.com/datenzee/rdf-template/main/datenzee_simple-dmp_1.0.0.km)) directly to your Data Stewardship Wizard.

**Example KM:**

```
Knowledge Model (annotations: [])
\- My Chapter (annotations: [])
    \- Data Management Plan (type: "List of Items Question", annotations: [ rdfType: "https://w3id.org/dcso/ns/core#DMP"])
        |- Title (type: "Value Question", annotations: [ rdfType: "http://purl.org/dc/terms/title"])
        |- Description (type: "Value Question", annotations: [ rdfType: "http://purl.org/dc/terms/description"])
        \- Dataset (type: "List of Items Question", annotations: [ rdfType: "https://w3id.org/dcso/ns/core#Dataset", rdfRelation: "https://w3id.org/dcso/ns/core#hasDataset"])
            |- Title (type: "Value Question", annotations: [ rdfType: "http://purl.org/dc/terms/title"])
            \- Description (type: "Value Question", annotations: [ rdfType: "http://purl.org/dc/terms/description"])

```

## Changelog

### 1.1.0

- Adjusted to template metamodel version 11 (released in DSW 3.20.0)

### 1.0.0

- Initial version of Datenzee RDF Template

## License

This template is released under Apache-2.0. Read the [LICENSE](https://raw.githubusercontent.com/datenzee/rdf-template/main/LICENSE) file for details.
