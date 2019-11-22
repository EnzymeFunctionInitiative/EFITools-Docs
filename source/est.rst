Enzyme Similarity Tool (EST)
============================
The main program is **efi.pl**.  This has all the parameters and settings to run EST jobs.

=================
Setup Environment
=================
First you need to setup the environment for the EFITools to run.  You need to source the environment.sh file from the EFITools directory

.. code-block:: bash

   source /usr/local/EFITools/environment.sh

======================
Global/Advance Options
======================

* Global Options

.. csv-table::

   "``--job-id``", "the job number to assign to the job; this is the prefix to each file; if not specified no prefix will be assigned to the output files and job scripts (the file name will mirror that of the input file)."
   "``--job-dir``", "the directory to store all of the inputs/outputs to the job; it will contain scripts/ (the location for scripts submitted ot the cluster), log/ (the output from cluster jobs), and output/ (the directory where results will be stored)."
   "``--help``","if no valid job types are specified, this help is displayed; if a job type is provided, shows the specific options for the job type."

* Advanced Options (only for administrators for testing purposes)

.. csv-table::

   "``--dry-run``", "doesn't create any directories or job scripts; outputs to the terminal what would be submitted to the cluster."
   "``--no-submit``", "only create the job scripts, do not submit them to the cluster."
   "``--dir-name``","the output directory name to put results into (defaults to output/)."
   "``--remove-temp``", "setting this to 0 will not remove intermediate files; useful for debugging; defaults to true (remove all intermediate files)"
   "``--serial-script``", "output all of the cluster jobs into a single file that can be run on a single cluster node, or on a stand-alone system."

==============
Sequence BLAST
==============

The provided sequence is used as the query for a BLAST search of the UniProt database. The retrieved sequences are used to generate the SSN. 
This allows exploration of local sequence-function space for the query sequence. By default, 1,000 sequences are collected. This allows a small "full" SSN to be generated and viewed with Cytoscape. This for local high resolution SSNs.


.. code-block:: bash

   efi.pl blast

.. csv-table::

   "``--sequence``", "Sequence to search"
   "``--sequence-file``", "File with Sequence"
   "``--blast-evalue``","numeric value indicating the negative log of the e-value to use for retrieving similar sequences; defaults to 5"
   "``--max-blast-results``", "numeric value to limit the number sequences retrieved; defaults to 1000"
   "``--blast-input-id``", "the ID to include in the SSN that represents the input sequence; defaults to zINPUTSEQ"
   "``--pfam``", "Pfam family; can also be Pfam clan; multiple families can be used by including the --pfam arg multiple times"
   "``--interpro``", "InterPro family; multiple families can be used by using the --interpro arg multiple times"
   "``--fraction``","A numeric value that is the fraction of sequences to include from the family; by default all sequences are used"
   "``--uniref-version``", "Uses the UniRef50 or UniRef90 cluster ID sequences instead of the full family"
   "``--exclude-fragments``","exclude sequences that are defined as fragments by UniProt"

========
Families
========

Defined protein families are used to generate the SSN. allows exploration of sequence-function space from defined protein families. A limit of 100,000 sequences is imposed. Generation of a SSN for more than one family is allowed. Using UniRef90 and UniRef50 databases allows the creation of SSNs for very large Pfam and/or InterPro families, but at lower resolution. 

.. code-block:: blash

   efi.pl family


.. csv-table::

   "``--pfam``", "Pfam family; can also be Pfam clan; multiple families can be used by including the --pfam arg multiple times"
   "``--interpro``", "InterPro family; multiple families can be used by using the --interpro arg multiple times"
   "``--fraction``","A numeric value that is the fraction of sequences to include from the family; by default all sequences are used"
   "``--uniref-version``", "Uses the UniRef50 or UniRef90 cluster ID sequences instead of the full family"
   "``--domain``", "use the sequence domain specified by the family(s)"
   "``--exclude-fragments``", "exclude sequences that are defined as fragments by UniProt"

=====
FASTA
=====

A SSN is generated from a set of defined sequences. allows generation of a SSN for a provided set of FASTA formatted sequences. By default, EST cannot associate the provided sequences with sequences in the UniProt database, and only two node attributes are provided for the SSNs generated: the number of residues as the "Sequence Length", and the FASTA header as the "Description". An option allows the FASTA headers to be read and if Uniprot or NCBI identifiers are recognized, the corresponding Uniprot information will be presented as node attributes. 

.. code-block:: bash

   efi.pl fasta

.. csv-table::

   "``--fasta-file``", "file containing FASTA-format sequences with FASTA headers"
   "``--use-fasta-headers``", "parse FASTA headers for UniProt or RefSeq IDs"
   "``--pfam``","Pfam family; can also be Pfam clan; multiple families can be used by including the --pfam arg multiple times"
   "``--interpro``", "InterPro family; multiple families can be used by using the --interpro arg multiple times"
   "``--fraction``", "A numeric value that is the fraction of sequences to include from the family; by default all sequences are used"
   "``--uniref-version``", "Uses the UniRef50 or UniRef90 cluster ID sequences instead of the full family"
   "``--exclude-fragments``", "exclude sequences that are defined as fragments by UniProt"

=============
Accession IDs
=============

The SSN is generated after fetching the information from the corresponding databases. allows for a list of UniProt IDs, NCBI IDs, and/or NCBI GI numbers (now "retired"). UniProt IDs are used to retrieve sequences and annotation information from the UniProt database. When recognized, NCBI IDs and GI numbers are used to retrieve the "equivalent" UniProt IDs and information. Sequences with NCBI IDs that cannot be recognized will not be included in the SSN and a "no match" file listing these IDs is available for download.

.. code-block:: bash

   efi.pl accession

.. csv-table::

   "``--accession-file``", "file containing list of sequence IDs, UniProt or NCBI RefSeq IDs are supported"
   "``--pfam``", "Pfam family; can also be Pfam clan; multiple families can be used by including the --pfam arg multiple times"
   "``--interpo``","InterPro family; multiple families can be used by using the --interpro arg multiple times"
   "``--fraction``", "A numeric value that is the fraction of sequences to include from the family; by default all sequences are used"
   "``--uniref-version``", "Uses the UniRef50 or UniRef90 cluster ID sequences instead of the full family"
   "``--exclude-fragments``", "exclude sequences that are defined as fragments by UniProt"

 
==========
Color SSNs
==========

Utility for the identification and coloring of independent clusters within a SSN. Independent clusters in the uploaded SSN are identified, numbered and colored. Summary tables, sets of IDs and sequences per clusters are provided. A Cytoscape-edited SNN can serve as input for this utility. 

.. code-block:: bash

   efi.pl color

.. csv-table::

   "``--ssn-in``", "path to uncolored SSN"
   "``--ssn-out``", "path to output SSN, colored and numbered"
   "``--map-file-name``","path to output file mapping UniProt IDs to clusters"
   "``--domain-map-file-name``", "path to output file mapping UniProt IDs to clusters, with domain info; only valid when the input SSN contains domain-length sequences"
   "``--stats``", "path to statistics file containing various node counts"
   "``--cluster-size``", "path to file that lists cluster sizes"
   "``--sp-clusters-desc``", "path to file that lists Swiss-Prot IDs and the corresponding cluster number"
   "``--sp-singletons-desc``", "path to file that lists Swiss-Prot IDs in singletons"





================
SSN Finalization
================

A minimum sequence similarity threshold that specifies the sequence pairs connected by edges is needed to generate the SSN. This threshold also determines the segregation of proteins into clusters. The threshold is applied to the edges in the SSN using the alignment score, an edge node attribute that is a measure of the similarity between sequence pairs. 

.. code-block:: bash

   efi.pl analyze

.. csv-table::

   "``--minval``", "minimum alignment score to use for separating nodes into clusters"
   "``--filter``", "eval = group on alignment score; bit = group on bitscore"
   "``--minlen``","minimum sequence length to include node in network"
   "``--maxlen``", "maximum sequence length to include node in network"
   "``--title``", "title of the file; goes into the filename; defaults to Untitled"
   "``--uniref-version``", "this should be set if the generate step was created using UniRef settings"


