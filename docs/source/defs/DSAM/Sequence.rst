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
   *  - type 
      - `CodeableConcept (FHIR) <https://build.fhir.org/datatypes.html#CodeableConcept>`__
      - [1..1]
   *  - identifier
      - `Identifier (FHIR) <https://build.fhir.org/datatypes.html#Identifier>`__
      - [0..*]
      - Identifier(s) for the sequence. Note the complex datatype includes attributes to capture both the identifer and the system or namespace that assigned the identifier. Identifiers MUST be unique within a system or namespace.
   *  - name
      - string
      - [0..*]
   *  - representation
      - SequenceRepresentation
      - [0..*]
   *  - features
      - :ref:`LocatedFeature` 
      - [0..*] 