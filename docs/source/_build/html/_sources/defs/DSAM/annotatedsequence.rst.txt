**Computational Definition**

**Information Model**

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
      - Description
   *  - sequence
      - :ref:`Sequence`
      - [1..1]
      - The Sequence that is annotated with features.
   *  - features
      - :ref:`LocatedFeature`
      - [0..*]
      - A list of annotated features on the Sequence.
