===========
Config File
===========

* Copy conf/build.conf.example to conf/build.conf

.. code-block:: bash

   cp conf/build.conf.example conf/build.conf

* Edit conf/build.conf to support your environment

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
   np=<NUMBER OF PROCESSORS>



