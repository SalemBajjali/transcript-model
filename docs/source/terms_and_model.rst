Terminology and Model 
!!!!!!!!!!!!!!!!!!!!!

Summary goes here 

Sequence-Based and Feature-Based
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

Summary goes here 

.. _Sequence-Based-View:

Sequence-Based View
###################

.. _Sequence:

Sequence
$$$$$$$$

Summary goes here

.. include:: defs/DSAM/Sequence.rst

.. _LocatedFeature:

LocatedFeature
$$$$$$$$$$$$$$

Summary goes here 

.. include:: defs/DSAM/LocatedFeature.rst

.. _SequenceFeature:

SequenceFeature
$$$$$$$$$$$$$$$

Summary goes here 

.. include:: defs/DSAM/SequenceFeature.rst

.. Feature-Based View
.. @@@@@@@@@@@@@@@@@@@

.. Summary goes here 

.. _Feature-Based-View:

Feature-Based View
##################

.. _SequenceFeature:

SequenceFeature
$$$$$$$$$$$$$$$

Summary goes here 

**Information Model**

.. include:: defs/DSAM/SequenceFBV.rst

.. _ContextualizedFeature:

ContextualizedFeature
$$$$$$$$$$$$$$$$$$$$$

Summary goes here 

.. include:: defs/DSAM/ContextualizedFeature.rst 


.. _SequenceFBV:

SequenceFBV
$$$$$$$$$$$

Summary goes here 

.. include:: defs/DSAM/SequenceFBV.rst


.. Locations and Intervals
.. @@@@@@@@@@@@@@@@@@@@@@@


.. .. _Location:

.. Location
.. ########

.. As used by biologists, the precision of "location" (or "locus") varies
.. widely, ranging from precise start and end numerical coordinates
.. defining a Location, to bounded regions of a sequence, to conceptual
.. references to named genomic features (e.g., chromosomal bands, genes,
.. exons) as proxies for the Locations on an implied reference sequence.

.. The most common and concrete Location is a :ref:`SequenceLocation`, i.e.,
.. a Location based on a named sequence and an Interval on that sequence.
.. Another common Location is a :ref:`ChromosomeLocation`, specifying a
.. location from cytogenetic coordinates of stained metaphase chromosomes.
.. Additional :ref:`planned-locations` may also be conceptual or symbolic locations,
.. such as a cytoband region or a gene. Any of these may be used as the
.. Location for Variation.

.. .. include:: defs/vrs/Location.rst

.. **Implementation Guidance**

.. * Location refers to a position.  Although it MAY imply a sequence,
..   the two concepts are not interchangeable, especially when the
..   location is non-specific (e.g., specified by an :ref:`IndefiniteRange`).
..   To represent a sequence derived from a Location, see
..   :ref:`DerivedSequenceExpression`.


.. .. _ChromosomeLocation:

.. ChromosomeLocation
.. $$$$$$$$$$$$$$$$$$

.. Chromosomal locations based on named features, including named landmarks,
.. cytobands, and regions observed from chromosomal staining techniques.

.. .. include:: defs/vrs/ChromosomeLocation.rst

.. **Implementation Guidance**

.. * ChromosomeLocation is intended to enable the representation of
..   cytogenetic results from karyotyping or low-resolution molecular
..   methods, particularly those found in older scientific literature.
..   Precise :ref:`SequenceLocation` should be preferred when
..   nucleotide-scale location is known.
.. * `species` is specified using the NCBI taxonomy.  The CURIE prefix
..   MUST be "taxonomy", corresponding to the `NCBI taxonomy prefix at
..   identifiers.org
..   <https://registry.identifiers.org/registry/taxonomy>`__, and the
..   CURIE reference MUST be an NCBI taxonomy identifier (e.g., 9606 for
..   Homo sapiens).
.. * ChromosomeLocation is intended primarily for human chromosomes.
..   Support for other species is possible and will be considered based
..   on community feedback.
.. * `chromosome` is an archetypal chromosome name. Valid values for, and
..   the syntactic structure of, `chromosome` depends on the species.
..   `chromosome` MUST be an official sequence name from `NCBI Assembly
..   <https://www.ncbi.nlm.nih.gov/assembly>`__.  For humans, valid
..   chromosome names are 1..22, X, Y (case-sensitive).  **NOTE: A `chr`
..   prefix is NOT part of the chromosome and MUST NOT be included.**
.. * `interval` refers to a contiguous region specified named markers,
..   which are presumed to exist on the specified chromosome.  See
..   :ref:`CytobandInterval` for additional information.
.. * The conversion of ChromosomeLocation instances to SequenceLocation
..   instances is out-of-scope for VRS.  When converting `start` and
..   `end` to SequenceLocations, the positions MUST be interpreted as
..   inclusive ranges that cover the maximal extent of the region.
.. * Data for converting cytogenetic bands to precise sequence
..   coordinates are available at `NCBI GDP
..   <https://ftp.ncbi.nlm.nih.gov/pub/gdp/>`__, `UCSC GRCh37 (hg19)
..   <http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/cytoBand.txt.gz>`__,
..   `UCSC GRCh38 (hg38)
..   <http://hgdownload.cse.ucsc.edu/goldenPath/hg38/database/cytoBand.txt.gz>`__,
..   and `bioutils (Python)
..   <https://bioutils.readthedocs.io/en/stable/reference/bioutils.cytobands.html>`__.
.. * See also the rationale
..   for :ref:`dd-not-using-external-chromosome-declarations`.


.. **Examples**

.. .. parsed-literal::

..     {
..       "chr": "19",
..       "interval": {
..         "end": "q13.32",
..         "start": "q13.32",
..         "type": "CytobandInterval"
..       },
..       "species_id": "taxonomy:9606",
..       "type": "ChromosomeLocation"
..     }


.. .. _SequenceLocation:

.. SequenceLocation
.. $$$$$$$$$$$$$$$$

.. A *Sequence Location* is a specified subsequence of a reference :ref:`Sequence`.
.. The reference is typically a chromosome, transcript, or protein sequence.

.. .. include:: defs/vrs/SequenceLocation.rst

.. **Implementation Guidance**

.. * For a :ref:`Sequence` of length *n*:
..    * 0 ≤ *interval.start* ≤ *interval.end* ≤ *n*
..    * inter-residue coordinate 0 refers to the point before the start of the Sequence
..    * inter-residue coordinate n refers to the point after the end of the Sequence.
.. * Coordinates MUST refer to a valid Sequence. VRS does not support
..   referring to intronic positions within a transcript sequence,
..   extrapolations beyond the ends of sequences, or other implied
..   sequence.

.. .. important:: HGVS permits variants that refer to non-existent
..                sequence. Examples include coordinates extrapolated
..                beyond the bounds of a transcript and intronic
..                sequence. Such variants are not representable using VRS
..                and MUST be projected to a genomic reference in order
..                to be represented.

.. **Examples**

.. .. parsed-literal::

..     {
..       "interval": {
..         "end": 44908822,
..         "start": 44908821,
..         "type": "SimpleInterval"
..       },
..       "sequence_id": "ga4gh:SQ.IIB53T8CNeJJdUqzn9V_JnRtQadwWCbl",
..       "type": "SequenceLocation"
..     }

.. .. _Interval:
.. .. _SequenceInterval:

.. SequenceInterval
.. ################

.. SequenceInterval is intended to be compatible with a "region" in Sequence Ontology
.. (`SO:0000001 <http://www.sequenceontology.org/browser/current_svn/term/SO:0000001>`_),
.. with the exception that the GA4GH VRS SequenceInterval may be zero-width. The SO
.. definition of region has an "extent greater than zero".

.. .. include:: defs/vrs/SequenceInterval.rst

.. .. sidebar:: VRS Uses Inter-residue Coordinates

..    **GA4GH VRS uses inter-residue coordinates when referring to spans of
..    sequence.**

..    Inter-residue coordinates refer to the zero-width points before and
..    after :ref:`residues <Residue>`. An interval of inter-residue
..    coordinates permits referring to any span, including an empty span,
..    before, within, or after a sequence. See
..    :ref:`inter-residue-coordinates-design` for more details on this design
..    choice.  Inter-residue coordinates are always zero-based.


.. **Sources**

.. * `Interbase Coordinates (Chado documentation) <http://gmod.org/wiki/Introduction_to_Chado#Interbase_Coordinates>`__
.. * `SequenceOntology: sequence_feature (SO:0000110) <http://www.sequenceontology.org/miso/current_svn/term/SO:0000110>`__ — Any extent of continuous biological sequence.
.. * `SequenceOntology: region (SO:0000001) <http://www.sequenceontology.org/miso/current_svn/term/SO:0000001>`__ — A sequence_feature with an extent greater than zero. A nucleotide region is composed of bases and a polypeptide region is composed of amino acids.

.. **Examples**

.. .. parsed-literal::

..     {
..       "end": {
..         "type": "Number",
..         "value": 44908822
..       },
..       "start": {
..         "type": "Number",
..         "value": 44908821
..       },
..       "type": "SequenceInterval"
..     }

.. .. _CytobandInterval:

.. CytobandInterval
.. ################

.. .. important::

..    VRS currently supports only human cytobands and
..    cytoband intervals. Implementers wishing to use VRS for other
..    cytogenetic systems are encouraged to open a `GitHub issue`_.

.. Cytobands refer to regions of chromosomes that are identified by
.. visible patterns on stained metaphase chromosomes.  They provide a
.. convenient, memorable, and low-resolution shorthand for chromosomal
.. segments.

.. .. include:: defs/vrs/CytobandInterval.rst

.. **Implementation Guidance**

.. * When using :ref:`CytobandInterval` to refer to human cytogentic
..   bands, the following conventions MUST be used. Bands are denoted by
..   the arm ("p" or "q") and position (e.g., "22", "22.3", or the symbolic
..   values "cen" or "ter") per ISCN conventions [1]_. These conventions
..   identify cytobands in order from the centromere towards the telomeres.
..   In VRS, we order cytoband coordinates in the p-ter → cen → q-ter
..   orientation, analogous to sequence coordinates. This has the
..   consequence that bands on the p-arm are represented in descending
..   numerical order when selecting cytobands for `start` and `end`.

.. **Examples**

.. .. parsed-literal::

..     {
..       "end": "q13.32",
..       "start": "q13.32",
..       "type": "CytobandInterval"
..     }

.. Primitives
.. @@@@@@@@@@

.. Primitives represent simple values with syntactic or other
.. constraints. They enable correctness for values stored in VRS.

.. .. _CURIE:

.. CURIE
.. #####

.. .. include:: defs/vrs/CURIE.rst

.. **Implementation Guidance**

.. * All identifiers in VRS MUST be a valid CURIE, regardless of
..   whether the identifier refers to GA4GH VRS objects or external data.
.. * For GA4GH VRS objects, this specification RECOMMENDS using globally
..   unique :ref:`computed-identifiers` for use within *and* between
..   systems.
.. * For external data, CURIE-formatted identifiers MUST be used.  When
..   an appropriate namespace exists at `identifiers.org
..   <http://identifiers.org/>`__, that namespace MUST be used.  When an
..   appropriate namespace does not exist at `identifiers.org
..   <http://identifiers.org/>`__, support is implementation-dependent.
..   That is, implementations MAY choose whether and how to support
..   informal or local namespaces.
.. * Implementations MUST use CURIE identifiers verbatim. Implementations
..   MAY NOT modify CURIEs in any way (e.g., case-folding).

.. **Examples**

.. Identifiers for GRCh38 chromosome 19:

.. .. parsed-literal::

..     ga4gh:SQ.IIB53T8CNeJJdUqzn9V_JnRtQadwWCbl
..     refseq:NC_000019.10
..     grch38:19

.. See :ref:`identify` for examples of CURIE-based identifiers for VRS
.. objects.