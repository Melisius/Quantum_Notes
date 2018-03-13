

Quantum operator examples
=========================

Orbital rotation operator
-------------------------

The orbital rotation operator is given as:

.. math::
   \hat{\kappa}=\sum_{pq}\kappa_{pq}\hat{E}_{pq}
   
The orbital rotation operator is anti-Hermitian, thus:

.. math::
   \kappa_{pq}=-\kappa_{qp}^{*}
   
here the * denotes complex conjugate.
Now the sum can be expanded:

.. math::
   \hat{\kappa}=\sum_{p>q}\left(\kappa_{pq}\hat{E}_{pq}+\kappa_{qp}\hat{E}_{qp}\right)+\sum_{p}\kappa_{pp}\hat{E}_{pp}
   
Now by employing the anti-Hermitian property:

.. math::
   \hat{\kappa}=\sum_{p>q}\left(\kappa_{pq}\hat{E}_{pq}-\kappa_{pq}^{*}\hat{E}_{qp}\right)+\sum_{p}\kappa_{pp}\hat{E}_{pp}
   
If it is known that the orbital rotations are real (this is not always the case), this can be simplified:

.. math::
   \hat{\kappa}=\sum_{p>q}\kappa_{pq}\left(\hat{E}_{pq}-\hat{E}_{qp}\right)
   
here it is used that :math:`Re\left(\kappa_{pq}^{*}\right)=Re\left(\kappa_{pq}\right)` and that :math:`Re\left(\kappa_{pp}\right)=Re\left(-\kappa_{pp}^{*}\right)=0`.
Now by :math:`\hat{E}_{pq}-\hat{E}_{qp}=\hat{E}_{pq}^{-}`:

.. math::
   \hat{\kappa}=\sum_{p>q}\kappa_{pq}\hat{E}_{pq}^{-}