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

* Install GD.  Download latest release from https://github.com/libgd/libgd/releases

.. code-block:: bash

    mkdir deps/work
    cd deps/work
    wget https://github.com/libgd/libgd/releases/download/gd-2.3.3/libgd-2.3.3.tar.gz

* Install Perl Modules.  This uses the cpanm to install the nessary perl modules.
  You can either install modules on a system level, or specify a location to install all the modules locally.
  If cpanm does not exist, it can be downloaded and installed using the following procedure (run from the
  EFI_HOME directory):

.. code-block:: bash

    curl -L https://cpanmin.us/ -o bin/cpanm
    chmod +x bin/cpanm

* Install modules.

.. code-block:: bash

    mkdir perl5
    bin/cpanm -l $PWD/perl5 --installdeps .

* After module installation, it is necessary to configure the Perl environment to use the locally-installed modules
  Edit the conf/perl_env.sh file and change the first line, BASE, to be the EFI_HOME directory.
  conf/perl_env.sh should be included in every environment config.



