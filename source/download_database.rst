=================
Download Database
=================

* The databases are located at 

	`https://efi.igb.illinois.edu/databases/latest <https://efi.igb.illinois.edu/databases/latest>`_

* Older versions can be found at 

	`https://efi.igb.illinois.edu/databases/ <https://efi.igb.illinois.edu/databases>`_


* You need to download the blastdb and either the sqlite database or the mysql import file.  
* The md5sum and sha256sums are also located in the folder

* Using wget

.. code-block:: bash

        wget https://efi.igb.illinois.edu/databases/20200423/blastdb_202004.tar.bz2
	wget https://efi.igb.illinois.edu/databases/20200423/efi_202004.mysql.sql.bz2
	wget https://efi.igb.illinois.edu/databases/20200423/efi_202004.sqlite.bz2

* Using rsync

.. code-block:: bash

        rsync -av rsync://efi.igb.illinois.edu/databases/20200423/blastdb_202004.tar.bz2 .
        rsync -av rsync://efi.igb.illinois.edu/databases/20200423/efi_202004.mysql.sql.bz2 .
        rsync -av rsync://efi.igb.illinois.edu/databases/20200423/efi_202004.sqlite.bz2 .



