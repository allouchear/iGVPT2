This is the example suite for midascpp
=======================================

Running
-----------

Give the path to the midascpp executable as MIDASCPP in ``run_example``
OR provide the path to the midascpp install directory with the --midas option.

Examples are run with the script ``run_example``
by running it in the ``example_suite`` directory,
and passing it the directory of the example as
an argument.

e.g.:

``
   ./run_example surface/grid/static/std_h2o_turbomole_mp2f12/
``
   this will run the generic pes example on water 
   using the Turbomole program.

NB: Remember to PATHS to ES programs in file ``ES_PROGRAMS``.

Cleaning
-----------

An example directory can be cleaned with the clean\_example.sh
script by running it with the directory to clean as
an argument.

e.g.:
``
   ./clean_example surface/grid/static/std_h2o_turbomole_mp2f12/ 
``

   this will clean the directory for the 
   generic Turbomole example on water

Unpack without running
-----------

Run with the --dry option.

To unpack an example without running it,
just move to the specific examples directory 
and run the script.

e.g.:
``
   cd surface/grid/static/std_h2o_turbomole_mp2f12/
   ./std_h2o_turbomole_mp2f12
``

   This will unpack example and ready all files
   (NB: this will not create a scratch dir 
    or run the calculation)

NB: scripts use bourne again shell (bash),
    but might work with other shells as well...

Navigating the example suite
-----------

The example suite is hierarchical build

````
     vib          surface           coordinates
      |              |                   |
  ---------      --------           ----------
  |   |   |      |      |           |        |
 vcc vci vscf  taylor  grid              modvibcoord
                        |                    
                     -------
                     |     |
                   adga  static 

````

 to give a natural structure to search for the kind of MidasCPP
 calculation you are interessted in. The name for the examples
 has the following structure:

``
  <std or adv>_<mol>_<program>_<property or special info>
``

  1. The first part tells you if it is an advanced, recommended or standard calculation.
  2. The second part specifies the molecule.
  3. The third part may indicate the used electronic structure program (PES).
  4. The last part indicates the property or gives a special info. 

 To search for molpro related examples you can use

``
 find ./ -type d -iname "*molpro*"
``

 in the top level directory.


