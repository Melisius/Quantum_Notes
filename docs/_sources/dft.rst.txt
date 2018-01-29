
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
   
Since the reference wavefunction only holds electrons in the occupied orbitals, it can be seen that :math:`p`, :math:`q`, :math:`r` and :math:`s` most be indicies for occupied orbitals:

.. math::
   \begin{array}{ccc} E^{[0]} & = & \sum_{ij}h_{ij}\left\langle 0\left|i^{\dagger}j\right|0\right\rangle \\ & + & \frac{1}{2}\sum_{ijkl}\left(ik|jl\right)\left\langle 0\left|i^{\dagger}k\right|0\right\rangle \left\langle 0\left|j^{\dagger}l\right|0\right\rangle \\ & + & E_{xc}\left[\rho\right]+V_{NN} \end{array}
   
Now the only way that :math:`\left\langle 0\left|i^{\dagger}j\right|0\right\rangle` can be non-zero is if :math:`i=j`, and it thus equals one:

.. math::
   E^{[0]}=\sum_{i}h_{ii}+\frac{1}{2}\sum_{ij}\left(ii|jj\right)+E_{xc}\left[\rho\right]+V_{NN}

- Four-Component Relativistic Kohn-Sham Theory, Trond Saue og Trygve Helgaker.



