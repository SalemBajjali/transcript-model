**Computational Definition**

TBD

**Information Model**

The definition of a location on a given sequence. This mapping provides sequence context (*contextualization*) for a parent entity (e.g., a feature).

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
      - The Sequence that provides the context for the mapped location.
   *  - location
      - `Location (VRS) <https://vrs.ga4gh.org/en/stable/terms_and_model.html#locations-and-intervals>`__
      - [1..1]
      - A location that defines a region (interval) on the given Sequence.
   *  - strand
      - `CodeableConcept (FHIR) <https://build.fhir.org/datatypes.html#CodeableConcept>`__
      - [0..1]
      - An indicator specifying whether the feature is on the forward or reverse strand of a double-stranded sequence. If not set, the feature is assumed to be on the forward strand (by convention). If the sequence is single-stranded and this attribute is set, it must not be set to "reverse".
