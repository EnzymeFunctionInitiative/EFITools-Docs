Genome Neighborhood Network (GNN)
=================================

The EFI-GNT (EFI Genome Neighborhood Tool) is focused on placing protein families and superfamilies into a genomic context. A sequence similarity network (SSN) is used as an input. Each sequence within a SSN is used as a query for interrogation of its genome neighborhood.  EFI-GNT enables exploration of the genome neighborhoods for sequences in SSN clusters in order to facilitate their assignment of function. 


=================
Setup Environment
=================
First you need to setup the environment for the EFITools to run.  You need to source the environment.sh file from the EFITools directory

.. code-block:: bash

   source /usr/local/EFITools/environment.sh

==================
Generating Network
==================

.. code-block:: bash

   efi.pl gnn


.. csv-table::

   "``--ssn-in``", "path to uncolored SSN"
   "``--ssn-out``", "path to output SSN, colored, numbered, and including GNN info; defaults to <INPUT_FILENAME>_coloredssn.xgmml"
   "``--gnn``","path to output cluster-centered GNN; defaults to <INPUT_FILENAME>_ssn_cluster_gnn.xgmml"
   "``--pfam``", "path to output Pfam-centered GNN defaults to <INPUT_FILENAME>_pfam_family_gnn.xgmml"
   "``--nb-size``", "neighborhood size, the number of neighbors to collect on either side; default 10"
   "``--cooc``", "minimal co-occurrence percentage lower limit; default 20"

============================
Genome Neighborhood Diagrams
============================

The EFI-GNT tools provide the capability to view diagrams of genome neighborhoods for input SSNs or for a set of proteins obtained either through a list of IDs or a BLAST.  In a given diagram, the “query” ID—the protein that was input either through a list or corresponding to a node in an SSN—is located in the center of the diagram.  It is always colored red, and is pointing in the “Forward” direction (5’ to 3’).  For query IDs that are on the reverse strand on the sequenceinformation, the neighboring genes are flipped appropriately.

.. code-block:: bash

   efi.pl gnd


.. csv-table::

   "``--diagram-file``", "the file to output arrow/diagram data to"
   "``--blast-seq``", "the sequence for Option A, which uses BLAST to get similar sequences"
   "``--evalue``","the evalue to use for BLAST; default 5"
   "``--max-seq``", "the maximum number of sequences to return from the BLAST; default 200"
   "``--id-file``", "file containing a list of IDs to use to generate the diagrams"
   "``--fasta-file``", "file containing FASTA sequences with headers; we extract the IDs from the headers and use those IDs to generate the diagrams"
   "``--upload-file``", "the file to unzip/prep for viewing in GND"
   "``--output``","output sqlite file for Options A-D"
   "``--title``", "the job title to save in the output file; shows up in GND viewer"
   "``--job-type``","the string to put in for the job type (used by the web app)"
   "``--nb-size``","the neighborhood window on either side of the query sequences; default 10"
