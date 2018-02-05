
Multi-Configurational Self-Consistent Field
===========================================

Introduction
------------

In MCSCF the wave function is given as:

.. math::
   \Psi_{\mathrm{MCSCF}}=\sum_{i}c_{i}^{\mathrm{CI}}\Phi_{i}\left(\left\{ c^{\mathrm{MO}}\right\} \right)
   
The :math:`\Phi_{i}` are different determinants. 
This looks very much like the CI wave function, but the big difference is that for an MCSCF wave function both the configuration coefficients and the orbital coefficients are optimized.
In CI only the configuration coefficients are optimized.
Thus giving two conditions for the optimization of the MCSCF wave function:

.. math::
   \frac{\partial E_{\mathrm{MCSCF}}\left(c^{\mathrm{CI}},c^{\mathrm{MO}}\right)}{\partial c_{i}^{\mathrm{CI}}}=0
   
and, 

.. math::
   \frac{\partial E_{\mathrm{MCSCF}}\left(c^{\mathrm{CI}},c^{\mathrm{MO}}\right)}{\partial c_{i}^{\mathrm{MO}}}=0
   
