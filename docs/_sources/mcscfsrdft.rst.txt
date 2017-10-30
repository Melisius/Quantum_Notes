

MCSCF-srDFT
===========

Range seperation
----------------

In WTF-srDFT a range seperation is employed on the two-electron operator such that:

.. math::
   \hat{g}\left(1,2\right)=\hat{g}^{\mathrm{lr}}\left(1,2\right)+\hat{g}^{\mathrm{sr}}\left(1,2\right)
   
Here lr is short for long-range and sr is short for short-range. The long-range and short-range part can be defined as:

.. math::
   \hat{g}^{\mathrm{lr}}\left(1,2\right)=\frac{f\left(\mu r_{12}\right)}{r_{12}}

.. math::
   \hat{g}^{\mathrm{sr}}\left(1,2\right)=\frac{1-f\left(\mu r_{12}\right)}{r_{12}}
   
This way makes :math:`\hat{g}\left(1,2\right)=r_{12}^{-1}` for all :math:`f`. :math:`\mu` is a parameter that describes the distance of seperation of the ranges.