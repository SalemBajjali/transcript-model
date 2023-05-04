**Computational Definition**

TBD

**Information Model**

A structural or functional feature that can be annotated on a Sequence at a defined location (interval). A given feature is not unique to a single Sequence and can be mapped to different locations on different Sequences through *contextualization*.

Examples of Sequence Features include:
 * Gene locus
 * Exon
 * Intron
 * 5' or 3' UTR
 * Transcription start site
 * Translation start or stop sites
 * Coding sequence (CDS)
 * Codon
 * Transcription factor binding site
 * Post-translational modification site
 * Splice donor/acceptor site
 * PolyA site

Sequence Features are first-class entities that can stand on their own as independent entries in knowledge bases and be used as the subject of VA statements.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
      - Description
   *  - identifier
      - `Identifier (FHIR) <https://build.fhir.org/datatypes.html#Identifier>`__
      - [0..*]
      - Identifier(s) for the sequence feature. Note the complex datatype includes attributes to capture both the identifer and the system or namespace that assigned the identifier. Identifiers MUST be unique within a system or namespace.
   *  - name
      - string
      - [0..*]
      - Name(s) for the sequence feature. Names are intended to be for human-readable purposes only and are not guaranteed to uniquely specify a sequence feature.
   *  - type
      - `CodeableConcept (FHIR) <https://build.fhir.org/datatypes.html#CodeableConcept>`__
      - [1..1]
      - The type of feature. The value of this attribute should refer to a term in an ontology (e.g., Sequence Ontology).
   *  - contexts
      - :ref:`SequenceContext`
      - [0..*]
      - A list of sequence contexts for the feature. This attribute should be used only by Feature-based structures.
