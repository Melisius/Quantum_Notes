
Density Functional Theory
=========================

Introduction
------------

In the formalism of Kohn-Sham DFT the energy can be expressed as:

.. math::
   E\left[\rho\right]=T\left[\rho\right]+V^{\mathrm{ext}}\left[\rho\right]+J\left[\rho\right]+E_{xc}\left[\rho\right]+V_{NN}
   
Here :math:`\rho` is the electron density. :math:`V_{NN}` is the nuclei-nuclei interaction, thus is does not depend on the electron density. The first term is the kinetic energy, it have an expressed similar to that of Hartree-Fock:

.. math::
   T\left[\rho\right]=\int\phi\left(r\right)\left(-\nabla^{2}\right)\phi\left(r\right)dr
   
The second term is the electron interaction with an external field. Here it should be noted that the field on the electrons by the nuclei is thought of as an external field. It is given as:

.. math::
   V^{\mathrm{ext}}\left[\rho\right]=\int\hat{V}^{\mathrm{ext}}\left(r\right)\rho\left(r\right)dr
   
The third term is the coulomb interaction of the electron density with the electron density. This term is also known as the Hartree term. And is given as:

.. math::
   J\left[\rho\right]=\frac{1}{2}\int\int\frac{\rho\left(r_{1}\right)\rho\left(r_{2}\right)}{r_{12}}dr_{1}dr_{2}
   
The last term is the exchange-correlation term. This term deals with the electron exchange and electron correlation (that is not included in the Hartree term). Just as in Hartree-Fock the determinant of the Kohn-Sham equations, the Kohn-Sham determinant, can be parametrize by unitary orbital-rotations, such that:

.. math::
   \left|\tilde{0}\right\rangle =\exp\left(-\hat{\kappa}\right)\left|0\right\rangle 
   
with,

.. math::
   \hat{\kappa}=\sum_{pq}\kappa_{pq}p^{\dagger}q
   
By this parameterization the density will now depend on both the spacial placement and on the orbital rotation. The density can be expressed as:

.. math::
   \rho\left(r,\kappa\right)=\sum_{pq}\tilde{D}_{pq}\left(\kappa\right)\Omega_{pq}\left(r\right)
   
Here :math:`\tilde{D}_{pq}\left(\kappa\right)` is the density matrix of the orbital-rotation parameterized Kohn-Sham orbitals, thus given as:

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle \tilde{0}\left|p^{\dagger}q\right|\tilde{0}\right\rangle =\left\langle 0\left|\exp\left(\hat{\kappa}\right)p^{\dagger}q\exp\left(-\hat{\kappa}\right)\right|0\right\rangle 
   
:math:`\Omega_{pq}\left(r\right)` is an overlap distribution, thus simply given as:

.. math::
   \Omega_{pq}\left(r\right)=\phi_{p}^{\dagger}\left(r\right)\phi_{q}\left(r\right)
   
By the above definition of the electron density, it is possible to express the energy in terms of the density matrix and the overlap distribution:

.. math::
   \begin{array}{ccc} E\left[\rho\right] & = & \sum_{pq}\left[\int\phi\left(r\right)\left(-\nabla^{2}\right)\phi\left(r\right)dr-\sum_{N}Z_{N}\int\frac{\Omega_{pq}\left(r\right)}{r_{N}}dr\right]\tilde{D}_{pq}\left(\kappa\right)\\ & + & \frac{1}{2}\sum_{pqrs}\int\int\frac{\Omega_{pq}\left(r_{1}\right)\Omega_{rs}\left(r_{2}\right)}{r_{12}}dr_{1}dr_{2}\tilde{D}_{pq}\left(\kappa\right)\tilde{D}_{rs}\left(\kappa\right)+E_{xc}\left[\rho\right]+V_{NN} \end{array}
   
Here the external potential have been assumed to only excerted by the nuclei. Notice that no new information have been gathered about the exchange-correlation functional. By standard notation this can be shortened to:

.. math::
   \begin{array}{ccc} E\left[\rho\right] & = & \sum_{pq}h_{pq}\tilde{D}_{pq}\left(\kappa\right)\\ & + & \frac{1}{2}\sum_{pqrs}\left(pq|rs\right)\tilde{D}_{pq}\left(\kappa\right)\tilde{D}_{rs}\left(\kappa\right)+E_{xc}\left[\rho\right]+V_{NN} \end{array}
   
With,

.. math::
   h_{pq}=\int\phi\left(r\right)\left(-\nabla^{2}\right)\phi\left(r\right)dr-\sum_{N}Z_{N}\int\frac{\Omega_{pq}\left(r\right)}{r_{N}}dr
   
and,

.. math::
   \left(pq|rs\right)=\int\int\frac{\Omega_{pq}\left(r_{1}\right)\Omega_{rs}\left(r_{2}\right)}{r_{12}}dr_{1}dr_{2}

- Four-Component Relativistic Kohn-Sham Theory, Trond Saue og Trygve Helgaker.

Energy Expansion
----------------

The Kohn-Sham energy can be expanded with respect to the orbital-rotations. Here the Taylor series of the KS energy around :math:`\kappa=0`:

.. math::
   E\left(\kappa\right)=E\left[\rho\left(\kappa\right)\right]+\sum_{pq}\frac{\partial E\left[\rho\left(\kappa\right)\right]}{\partial\kappa_{pq}}\kappa_{pq}+\mathcal{O}\left(\kappa^{2}\right)
   
This notation can be shortened:

.. math::
   E\left(\kappa\right)=E^{[0]}+\sum_{pq}E_{pq}^{[1]}\kappa_{pq}+\mathcal{O}\left(\kappa^{2}\right)
   
with the superscript indication the order of derivative with respect to \kappa. The density matrix can also by expanded, by using the BCH expansion:

.. math::
   \tilde{D}_{pq}=\left\langle 0\left|p^{\dagger}q\right|0\right\rangle +\sum_{rs}\left\langle 0\left|\left[p^{\dagger}q,r^{\dagger}s\right]\right|0\right\rangle \kappa_{rs}+\mathcal{O}\left(\kappa^{2}\right)
   
If the zero'th order term of the density matrix is associated with the zero'th order term of the energy, it can be written that:

.. math::
   \begin{array}{ccc} E^{[0]} & = & \sum_{pq}h_{pq}\left\langle 0\left|p^{\dagger}q\right|0\right\rangle \\ & + & \frac{1}{2}\sum_{pqrs}\left(pq|rs\right)\left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \\ & + & E_{xc}\left[\rho\right]+V_{NN} \end{array}
   
Since the reference wave function only holds electrons in the occupied orbitals, it can be seen that :math:`p`, :math:`q`, :math:`r` and :math:`s` most be indicies for occupied orbitals:

.. math::
   \begin{array}{ccc} E^{[0]} & = & \sum_{ij}h_{ij}\left\langle 0\left|i^{\dagger}j\right|0\right\rangle \\ & + & \frac{1}{2}\sum_{ijkl}\left(ik|jl\right)\left\langle 0\left|i^{\dagger}k\right|0\right\rangle \left\langle 0\left|j^{\dagger}l\right|0\right\rangle \\ & + & E_{xc}\left[\rho\right]+V_{NN} \end{array}
   
Now the only way that :math:`\left\langle 0\left|i^{\dagger}j\right|0\right\rangle` can be non-zero is if :math:`i=j`, and it thus equals one:

.. math::
   E^{[0]}=\sum_{i}h_{ii}+\frac{1}{2}\sum_{ij}\left(ii|jj\right)+E_{xc}\left[\rho\right]+V_{NN}
   
**Seem to be of wrong sign for the first two terms**
Now if the first order term of the density matrix is associated with the first order term of the energy:

.. math::
   \begin{array}{ccc} E^{[1]} & = & \sum_{pq}h_{pq}\frac{\partial\tilde{D}_{pq}}{\partial\kappa_{rs}}\\ & + & \frac{1}{2}\frac{\partial}{\partial\kappa_{RS}}\sum_{pqrs}\left(pq|rs\right)\tilde{D}_{pq}\tilde{D}_{rs}\\ & + & \frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{rs}}+\frac{\partial V_{NN}}{\partial\kappa_{rs}} \end{array}
   
By expanding with the chain-rule:

.. math::
   \begin{array}{ccc} E^{[1]} & = & \sum_{pq}h_{pq}\frac{\partial\tilde{D}_{pq}}{\partial\kappa_{rs}}\\ & + & \frac{1}{2}\sum_{pqrs}\left(pq|rs\right)\left\{ \frac{\partial\tilde{D}_{pq}}{\partial\kappa_{RS}}\tilde{D}_{rs}+\tilde{D}_{pq}\frac{\partial\tilde{D}_{rs}}{\partial\kappa_{RS}}\right\} \\ & + & \frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{rs}}+\frac{\partial V_{NN}}{\partial\kappa_{rs}} \end{array}
   
By expanding the derivatives:

.. math::
   \begin{array}{ccc} E^{[1]} & = & \sum_{pq}h_{pq}\left\langle 0\left|\left[r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle \\ & + & \frac{1}{2}\sum_{pqrs}\left(pq|rs\right)\left\{ \left\langle 0\left|\left[R^{\dagger}S,p^{\dagger}q\right]\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \right.\\ & + & \left.\left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|\left[R^{\dagger}S,r^{\dagger}s\right]\right|0\right\rangle \right\} \\ & + & \frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{rs}}+\frac{\partial V_{NN}}{\partial\kappa_{rs}} \end{array}
   
Since the nuclear-nuclear repulsion does not depend on :math:`\kappa` this term will vanish. For the two electron part, the terms coming from :math:`\sum_{rs}\left\langle 0\left|\left[r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle \kappa_{rs}\sum_{r's'}\left\langle 0\left|\left[r'^{\dagger}s',p'^{\dagger}q'\right]\right|0\right\rangle \kappa_{r's'}` are not included, because these will be of second order in :math:`\kappa`. The derivative of the exchange-correlation functional will be dealt with after the one and two electron part. The relation :math:`\left[p^{\dagger}q,r^{\dagger}s\right]=p^{\dagger}s\delta_{qr}-r^{\dagger}q\delta_{ps}` can now be used:

.. math::
   \begin{array}{ccc} E^{[1]} & = & \sum_{pq}h_{pq}\left\{ \left\langle 0\left|r^{\dagger}q\right|0\right\rangle \delta_{ps}-\left\langle 0\left|p^{\dagger}s\right|0\right\rangle \delta_{qr}\right\} \\ & + & \frac{1}{2}\sum_{pqrs}\left(pq|rs\right)\left\{ \left\langle 0\left|R^{\dagger}q\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{pS}\right.\\ & - & \left\langle 0\left|p^{\dagger}S\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{Rq}\\ & + & \left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|R^{\dagger}s\right|0\right\rangle \delta_{rS}\\ & - & \left.\left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|r^{\dagger}S\right|0\right\rangle \delta_{Rs}\right\} \\ & + & \frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{rs}} \end{array}
   
It can now be seen that if :math:`\kappa\equiv\kappa_{ij}` that all of the terms equal zero, since:

.. math::
   \left\langle 0\left|i^{\dagger}q\right|0\right\rangle \delta_{pj}-\left\langle 0\left|p^{\dagger}j\right|0\right\rangle \delta_{qi}=\left\langle 0\left|i^{\dagger}i\right|0\right\rangle \delta_{jj}-\left\langle 0\left|j^{\dagger}j\right|0\right\rangle \delta_{ii}=0
   
and,

.. math::
   \begin{array}{cc} & \left\langle 0\left|i^{\dagger}q\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{pj}\\ - & \left\langle 0\left|p^{\dagger}j\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{iq}\\ + & \left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|i^{\dagger}s\right|0\right\rangle \delta_{rj}\\ - & \left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|r^{\dagger}j\right|0\right\rangle \delta_{is} \end{array}
   
Equals:

.. math::
   \begin{array}{cc} & \left\langle 0\left|i^{\dagger}i\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{jj}\\ - & \left\langle 0\left|j^{\dagger}j\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{ii}\\ + & \left\langle 0\left|j^{\dagger}i\right|0\right\rangle \left\langle 0\left|i^{\dagger}s\right|0\right\rangle \delta_{rj}\\ - & \left\langle 0\left|j^{\dagger}i\right|0\right\rangle \left\langle 0\left|r^{\dagger}j\right|0\right\rangle \delta_{is} \end{array}
   
Equals:

.. math::
   \begin{array}{cc} & \left\langle 0\left|i^{\dagger}i\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{jj}\\ - & \left\langle 0\left|j^{\dagger}j\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{ii}\\ + & 0\\ - & 0\\ = & 0 \end{array}
   
The same argument can be made for :math:`\kappa\equiv\kappa_{ab}`. Now for :math:`\kappa\equiv\kappa_{ia}`:

.. math::
   \begin{array}{ccc} E^{[1]} & = & \sum_{pq}h_{pq}\left\{ \left\langle 0\left|i^{\dagger}q\right|0\right\rangle \delta_{pa}-\left\langle 0\left|p^{\dagger}a\right|0\right\rangle \delta_{qi}\right\} \\ & + & \frac{1}{2}\sum_{pqrs}\left(pq|rs\right)\left\{ \left\langle 0\left|i^{\dagger}q\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{pa}\right.\\ & - & \left\langle 0\left|p^{\dagger}a\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{iq}\\ & + & \left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|i^{\dagger}s\right|0\right\rangle \delta_{ra}\\ & - & \left.\left\langle 0\left|p^{\dagger}q\right|0\right\rangle \left\langle 0\left|r^{\dagger}a\right|0\right\rangle \delta_{is}\right\} \\ & + & \frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{ia}} \end{array}
   
Now by letting the two first :math:`\delta` equal to one:

.. math::
   \begin{array}{ccc} E^{[1]} & = & \sum_{ai}h_{ai}\left\{ \left\langle 0\left|i^{\dagger}i\right|0\right\rangle \delta_{aa}-\left\langle 0\left|a^{\dagger}a\right|0\right\rangle \delta_{ii}\right\} \\ & + & \frac{1}{2}\sum_{airs}\left(pq|rs\right)\left\{ \left\langle 0\left|i^{\dagger}i\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{aa}\right.\\ & - & \left\langle 0\left|a^{\dagger}a\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{ii}\\ & + & \left\langle 0\left|a^{\dagger}i\right|0\right\rangle \left\langle 0\left|i^{\dagger}s\right|0\right\rangle \delta_{ra}\\ & - & \left.\left\langle 0\left|a^{\dagger}i\right|0\right\rangle \left\langle 0\left|r^{\dagger}a\right|0\right\rangle \delta_{is}\right\} \\ & + & \frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{ia}} \end{array}
   
Thus giving:

.. math::
   \begin{array}{ccc} E^{[1]} & = & \sum_{ai}h_{ai}\left\{ \left\langle 0\left|i^{\dagger}i\right|0\right\rangle \delta_{aa}-\left\langle 0\left|a^{\dagger}a\right|0\right\rangle \delta_{ii}\right\} \\ & + & \frac{1}{2}\sum_{airs}\left(pq|rs\right)\left\{ \left\langle 0\left|i^{\dagger}i\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{aa}\right.\\ & - & \left.\left\langle 0\left|a^{\dagger}a\right|0\right\rangle \left\langle 0\left|r^{\dagger}s\right|0\right\rangle \delta_{ii}\right\} \\ & + & \frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{ia}} \end{array}
   
It can now be seen that :math:`r` must be equal to :math:`s` and must be of an occupied type:

.. math::
   E^{[1]}=\sum_{ai}h_{ai}+\frac{1}{2}\sum_{aij}\left(pq|jj\right)+\frac{\partial E_{xc}\left[\rho\right]}{\partial\kappa_{ia}}
   
**First term seem to be of wrong sign, and second term seem to be a factor -2 wrong**
Now only the last term need to be evaluated. The expansion of exchange-correlation energy density is simply:

.. math::
   e_{xc}\left(\rho,\zeta\right)=e_{xc}\left(\rho_{0},\zeta_{0}\right)+\sum_{rs}\frac{\partial e_{xc}\left(\rho,\zeta\right)}{\partial\kappa_{rs}}\kappa_{rs}+\mathcal{O}\left(\kappa^{2}\right)

Which can be reduced to:

.. math::
   e_{xc}\left(\rho,\zeta\right)=e_{xc}\left(\rho_{0},\zeta_{0}\right)+\sum_{pqrs}\left\langle 0\left|\left[r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle \left\{ \frac{\partial e_{xc}}{\partial\rho}\Omega_{pq}+2\frac{\partial e_{xc}}{\partial\zeta}\left(\nabla\rho_{0}\nabla\Omega_{pq}\right)\right\} \kappa_{rs}+\mathcal{O}\left(\kappa^{2}\right)
   
As before the term :math:`\left\langle 0\left|\left[r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle`  will only be non-zero for :math:`\kappa\equiv\kappa_{ia}`, now giving:

.. math::
   \frac{\partial e_{xc}\left(\rho,\zeta\right)}{\partial\kappa_{ia}}=\sum_{pq}\left\langle 0\left|\left[i^{\dagger}a,p^{\dagger}q\right]\right|0\right\rangle \left\{ \frac{\partial e_{xc}}{\partial\rho}\Omega_{pq}+2\frac{\partial e_{xc}}{\partial\zeta}\left(\nabla\rho_{0}\nabla\Omega_{pq}\right)\right\} 
   
.. math::
   \frac{\partial e_{xc}\left(\rho,\zeta\right)}{\partial\kappa_{ia}}=\sum_{ai}\left\{ \left\langle 0\left|i^{\dagger}i\right|0\right\rangle \delta_{aa}-\left\langle 0\left|a^{\dagger}a\right|0\right\rangle \delta_{ii}\right\} \left\{ \frac{\partial e_{xc}}{\partial\rho}\Omega_{ai}+2\frac{\partial e_{xc}}{\partial\zeta}\left(\nabla\rho_{0}\nabla\Omega_{ai}\right)\right\} 
   
.. math::
   \frac{\partial e_{xc}\left(\rho,\zeta\right)}{\partial\kappa_{ia}}=\sum_{ai}\left\{ \frac{\partial e_{xc}}{\partial\rho}\Omega_{ai}+2\frac{\partial e_{xc}}{\partial\zeta}\left(\nabla\rho_{0}\nabla\Omega_{ai}\right)\right\} 

- Four-Component Relativistic Kohn-Sham Theory, Trond Saue og Trygve Helgaker.



