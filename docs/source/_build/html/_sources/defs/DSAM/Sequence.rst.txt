**Computational Definition**

A character string of Residues that represents a biological sequence using the conventional sequence order (5’-to-3’ for nucleic acid sequences, and amino-to-carboxyl for amino acid sequences). IUPAC ambiguity codes are permitted in Sequences.

**Information Model**

A string constrained to match the regular expression ``^[A-Z*\-]*$``, derived from the IUPAC one-letter nucleic acid and amino acid codes.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
      - Description
   *  - type 
      - `CodeableConcept (FHIR) <https://build.fhir.org/datatypes.html#CodeableConcept>`__
      - [1..1]
      - The type of sequence (e.g., DNA, RNA, protein). The value of this attribute should represent a term in an ontology (e.g., Sequence Ontology).
   *  - identifier
      - `Identifier (FHIR) <https://build.fhir.org/datatypes.html#Identifier>`__
      - [0..*]
      - Identifier(s) for the sequence. Note the complex datatype includes attributes to capture both the identifer and the system or namespace that assigned the identifier. Identifiers MUST be unique within a system or namespace.
   *  - name
      - string
      - [0..*]
      - Name(s) for the sequence. Names are intended to be for human-readable purposes only and are not guaranteed to uniquely specify a sequence.
   *  - representation
      - SequenceRepresentation
      - [0..*]
      - Representation(s) of the sequence. All representations for a given sequence MUST resolve to the same literal string.
   *  - features
      - :ref:`LocatedFeature` 
      - [0..*]
      - A list of annotated features on the sequence. This attribute should be used only by Sequence-based structures.
