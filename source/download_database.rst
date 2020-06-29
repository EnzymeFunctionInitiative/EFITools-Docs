=================
Download Database
=================

* The databases are located at 

.. code-block:: bash

	https://efi.igb.illinois.edu/database/latest

* Older versions can be found at 

.. code-block:: bash

        https://efi.igb.illinois.edu/database/

* We provide the sqlite database, mysql import file, and the blast databases along with their md5 and sha256 checksums.
* Using wget

.. code-block:: bash

        wget https://efi.igb.illinois.edu/databases/20200423/blastdb_202004.tar.bz2
	wget https://efi.igb.illinois.edu/databases/20200423/efi_202004.mysql.bz2
	wget https://efi.igb.illinois.edu/databases/20200423/efi_202004.sqlite.bz2

* Using rsync

.. code-block:: bash

        rsync -av rsync://efi.igb.illinois.edu/databases/20200423/blastdb_202004.tar.bz2 .
        rsync -av rsync://efi.igb.illinois.edu/databases/20200423/efi_202004.mysql.bz2 .
        rsync -av rsync://efi.igb.illinois.edu/databases/20200423/efi_202004.sqlite.bz2 .



