Requirements
============

===========================
Minimal System Requirements
===========================

* Linux System.  Testing on Redhat/CentOS 6/7
* 8 Cores, minimum
* 32 GB of RAM, minimum
* 1 TB of hard drive space

The amount of CPU cores and RAM required is greatly dependent on the types of inputs provided. For small families and numbers of sequences, low system specs will work just fine.  For large families, much more RAM can be required.

============
Applications
============

Versions more recent than the versions specified below are acceptable.

* Perl (https://www.perl.org/)

* Perl Modules (https://www.cpan.org/)

   - Array::Utils >= 0.5
   - Bio::HMM::Logo (https://github.com/Janelia-Farm-Xfam/Bio-HMM-Logo)
   - Capture::Tiny >= 0.42
   - Data::Dumper >= 2.160
   - Data::UUID
   - Config::IniFiles >= 3.000002
   - DBD::mysql >= 4.013
   - DBD::SQLite >= 1.27
   - DBI >= 1.609
   - Exporter >= 5.68
   - File::Slurp >= 9999.19
   - Getopt::Long >= 2.48
   - GD::Graph::boxplot >= 1.00
   - Imager
   - Imager::File::PNG
   - Inline >= 0.53
   - IO::File >= 1.16
   - JSON >= 2.15
   - List::MoreUtils >= 0.428
   - List::Util >= 1.45
   - Log::Message::Simple >= 0.10
   - Scalar::Util >= 1.45
   - Statistics::Descriptive >= 3.0702
   - Statistics::R >= 0.34
   - Storable >= 2.56
   - SVG (for Bio::HMM::Logo)
   - XML::LibXML >= 1.70
   - XML::LibXML::Reader >= 2.0129
   - XML::Parser >= 2.36
   - XML::Writer >= 0.606

* These modules can be installed by using the cpanm command, ran from the EFITools installation directory.

* R 3.3.0 or greater (https://www.r-project.org/) with PNG support

* R Packages 

   - rhdf5 (https://bioconductor.org/packages/release/bioc/html/rhdf5.html) **
   - Hmisc (https://cran.r-project.org/web/packages/Hmisc/index.html) **

* HDF5 (https://www.hdfgroup.org/solutions/hdf5/)

* BLAST 2.2.26 (https://blast.ncbi.nlm.nih.gov/Blast.cgi) - Note: This is the legacy BLAST, and requires this specific version; not NCBI-BLAST+

* NCBI-BLAST+ 2.2.28 (for EFI-CGFP)

* CD-HIT (http://weizhongli-lab.org/cd-hit/)

* USEARCH v6.0.307 (http://www.drive5.com/usearch/)

* MUSCLE v3.8.31 (http://www.drive5.com/muscle/)

* DIAMOND 0.9 (https://github.com/bbuchfink/diamond)

* Clustal Omega (http://www.clustal.org/omega/)

* weblogo > 3.7 (Python app; can be installed with pip)

* GNU Coreutils 8.28 or greater (https://www.gnu.org/software/coreutils/)

* SQL Database.  Currently supports the following

   - SQLite (https://www.sqlite.org/)
   - MySQL (https://www.mysql.com/)
   - MariaDB (https://mariadb.com/)

* Libxml2 (http://www.xmlsoft.org/)

* LibGD (http://libgd.github.io/)

* Linux utilities: dos2unix, mac2unix, bc

HDF5 is only required if using HDF5-based graphing code (as of release 2, this is disabled by
default).

=================
Genomic Databases
=================

* InterPro (https://www.ebi.ac.uk/interpro/)
* Uniprot (https://www.uniprot.org/)

============
HPC Clusters
============

* This can be run on a single machine.  A HPC Job Scheduler is also supported.  Currently supports the following

   - SLURM (https://slurm.schedmd.com/slurm.html)
   - PBS Torque (https://www.adaptivecomputing.com/products/torque/)
   - PBS Pro (https://www.pbspro.org/)

