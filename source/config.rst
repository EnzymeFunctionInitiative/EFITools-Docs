===========
Config File
===========

* Copy conf/efi.config.example to conf/efi.config

.. code-block:: bash

   cp conf/efi.config.example conf/efi.config

* Edit conf/efi.config to support your environment

* For MySQL/MariaDB Setup edit the database section.

.. code-block:: bash

   [database]
   dbi=mysql
   user=<MYSQLUSER>
   password=<MYSQLPASSWORD>
   host=<MYSQLHOST>
   port=3306

* For SQLite
  
.. code-block:: bash

   [database]
   dbi=sqlite3
   name=<PATH TO SQLITE DATABASE>

 
* For HPC Cluster, specify the job scheduler and queue/partition to use.

.. code-block:: bash

   [cluster]
   scheduler=<slurm/torque/pbspro>
   queue=<QUEUE>
   mem_queue=<LARGE MEMORY QUEUE>
   max_queue_ram=<MAXIMUM RAM RESERVATION SUPPORTED FOR STANDARD NODE>
   max_mem_queue_ram=<MAXIMUM RAM RESERVATION SUPPORTED FOR LARGE MEMORY NODE>
   np=<NUMBER OF PROCESSORS>
   scratch_dir=<LOCAL NODE SCRATCH DIRECTORY>

The ``max_queue_ram`` and ``max_mem_queue_ram`` paramters are used to dynamically determine which node to assign particular jobs to.

===========
Environment
===========

In order to run the EFITool commands, the environment for it needs to be setup so the bin folder is in your PATH,  
* Copy environment.sh.example file to environment.sh

.. code-block:: bash

   cp environment.sh.example environment.sh

* Edit environmemt.sh to have the PATH variable point to the bin folder and add any other PATHS, LD_LIRRARY_PATHS, modules that are needed.

.. code-block:: bash

   #!/bin/bash
   export PATH=/usr/local/EFITools/bin:$PATH
   export PATH=/usr/local/EFITools/sbin/db_tools:$PATH

