========
Download
========

* Download the latest version from https://github.com/EnzymeFunctionInitiative/EFITools/releases

* Alternatively you can git clone the repository

.. code-block:: bash

   git clone https://github.com/EnzymeFunctionInitiative/EFITools.git

* Extract the zip or tar.gz file

.. code-block:: bash

   tar -xf 2.0.tar.gz
   unzip 2.0.zip

* Install required applcations

** R - 

** CD-HIT

** Coreutils - It is included in all linux distributions.  We recommend to compile the latest version so the **sort** command has all the features.

** BLAST - Download the precompiled version

* Set CPAN module install location
.. code-block:: bash

   o conf mbuildpl_arg "--install_base <PERL PREFIX>"
   o conf makepl_arg "PREFIX=<PERL PERFIX>"
   o conf commit 

* Install required CPAN modules

.. code-block:: bash

   cpan install DBI DBD::mysql DBD::SQLite Capture::Tiny Exporter Log::Message::Simple Getopt::Long \
	List::Util List::MoreUtils IO::File XML::Writer XML::LibXML XML::Parser XML::LibXML::Reader \
	Data::Dumper File::Slurp JSON Storable Scalar::Util Array::Utils Config::IniFiles \
	Statistics::Descriptive GD::Graph::boxplot


