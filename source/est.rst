Enzyme Similarity Tool (EST)
============================

* Sequence BLAST

The provided sequence is used as the query for a BLAST search of the UniProt database. The retrieved sequences are used to generate the SSN. 
This allows exploration of local sequence-function space for the query sequence. By default, 1,000 sequences are collected. This allows a small "full" SSN to be generated and viewed with Cytoscape. This for local high resolution SSNs.


.. code-block:: bash

   ssn_blast_job.pl

.. csv-table::

   "``--seq``", "Sequence to search"
   "``--tmp|tmpdir``", "Temporary Directory"
   "``--evalue``","Family E-Value"
   "``--blast-evalue``", "Blast E-Value"
   "``--multiplexing``", "Multiplexing"
   "``--lengthdif``", "Length Difference"
   "``--sim``", "Unknown"
   "``--np``","Number of Processors (1,2,4,etc)"
   "``--blasthit``", "Blast Hits"
   "``--queue``","Queue/Partition to use"
   "``--memqueue``", "High Memory Queue/Partition to use"
   "``--nresults``", "Maximum number of Results"
   "``--seq-count-file``", "Sequence Count File"
   "``--ipro``", "Interpro"
   "``--pfam``", "PFam"
   "``--uniref-version``", "Uniref Version"
   "``--uniref-expand``", "expand to include all homologues of UniRef seed sequences that are provided."
   "``--fraction``", "Fraction"
   "``--maxsequence``", "Max Family Sequence"
   "``--oldgraphs``", "Use Old Graph Method"
   "``--job-id``", "Job ID"
   "``--blast-input-id``", "Blast Input ID"
   "``--remove-temp``", "Remove Temporary Directory"
   "``--scheduler``", "Scheduler to Use (PBS/SLURM)"
   "``--dryrun``", "Dry-Run - Prints out commands"
   "``--config``", "Config File to use (defaults to conf/efi.config)"
   "``--exclude-fragments``", "Exclude Fragments"
   "``--db-type``", "uniprot, uniref50, uniref90 (defaults to uniprot)"


* Families

Defined protein families are used to generate the SSN. allows exploration of sequence-function space from defined protein families. A limit of 100,000 sequences is imposed. Generation of a SSN for more than one family is allowed. Using UniRef90 and UniRef50 databases allows the creation of SSNs for very large Pfam and/or InterPro families, but at lower resolution. 

* FASTA

A SSN is generated from a set of defined sequences. allows generation of a SSN for a provided set of FASTA formatted sequences. By default, EST cannot associate the provided sequences with sequences in the UniProt database, and only two node attributes are provided for the SSNs generated: the number of residues as the "Sequence Length", and the FASTA header as the "Description". An option allows the FASTA headers to be read and if Uniprot or NCBI identifiers are recognized, the corresponding Uniprot information will be presented as node attributes. 

* Accession IDs

The SSN is generated after fetching the information from the corresponding databases. allows for a list of UniProt IDs, NCBI IDs, and/or NCBI GI numbers (now "retired"). UniProt IDs are used to retrieve sequences and annotation information from the UniProt database. When recognized, NCBI IDs and GI numbers are used to retrieve the "equivalent" UniProt IDs and information. Sequences with NCBI IDs that cannot be recognized will not be included in the SSN and a "no match" file listing these IDs is available for download.
 
* Color SSNs

Utility for the identification and coloring of independent clusters within a SSN. Independent clusters in the uploaded SSN are identified, numbered and colored. Summary tables, sets of IDs and sequences per clusters are provided. A Cytoscape-edited SNN can serve as input for this utility. 

.. code-block:: bash

   ssn_color_job.pl

* SSN Finalization

A minimum sequence similarity threshold that specifies the sequence pairs connected by edges is needed to generate the SSN. This threshold also determines the segregation of proteins into clusters. The threshold is applied to the edges in the SSN using the alignment score, an edge node attribute that is a measure of the similarity between sequence pairs. 

.. code-block:: bash

   ssn_analysis_job.pl


