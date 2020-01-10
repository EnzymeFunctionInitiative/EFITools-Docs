Build Database
==============

===================
Building a Database
===================

The ``builddb.pl`` script is used to create the database build directory
structure.  The structure is created for any of the following build steps.

All scripts are created in ``BUILD_DIR/build``

The ``--dir`` parameter is optional; if it is omitted the current working directory
is used as the database build directory.

If --config is omitted, the ``EFITools/conf`` directory is checked for a config
file named ``build.conf``.

To output SQL loading files for a SQLite3 file, add the ``--db-type sqlite3``
command-line argument.

---
Step 1: Downloading UniProt and Interpro files
---

``builddb.pl`` can be used to create a script that downloads the requisite files
and is used as follows:

.. code-block:: bash

	builddb.pl --dir BUILD_DIR --download

This creates a script ``0-download.sh``, which can be executed using bash.  The
output from the downloads are stored in ``input/``.  

---
Step 2: Downloading ENA files
---

Currently this is a process that is not automatically included in the download
script build by ``builddb.pl``.  However, there is a line at the end of the file
that gives guidance on how this might be done.  The reason that it is not
included is that the ``rsync`` takes a long time, and occasionally fails and must
be restarted.  This will be moved into the datamover process eventually.  The
download script shouldn't take more than a day to run, but the ``rsync`` of ENA
data will take several days.  The release cycle is different than UniProt and
Interpro as well, so the user will not always download ENA files.  The ``rsync``
can be run independent of the UniProt and Interpro download and processing
jobs.

---
Step 3: Process the UniProt and Interpro files
---

The UniProt and Interpro files need to be processed after being
downloaded.  To create and automatically submit scripts that will process the
downloaded files, the following command can be run:

.. code-block:: bash

	builddb.pl --dir BUILD_DIR --db-name YYYY-MM

This will create several tables in the ``output/`` directory:

.. code-block:: bash

    annotations.tab
    family_counts.tab
    family_info.tab
    idmapping.tab
    INTERPRO.tab
    PFAM_clans.tab
    PFAM.tab
    taxonomy.tab
    uniref.tab

These are loaded into the database with the ``.sql`` script that is generated
by ``builddb.pl``.  This are output into the ``build/`` directory and are
named something like ``#-createDbAndImportData-counts.sql`` and
``#-createDbAndImportData.sql``. Both of these files need to be loaded into
the MySQL or SQLite databases.

---
Step 4: Process ENA files
---

The job that processes the ENA files is dependent on the first part of Step 3,
namely the process-downloads job file.  Once that job is completed, ``builddb.pl``
can be used to create and start a job that processes the ENA files and builds
a tab file that can be imported into the database.  It can be run as follows:

.. code-block:: bash

	builddb.pl --dir BUILD_DIR --ena-dir ENA_DIR --build-ena


This could be triggered at the end of the script that downloads (``rsync``) the
ENA files and made a dependency of the process-downloads job.
If the ``--ena-dir`` option is not provided, it is assumed that the ENA files have
been downloaded to ``BUILD_DIR/input/ena/release``.

---
Step 5: Create database and import data
---

The final steps in building a database involve using ``builddb.pl`` to create SQL
scripts used for creating and importing the data into tables.  In order to
mitigate the risk of overwriting a database, the scripts require that the
user have created a database manually (e.g. "``create database YYYY-MM``" from
within MySQL).  

The ``.sql`` files are output by default, but can be output again by running

.. code-block:: bash

	builddb.pl --dir BUILD_DIR --db-name YYYY-MM --sql

By default ``.sql`` scripts are created that are compatible with MySQL/MariaDB.
To create ones that are compatible with SQLite3, add the ``--db-type sqlite3``
parameter to the command line arguments.

---
Build config file
---

There is a separate ``build.conf`` file in the ``conf/`` directory that contains
information necessary to  build the database.  The ``builddb.pl`` script uses
this file, and does not rely on the ``efi.conf`` file in the ``conf/`` directory.

---
Appendix A
---

To ONLY create a script and SQL file that will create the ``family_counts.tab``
and ``family_info.tab`` tables that need to be imported into both the database
and the EFI webserver mysql database:

.. code-block:: bash

	builddb.pl --dir BUILD_DIR --build-counts


