Terminology and Model 
!!!!!!!!!!!!!!!!!!!!!

Summary goes here 

Sequence-Based View
@@@@@@@@@@@@@@@@@@@

Summary goes here 

.. _Sequence-Based View:

Sequence-Based View
###################

.. _Sequence:

Sequence
$$$$$$$$

Summary goes here

**Information Model**

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
      - identifier
      - [0..*]
   *  - name
      - string
      - [0..*]
   *  - representation
      - SequenceRepresentation
      - [0..*]
   *  - features
      - LocatedFeature
      - [0..*] 


.. _LocatedFeature:

LocatedFeature
$$$$$$$$$$$$$$

Summary goes here 

**Information Model**

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
   *  - feature 
      - SequenceFeature
      - [1..1]
   *  - location
      - Location
      - [1..1]
   *  - strand
      - CodeableConcept
      - [0..1]

.. _SequenceFeature:

SequenceFeature
$$$$$$$$$$$$$$$

Summary goes here 

**Information Model**

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
   *  - identifier 
      - identifier
      - [0..*]
   *  - type
      - CodableConcept
      - [1..1]
   *  - name
      - string
      - [0..*]

Feature-Based View
@@@@@@@@@@@@@@@@@@@

Summary goes here 

.. _Feature-Based View:

Feature-Based View
##################

.. _SequenceFeature:

SequenceFeature
$$$$$$$$$$$$$$$

Summary goes here 

**Information Model**

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
   *  - identifier 
      - identifier
      - [0..*]
   *  - type
      - CodableConcept
      - [1..1]
   *  - name
      - string
      - [0..*]
   *  - contexts
      - ContextualizedFeature
      - [0..*]

.. _ContextualizedFeature:

ContextualizedFeature
$$$$$$$$$$$$$$$$$$$$$

Summary goes here 

**Information Model**

.. list-table::
   :class: clean-wrap
   :header-rows: 1
   :align: left
   :widths: auto
   
   *  - Field 
      - Type
      - Limits
   *  - sequence 
      - Sequence
      - [1..1]
   *  - location
      - Location
      - [1..1]
   *  - strand
      - CodeableConcept
      - [0..1]


.. _Sequence:

Sequence
$$$$$$$$

Summary goes here 

**Information Model**

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
      - identifier
      - [0..*]
   *  - name
      - string
      - [0..*]
   *  - representation
      - SequenceRepresentation
      - [0..*]

Locations
@@@@@@@@@

.. _Location:

Location
########

As used by biologists, the precision of "location" (or "locus") varies
widely, ranging from precise start and end numerical coordinates
defining a Location, to bounded regions of a sequence, to conceptual
references to named genomic features (e.g., chromosomal bands, genes,
exons) as proxies for the Locations on an implied reference sequence.

The most common and concrete Location is a :ref:`SequenceLocation`, i.e.,
a Location based on a named sequence and an Interval on that sequence.
Another common Location is a :ref:`ChromosomeLocation`, specifying a
location from cytogenetic coordinates of stained metaphase chromosomes.
Additional :ref:`planned-locations` may also be conceptual or symbolic locations,
such as a cytoband region or a gene. Any of these may be used as the
Location for Variation.

.. include:: defs/Location.rst

.. _ChromosomeLocation:

ChromosomeLocation
$$$$$$$$$$$$$$$$$$

Chromosomal locations based on named features, including named landmarks,
cytobands, and regions observed from chromosomal staining techniques.

.. include:: defs/ChromosomeLocation.rst

.. _SequenceLocation:

SequenceLocation
$$$$$$$$$$$$$$$$

A *Sequence Location* is a specified subsequence of a reference :ref:`Sequence`.
The reference is typically a chromosome, transcript, or protein sequence.

.. include:: defs/SequenceLocation.rst

