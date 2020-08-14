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

** R with PNG Support
You can see if R has PNG support by running capabilities()

.. code-block:: bash

   capabilities() 
       jpeg         png        tiff       tcltk         X11        aqua 
       TRUE        TRUE        TRUE        TRUE       FALSE       FALSE 
   http/ftp     sockets      libxml        fifo      cledit       iconv 
       TRUE        TRUE        TRUE        TRUE        TRUE        TRUE 
        NLS     profmem       cairo         ICU long.double     libcurl 
       TRUE       FALSE        TRUE       FALSE        TRUE        TRUE

** CD-HIT

.. code-block:: bash

   wget https://github.com/weizhongli/cdhit/archive/V4.8.1.tar.gz
   tar -xf V4.8.1.tar.gz
   cd cdhit-4.8.1
   make
   make install PREFIX=<INSTALL LOCATION>

** Coreutils - It is included in all linux distributions.  We recommend to compile the latest version so the **sort** command has all the features.

** BLAST - Download the precompiled version 2.2.26

.. code-block:: bash

   wget ftp://ftp.ncbi.nlm.nih.gov/blast/executables/legacy.NOTSUPPORTED/2.2.26/blast-2.2.26-x64-linux.tar.gz
   tar -xf blast-2.2.26-x64-linux.tar.gz

* Install Perl Modules.  This uses the cpanm to install the nessary perl modules.  You can specify a location to install all the modules.

.. code-block:: bash

	cpanm -l <INSTALL LOCATION>  --installdeps .


