
Programs
========

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
   
OMP_WAIT_POLICY ensures that the OMP threads are kept active.
   
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

.. figure:: figures/Efficiency_CP.svg

In the efficiency plot the same story can be seen as in the speedup plot. 
Here it can also be seen that 14 and 21 looks like they are good spots.



