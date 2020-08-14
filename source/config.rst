===========
Config File
===========

* Copy conf/efi.config.example to conf/efi.config

.. code-block:: bash

   cp conf/efi.conf.example conf/efi.config

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

* The [environment.headers] section allows you to specify additional bash options at the top of the created scripts.  You should put any additional PATH, LD_LIBRARY_PATHS in here.  If you are using environment modules such as lmod https://lmod.readthedocs.io/en/latest/, you can have your module load commands in here.  A couple of examples are below

.. code-block:: bash
   
   [environment.headers]
   export PATH=/usr/local/blast/bin:/usr/local/cdhit/bin:/usr/local/R/bin:/usr/local/muscle/bin:/usr/local/usearch:/usr/local/diamond/bin:$PATH
   export LD_LIBRARY_PATH=/usr/local/R/lib64/R/lib:$LD_LIBRARY_PATH


.. code-block:: bash

   [environment.headers]
   module load perl
   module load blast
   module load cdhit
   module load usearch
   module load muscle
   module load diamond
   module load R
   
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

