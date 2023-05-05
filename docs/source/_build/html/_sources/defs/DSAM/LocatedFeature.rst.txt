**Computational Definition**

TBD

**Information Model**

A mapping between a given sequence feature and its location on a given sequence.

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
      - Description
   *  - feature
      - :ref:`SequenceFeature` 
      - [1..1]
      - The feature at the given location
   *  - location
      - `Location (VRS) <https://vrs.ga4gh.org/en/stable/terms_and_model.html#locations-and-intervals>`__
      - [1..1]
      - The location of the feature
   *  - strand
      - `CodeableConcept (FHIR) <https://build.fhir.org/datatypes.html#CodeableConcept>`__
      - [0..1]
      - An indicator specifying whether the feature is on the forward or reverse strand of a double-stranded sequence. If not set, the feature is assumed to be on the forward strand (by convention). If the sequence is single-stranded and this attribute is set, it must not be set to "reverse".
