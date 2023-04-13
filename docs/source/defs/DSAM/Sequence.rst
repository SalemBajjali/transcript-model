**Computational Definition**

A character string of Residues that represents a biological sequence using the conventional sequence order (5'-to-3' for nucleic acid sequences, and amino-to-carboxyl for amino acid sequences). IUPAC ambiguity codes are permitted in Sequences.

**Information Model**

The Sequence class represents the concept of a particular sequence rather than its instantiation in a particular database or serialization. The Sequence class provides convenience attributes to capture human-readable names and identifiers that are associated with a sequence, but the *representation* of the sequence itself (the linear string of residues) is captured using the SequenceRepresentation abstract data type (defined by the `FHIR Molecular Sequence Resource <https://build.fhir.org/branches/cg-im-molseq-work_in_progress/molecularsequence.html>`__, which are similar to the `VRS SequenceExpression classes <https://vrs.ga4gh.org/en/stable/terms_and_model.html#sequence-expression>`__).

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
      - Identifier(s) for the sequence. Identifiers are used for cross-referencing sequence concepts only, not for capturing the sequence itself (which is done with the *representation* attribute). Note the complex datatype includes attributes to capture both the identifer and the system or namespace that assigned the identifier. Identifiers MUST be unique within a system or namespace.
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
