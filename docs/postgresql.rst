===============
Oracle JRE Role
===============

Tasks
=====

* Installs and configures Postgresql server.
* Create postgresql users and databases.

Variables
=========

+---------------------------------------------+----------+--------------------------------------------------------+-------------------------------------+
| Variable                                    | Required | Default                                                | Description                         |
+=============================================+==========+========================================================+=====================================+
| ``postgresql_databases``                    | no       | ``[]``                                                 | List of databases in folowing       |
|                                             |          |                                                        | format::                            |
|                                             |          |                                                        |                                     |
|                                             |          |                                                        |   - name: <database name>           |
|                                             |          |                                                        |     password: <password>            |
+---------------------------------------------+----------+--------------------------------------------------------+-------------------------------------+
| ``postgresql_max_connections``              | no       | 200                                                    | ``postgresql.conf`` options.        |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_checkpoint_segments``          | no       | 32                                                     |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_checkpoint_completion_target`` | no       | 0.7                                                    |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_default_statistics_target``    | no       | 100                                                    |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_shared_buffers``               | no       | RAM / 4                                                |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_effective_cache_size``         | no       | RAM * 3 / 4                                            |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_work_mem``                     | no       | (RAM - ``shared_buffers``) / (``max_connections`` * 3) |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_maintenance_work_mem``         | no       | min(RAM / 16, 2 Gb)                                    |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+                                     |
| ``postgresql_wal_buffers``                  | no       | min(``shared_buffers`` * 3 / 100, 16 Mb)               |                                     |
|                                             |          | if value > 14 Gb, then make it 16 Mb JRE package name. |                                     |
+---------------------------------------------+----------+--------------------------------------------------------+-------------------------------------+
| ``postgresql_accept``                       | no       |                                                        | List of IPv4 accepted net           |
|                                             |          |                                                        | addresses (``X.X.X.X/netmask``).    |
+---------------------------------------------+----------+--------------------------------------------------------+-------------------------------------+
| ``postgresql_accept6``                      | no       |                                                        | List of IPv6 accepted net           |
|                                             |          |                                                        | addresses (``X.X.X.X/netmask``).    |
+---------------------------------------------+----------+--------------------------------------------------------+-------------------------------------+
| ``kernel_shmall``                           | no       | RAM (in Mb) * 128                                      | ``kernel.shmall`` sysctl parameter. |
+---------------------------------------------+----------+--------------------------------------------------------+-------------------------------------+
| ``kernel_shmmax``                           | no       | ``kernel_shmall`` * 4096                               | ``kernel.shmmax`` sysctl parameter. |
+---------------------------------------------+----------+--------------------------------------------------------+-------------------------------------+
