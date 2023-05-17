**Computational Definition**

TBD

**Information Model**

A *transcript* is a type of annotated sequence. It represents a single-stranded RNA sequence that may contain structural features (e.g., exons) and functional features (e.g., coding region). Because the concept of *transcript* is so widely used, and because the concepts of sequence, exon, and gene are so closely intertwined with it, an explicit model for Transcript was developed.

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
