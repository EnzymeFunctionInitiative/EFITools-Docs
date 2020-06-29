==============
Build Database
==============

The ``builddb.pl`` script is used to create the database build directory
structure.  The structure is created for any of the following build steps.

All scripts are created in ``BUILD_DIR/build``

The ``--dir`` parameter is optional; if it is omitted the current working directory
is used as the database build directory.

If --config is omitted, the ``EFITools/conf`` directory is checked for a config
file named ``build.conf``.

To output SQL loading files for a SQLite3 file, add the ``--db-type sqlite3``
command-line argument.


