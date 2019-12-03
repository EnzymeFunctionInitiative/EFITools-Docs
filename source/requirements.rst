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

   - DBI 1.609
   - DBD::mysql 4.013
   - DBD::SQLite 1.27
   - Capture::Tiny 0.42
   - Exporter 5.68
   - Log::Message::Simple 0.10
   - Getopt::Long 2.48
   - List::Util 1.45
   - List::MoreUtils 0.428
   - IO::File 1.16
   - XML::Writer 0.606
   - XML::LibXML 1.70
   - XML::Parser 2.36
   - XML::LibXML::Reader 2.0129
   - Data::Dumper 2.160
   - File::Slurp 9999.19
   - JSON 2.15
   - Storable 2.56
   - Scalar::Util 1.45
   - Array::Utils 0.5
   - Config::IniFiles 3.000002
   - GD::Graph::boxplot 1.00

* R 3.3.0 or greater (https://www.r-project.org/)

* R Packages 

   - rhdf5 (https://bioconductor.org/packages/release/bioc/html/rhdf5.html) **
   - Hmisc (https://cran.r-project.org/web/packages/Hmisc/index.html) **

* HDF5 (https://www.hdfgroup.org/solutions/hdf5/) **

* BLAST 2.2.26 (https://blast.ncbi.nlm.nih.gov/Blast.cgi) - Note: This is the legacy BLAST, and requires this specific version; not NCBI-BLAST+

* NCBI-BLAST+ 2.2.28 (for EFI-CGFP)

* CD-HIT (http://weizhongli-lab.org/cd-hit/)

* USEARCH v6.0.307 (http://www.drive5.com/usearch/)

* MUSCLE v3.8.31 (http://www.drive5.com/muscle/)

* DIAMOND 0.9 (https://github.com/bbuchfink/diamond)

* GNU Coreutils 8.28 or greater (https://www.gnu.org/software/coreutils/)

* SQL Database.  Currently supports the following

   - SQLite (https://www.sqlite.org/)
   - MySQL (https://www.mysql.com/)
   - MariaDB (https://mariadb.com/)

* Libxml2 (http://www.xmlsoft.org/)

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

* A Job Scheduler.  Currently supports the following

   - SLURM (https://slurm.schedmd.com/slurm.html)
   - PBS Torque (https://www.adaptivecomputing.com/products/torque/)
   - PBS Pro (https://www.pbspro.org/)

