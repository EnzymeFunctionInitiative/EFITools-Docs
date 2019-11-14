===========
Config File
===========

* Copy conf/efi.config.example to conf/efi.config

.. code-block:: bash

   cp conf/efi.config.example conf/efi.config

* Edit conf/efi.config to support your environment

* For MySQL Setup edit the database section.

.. code-block:: bash

   [database]
   user=<MYSQLUSER>
   password=<MYSQLPASSWORD>
   host=<MYSQLHOST>
   port=3306
   ip_range=<IPRANGE>

* For SQLite

* For HPC Cluster, specify the job scheduler and queue/paritition to use.

.. code-block:: bash

   [cluster]
   scheduler=<PBS/SLURM>
   queue=<QUEUE>

* Copy environment.sh.example file to environment.sh

.. code-block:: bash

   cp environment.sh.example environment.sh

* Edit environemt.sh to support your environement

.. code-block:: bash

   export EFI_CONFIG
   export EFI_PASS
   export EFI_EST
   export EFI_QUEUE
   export EFI_NP
   export EFI_MEMQUEUE


