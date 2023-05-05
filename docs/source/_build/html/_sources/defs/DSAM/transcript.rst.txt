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
   *  - exons
      - :ref:`LocatedFeature`
      - [0..*]
      - A list of sequence features representing the exons of the transcript.
   *  - codingRegion
      - :ref:`LocatedFeature`
      - [0..*]
      - A list of sequence features representing the coding region of the transcript.
   *  - associatedGenes
      - identifier
      - [0..*]
      - A list of gene(s) associated with the transcript. Note: This structure provides support for fusions, prokaryotic operons, etc, but it does not specify which region(s) or feature(s) within the transcript are associated with a particular gene.
