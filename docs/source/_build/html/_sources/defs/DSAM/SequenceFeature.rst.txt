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
   *  - identifier 
      - `Identifier (FHIR) <https://build.fhir.org/datatypes.html#Identifier>`__
      - [0..*]
   *  - type
      - `CodeableConcept (FHIR) <https://build.fhir.org/datatypes.html#CodeableConcept>`__
      - [1..1]
   *  - name
      - string
      - [0..*]
   *  - contexts
      - :ref:`SequenceContext`
      - [0..*]