**Computational Definition**

TBD

**Information Model**

Conceptually, an *annotated sequence* is a sequence with associated annotations (e.g., features). Structurally, the class is a container for a Sequence and located features (and because of this an Annotated Sequence is a complex object that is neither a Sequence nor a Feature). This class may serve as a generalized parent class that can be specialized to support complex types of annotated sequences (e.g., transcripts).


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
