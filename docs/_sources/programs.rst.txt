
Programs
========

Amber
-----

A section with some notes about the `Amber <http://ambermd.org/>`_ program.

RESP charges
~~~~~~~~~~~~

Most organic molecules are not explicitly included in the force fields use in Amber.
For these kinds of molecules the GAFF in Amber can be used. 
This force field includes all the bonded and the Lennard-Jones parameters. 
Thus when using these kind of general force field, charges are still needed to account for the electrostatic interactions.
In Amber these charges can be found by doing a restrained electrostatic potential fit (RESP).
RESP can be done using Antechamber, which is a part of the Amber program.
The RESP calculation in Antechamber requires an electro static potential (ESP).
This ESP can be calculated using Gaussian, which then produces a file that can immediately be used by Antechamber.
A minimal Gaussian input file, used to make an ESP for RESP can be seen below:

.. code-block:: fortran

	%NProcShared="NUMBER PROCESSES"
	%mem="AMOUNT MEMORY"MB
	%chk="PATH TO SAVE CHK FILE"
	#p HF/6-31G* SCF=Tight Pop=MK IOp(6/50=1)

	 "SOME TITLE"

	"CHARGE" "MULTIPLICITY"
	"ATOM"         "X"        "Y"       "Z"
	"..."

	"NAME OF ESP FOR ANTECHAMBER".gesp

Everything in " " should be replaced with something user defined (including the " ").
For GAFF the method should be Hartree-Fock with the basis set 6-31G*.
This is used to be consistent with the rest of the force field parameters.
The setting IOp(6/50=1) specifies that the ESP should be printed in a format accepted by Antechamber.
The printed ESP is the ".gesp" file.
Before doing an ESP calculation it is advised to do a geometry optimization with HF/6-31G*.
If metal sites are present B3LYP/6-31G* should be used instead.
For ESP calculations other useful settings are:

IOp(6/41=N), sets the number of layers for which the ESP is calculated.
Default is N = 4.
The chosen value must be 4 or above.
I.e. N ≤ 4.

IOp(6/42=N), sets the density of points per area of the ESP.
Default is N = 1.

IOp(6/43=N), sets the increment between ESP layers.
Default is :math:`\frac{0.4}{\sqrt{\mathrm{layer\ index}}}`.
If N is user defined, the increments will be 0.01*N.

If more than one IOp setting is used, is specified as:

.. code-block:: fortran

	IOp(6/41=10,6/42=17,6/50=1)
	
I.e. IOp is just specified once, with all the settings inside.
Setting IOp(6/41=10) and IOp(6/42=17) is [recommended settings](http://signe.teokem.lu.se/~ulf/Methods/resp.html).
Now that the ".gesp" file have been produced, the RESP charges can be calculated with Antechamber by the following command:

.. code-block:: fortran

	antechamber -i "ESP FILE".gesp -fi gesp -o "OUTPUT FILE".mol2 -fo mol2 -c resp

This will produce a mol2 file, where the charges can be found in last column for each atom. 

*****************************
Example - para-nitrophenolate
*****************************

Here is an example with para-nitrophenolate of calculating the ESP file needed in Antechamber.

.. code-block:: fortran
	
	%NProcShared=12
	%mem=20000MB
	%chk=/home/erik/AmberRuns/PNP1/Resp/PNP1resp.chk
	#p HF/6-31G* SCF=Tight Pop=MK IOp(6/41=10,6/42=17,6/50=1)

	 PNP1 RESP

	-1 1
	C          0.00000        1.22448        1.40664
	C          0.00000        1.21586        0.05197
	C          0.00000        0.00000       -0.66739
	C          0.00000       -1.21586        0.05197
	C          0.00000       -1.22448        1.40664
	C          0.00000        0.00000        2.19316
	O          0.00000        0.00000        3.41948
	N          0.00000        0.00000       -2.06029
	O          0.00000       -1.05965       -2.65602
	O          0.00000        1.05965       -2.65602
	H          0.00000        2.15260        1.95166
	H          0.00000        2.13693       -0.49934
	H          0.00000       -2.13693       -0.49934
	H          0.00000       -2.15260        1.95166

	PNP1resp.gesp

After running Gaussian, the Antechamber command looks like the following for this example:
	
.. code-block:: fortran

	antechamber -i PNP1resp.gesp -fi gesp -o PNP1.mol2 -fo mol2 -c resp

CPMD
----
A section about the `CPMD <http://www.cpmd.org/>`_ program.

Parallelization
~~~~~~~~~~~~~~~

In CPMD one of the things to keep an eye out for when trying to scale over multiple nodes is the number of planes.
The number of planes for a given system can be found in an output file, ran for any amount of time.

.. code-block:: fortran

	 PARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARA
	  NCPU     NGW     NHG  PLANES  GXRAYS  HXRAYS ORBITALS Z-PLANES
		 0    3877   30927       6     166     654       5       1
		 1    3875   30939       6     166     654       6       1
		 2    3871   30935       6     166     654       5       1
		 3    3871   30937       6     166     654       5       1
		 4    3869   30935       6     166     654       6       1
		 5    3868   30931       6     164     654       5       1
		 6    3868   30923       6     164     654       5       1
		 7    3870   30926       6     164     656       6       1
		 8    3866   30924       6     164     656       5       1
		 9    3864   30916       6     164     656       5       1
		10    3864   30926       6     164     656       6       1
		11    3862   30932       6     164     656       5       1
		12    3862   30932       6     164     656       5       1
		13    3866   30926       6     164     656       6       1
		14    3864   30930       6     164     656       5       1
		15    3868   30922       6     164     656       5       1
		16    3872   30932       6     164     656       6       1
		17    3870   30934       6     164     656       5       1
		18    3870   30936       6     164     656       5       1
		19    3868   30920       6     164     656       6       1
		20    3868   30910       6     164     656       5       1
		21    3866   30930       6     164     656       5       1
		22    3861   30854       6     163     655       6       1
		23    3860   30910       6     164     656       5       1
					G=0 COMPONENT ON PROCESSOR :    22
	 PARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARAPARA
	 
The total number of planes is the sum of the column "PLANES".
For the above this would be 144 planes in total.
Obviously this would mean that the parallelization would stop at (nodes*tasks_per_node)/planes = 1.
In CPMD there is an option to let multiple nodes divide the calculation associated with a single plane.
This setting is called CP_GROUPS.
When using CP_GROUPS the goal is still to have the same amount of planes per effective tasks.
Here effective tasks is the number of tasks divided with the amount of CP_GROUPS.

.. math::
   N_{\mathrm{effective\ tasks}} = \frac{N_{\mathrm{total\ tasks}}}{N{_{\mathrm{CP\_GROUPS}}}}
   
To ensure that the number of planes per process is the same, the following relation must be true:

.. math::
   \frac{N{_{\mathrm{CP\_GROUPS}}} N_{\mathrm{planes}}}{N_{\mathrm{total\ tasks}}} \mod 1 = 0

If CPMD have been compiled with OMP, OMP threading can be tried too.
The chosen number of OMP threads and MPI processes must be chosen such that:

.. math::
   N_{\mathrm{OMP\ threads}} N_{\mathrm{MPI\ processes}} = N_{\mathrm{total\ tasks}}
   
OMP threads can be set by:

.. code-block:: fortran

   export OMP_NUM_THREADS=X
   export OMP_WAIT_POLICY=active
   
OMP_WAIT_POLICY=active, ensures that the OMP threads are kept active.
   
******************
Example - 48 Water
******************

This example was benchmarked on the supercomputer Abacus 2.0 at the University of Southern Denmark.
On this architecture every node have 24 cores. 
For this example of 48 water, the number of planes is 168.
Since 168 / 24 = 7, i.e. an integer, it could be thought that settings CP_GROUPS = number of nodes would be a good choice.
It can be identified that three different "sweet spots" exist.
Following the formula from the above section:

.. math::
   \frac{N{_{\mathrm{CP\_GROUPS}}} N_{\mathrm{planes}}}{N_{\mathrm{total\ tasks}}} \mod 1 = 0
  
.. math::
   \frac{1 \cdot 168}{7 \cdot 24} \mod 1  = 1 \mod 1 = 0
   
.. math::
   \frac{2 \cdot 168}{14 \cdot 24} \mod 1  = 1 \mod 1 = 0
   
.. math::
   \frac{3 \cdot 168}{21 \cdot 24} \mod 1  = 1 \mod 1 = 0
   
This indicates that 7, 14 and 21 would be a nice number of nodes.
Higher values of CP_GROUPS also gives integers for 7, 14 and 21 nodes. 
Try the different values to make sure to know what is best.
For the following plots CP_GROUP = 1, 2, 3, 4 tried for all the nodes.

.. figure:: figures/Speedup_CP.svg

For Nodes = [1, 13] the best performance was for CP_GROUPS = 1.

For Nodes = [14, 20] the best performance was for CP_GROUPS = 2.

For Nodes = [21, 24] the best performance was for CP_GROUPS = 3.

This can be rationalized since it was found that 7, 14 and 21 nodes were the spots where the planes were evenly distributed.
If 8 nodes is used instead of 7, some of the processes just have to do less work, while most have to do the same.
The time per step is therefore ca. the same. 
All the numbers between 7 and 14 will have the number of CP_GROUPS equal to that of 7, because 14 nodes is needed, for the CP_GROUPS to make a more even distribution of the planes.
For this specific system it seems like the best parallelization is for the minimal amount of CP_GROUPS that distributes the planes evenly.

.. figure:: figures/Efficiency_CP.svg

In the efficiency plot the same story can be seen as in the speedup plot. 
Here it can also be seen that 14 and 21 looks like they are good spots.


VMD
---

A section about some tricks for the `VMD <http://www.ks.uiuc.edu/Research/vmd/>`_ program.

Set periodic boundary conditions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Sometimes trajectories from programs does not include the information about the periodic boundary conditions.
For a cubic box this is easy to specify on via the TCL terminal.
This can be specified by the following two commands.

.. code-block:: python

   pbc set {X Y Z} -all -molid top
   pbc box -center origin -shiftcenter {cX cY cZ}
 
The first command sets the size of the box for all frames.
"X", "Y" and "Z" have to be specified in Angstrom.
The next command sets the origin of the box.
"cX", "cY" and "cZ" is specified as the starting location of the box.
The default is just (0, 0, 0).

