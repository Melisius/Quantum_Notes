
Density Functional Theory
=========================

Density matrix expansion
------------------------
 
The density matrix is given as:

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle \tilde{0}\left|p^{\dagger}q\right|\tilde{0}\right\rangle =\left\langle 0\left|\exp\left(\hat{\kappa}\right)p^{\dagger}q\exp\left(-\hat{\kappa}\right)\right|0\right\rangle 
  
The BCH expansion is given as:

.. math::
   \exp\left(A\right)B\exp\left(-A\right)=B+\left[A,B\right]+\frac{1}{2!}\left[A,\left[A,B\right]\right]+...
   
If :math:`A=\hat{\kappa}` and :math:`B=p^{\dagger}q`, it can be written that:

.. math::
   \tilde{D}_{pq}\left(A\right)=\left\langle 0\left|B\right|0\right\rangle +\left\langle 0\left|\left[A,B\right]\right|0\right\rangle +O\left(A^{2}\right)

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle 0\left|p^{\dagger}q\right|0\right\rangle +\left\langle 0\left|\left[\hat{\kappa},p^{\dagger}q\right]\right|0\right\rangle +O\left(\kappa^{2}\right)

It can now be used that:

.. math::
   \hat{\kappa}=\sum_{pq}\kappa_{pq}p^{\dagger}q

Thus giving:

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle 0\left|p^{\dagger}q\right|0\right\rangle +\left\langle 0\left|\left[\sum_{rs}\kappa_{rs}r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle +O\left(\kappa^{2}\right)
   
Since :math:`\kappa_{rs}` is just a matrix element, the above equation can rewritten as:

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle 0\left|p^{\dagger}q\right|0\right\rangle +\sum_{rs}\left\langle 0\left|\left[r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle \kappa_{rs}+O\left(\kappa^{2}\right)