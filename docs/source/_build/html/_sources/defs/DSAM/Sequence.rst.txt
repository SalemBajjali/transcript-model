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
      - CodeableConcept
      - [1..1]
   *  - identifier
      - Identifier
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