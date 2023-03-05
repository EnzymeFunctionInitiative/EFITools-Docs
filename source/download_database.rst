=================
Download Database
=================

1. Download databases

* The databases are located at 

	`https://efi.igb.illinois.edu/downloads/databases/latest <https://efi.igb.illinois.edu/downloads/databases/latest>`_

* Older versions can be found at 

	`https://efi.igb.illinois.edu/downloads/databases/ <https://efi.igb.illinois.edu/downloads/databases>`_


* You need to download the blastdb and either the sqlite database or the mysql import file.  
* The md5sum and sha256sums are also located in the folder
* We recommend using `rsync` to download the databases due to their large sizes, but `wget` and `curl` can be used as well.

.. code-block:: bash

	# Using rsync:
	rsync -avPr rsync://efi.igb.illinois.edu/downloads/databases/20200423/blastdb/ .
        rsync -avP rsync://efi.igb.illinois.edu/downloads/databases/20200423/efi_202004.mysql.sql.bz2 .
        rsync -avP rsync://efi.igb.illinois.edu/downloads/databases/20200423/efi_202004.sqlite.bz2 .

	# Using wget:
        wget -r -np -R "index.html*" https://efi.igb.illinois.edu/downloads/databases/20200423/blastdb/
	wget https://efi.igb.illinois.edu/downloads/databases/20200423/efi_202004.mysql.sql.bz2
	wget https://efi.igb.illinois.edu/downloads/databases/20200423/efi_202004.sqlite.bz2

* The above commands will download the blastdb database folder one file at a time. This may be slightly slower, but is often more reliable than downloading it as a single compressed file. However, if you would like to download it as a tar, you can do so using either of the commands below:

.. code-block:: bash

	# Using rsync:
	rsync -avP rsync://efi.igb.illinois.edu/downloads/databases/20200423/blastdb_202004.tar.bz2 .

	# Using wget:
        wget https://efi.igb.illinois.edu/downloads/databases/20200423/blastdb_202004.tar.bz2


2. Unzip compressed database files

* The mysql and sqlite files are always compressed, and need to be unzipped:

.. code-block:: bash

	bunzip2 -vvk efi_202004.mysql.bz2
	bunzip2 -vvk efi_202004.sqlite.bz2

* If you downloaded the blastdb database as an uncompressed folder, then no further action is needed.

* If you downloaded it as a tar, you will need to untar it:

.. code-block:: bash

	tar -xvj blastdb_202004.tar.bz2
