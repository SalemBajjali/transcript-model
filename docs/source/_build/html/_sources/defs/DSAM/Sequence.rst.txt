**Computational Definition**

Summary goes here 

**Information Model**

Summary goes here 

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
   *  - name
      - string
      - [0..*]
   *  - representation
      - SequenceRepresentation
      - [0..*]
   *  - features
      - :ref:`LocatedFeature` 
      - [0..*] 