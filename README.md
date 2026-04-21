# Phase 2: Ontology Conceptualization

[cite_start]In this phase, the requirements defined in the Ontology Requirements Specification Document (ORSD) were transformed into a formal conceptual model using the **Chowlk notation**[cite: 47, 351]. 

## 1. Conceptual Diagram
[cite_start]The ontology was designed using the [diagrams.net](https://app.diagrams.net/) tool following the visual syntax required by Chowlk for automatic conversion to OWL[cite: 47, 219].

![Tony Awards Ontology Diagram](./ontology/tony-awards.png)

## 2. Model Description
[cite_start]The conceptualization represents the domain of the **Tony Awards** and is structured around the following pillars[cite: 88, 90]:

* [cite_start]**Classes (Concepts)**: The main entities include `Person`, `Production`, `Ceremony`, `AwardCategory`, and `Theater`[cite: 167, 178].
* **Object Properties (Relationships)**: These define how entities interact, such as:
    * [cite_start]`base:actedIn` (links a Person to a Production)[cite: 401, 421].
    * [cite_start]`base:performedIn` (links a Production to a Theater)[cite: 421, 467].
    * [cite_start]`base:nominatedFor` (links a Production/Person to an AwardCategory)[cite: 401].
* **Datatype Properties (Attributes)**: These describe characteristics of the classes, such as:
    * [cite_start]`base:productionTitle` (xsd:string)[cite: 404, 407].
    * [cite_start]`base:ceremonyYear` (xsd:integer)[cite: 410, 426].
    * [cite_start]`base:isWinner` (xsd:boolean)[cite: 126, 407].

## 3. Formal Constraints & Logic
[cite_start]To ensure the machine-readability and formal structure of the ontology, several OWL constructs were implemented[cite: 88, 103]:

* [cite_start]**Functional Properties**: Attributes like `ceremonyYear` are defined as Functional, meaning each ceremony is associated with exactly one year[cite: 596, 598, 672].
* [cite_start]**Existential Quantifiers (some)**: Used to specify that a Tony-nominated production must be linked to at least one award category[cite: 859, 861].
* [cite_start]**Inverse Properties**: The relationship `performedIn` is defined as the inverse of `hosts` to allow bidirectional navigation between productions and theaters[cite: 534, 535].
* [cite_start]**Disjoint Classes**: Classes like `Person` and `Production` are defined as disjoint, ensuring an individual cannot belong to both classes simultaneously[cite: 265, 267].

## 4. Implementation
[cite_start]The conceptual diagram was converted into a formal ontology file using the [Chowlk Converter](https://chowlk.linkeddata.es/)[cite: 48]. [cite_start]The resulting Turtle file (`.ttl`) contains the TBox (terminological) axioms of the knowledge base[cite: 133, 134].

You can find the implementation file here: [ontology.ttl](./ontology/ontology.ttl)
