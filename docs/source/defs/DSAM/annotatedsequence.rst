**Computational Definition**

TBD

**Information Model**

An *annotated sequence* is a sequence with associated annotations (e.g., features). Structurally, the class is simply a container for a Sequence and located features. This class may serve as a generalized parent class that can be specialized to support complex types of annotated sequences (e.g., transcripts).


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
