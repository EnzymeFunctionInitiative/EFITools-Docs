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

To test you can run

.. code-block:: bash

   efi.pl color --ssn-in <INSTALL LOCATION>/sample_data/ssn_uniprot_domain_colored.xgmml

