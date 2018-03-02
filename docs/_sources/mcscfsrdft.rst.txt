
MCSCF-srDFT
===========

Introduction
-------------

The method of MCSCF-srDFT is based on the separation of two electron integrals into a long-range part and a short-range part. 
Now the regular two electron operator is given as:

.. math::
   w_{ee}\left(r_{12}\right)=r_{12}^{-1}
   
Now breaking it up into two parts gives:

.. math::
   w_{ee}\left(r_{12}\right)=w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)+w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)
   
Here lr is long-range, sr is short-range and :math:`\mu` is a parameter that controls where the long-range and short-range interactions are separated. 
From Hohnenberg-Kohn it is known that the universal functional is defined as:

.. math::
   F\left[n\right]=\min_{\Psi\rightarrow n}\left\langle \Psi\left|\hat{T}+\hat{W}_{ee}\right|\Psi\right\rangle 
   
for,

.. math::
   \hat{W}_{ee}=\frac{1}{2}\sum_{i\neq j}w_{ee}\left(r_{ij}\right)
   
This gives rise to:

.. math::
   \hat{W}_{ee}=\hat{W}_{ee}^{\mathrm{lr},\mu}+\hat{W}_{ee}^{\mathrm{sr},\mu}=\frac{1}{2}\sum_{i\neq j}w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)+\frac{1}{2}\sum_{i\neq j}w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)
   
A separation of the universal functional into a long-range and a short-range part should also be possible:

.. math::
   F\left[n\right]=F^{\mathrm{lr},\mu}\left[n\right]+F^{\mathrm{sr},\mu}\left[n\right]
   
Here:

.. math::
   F^{\mathrm{lr},\mu}\left[n\right]=\min_{\Psi\rightarrow n}\left\langle \Psi\left|\hat{T}+\hat{W}_{ee}^{\mathrm{lr},\mu}\right|\Psi\right\rangle 

and,

.. math::
   F^{\mathrm{sr},\mu}\left[n\right]=E_{H}^{\mathrm{sr},\mu}\left[n\right]+E_{xc}^{\mathrm{sr},\mu}\left[n\right]
   
Here :math:`E_{H}^{\mathrm{sr},\mu}` is the Hartree term and :math:`E_{xc}^{\mathrm{sr},\mu}` is the exchange-correlation term, both given as short-range. Now the ground state energy can be expresesd accourding to the variational principle:

.. math::
   E_{0}=\min_{n}\left\{ F\left[n\right]+\int v_{Ne}\left(r\right)n\left(r\right)dr\right\} 
   
Giving:

.. math::
   E_{0}=\min_{\Psi}\left\{ \left\langle \Psi\left|\hat{T}+\hat{V}_{Ne}+\hat{W}_{ee}^{\mathrm{lr},\mu}\right|\Psi\right\rangle +E_{H}^{\mathrm{sr},\mu}\left[n_{\Psi}\right]+E_{xc}^{\mathrm{sr},\mu}\left[n_{\Psi}\right]\right\} 
   
.. math::
   E_{0}=\left\langle \Psi^{\mu}\left|\hat{T}+\hat{V}_{Ne}+\hat{W}_{ee}^{\mathrm{lr},\mu}\right|\Psi^{\mu}\right\rangle +E_{H}^{\mathrm{sr},\mu}\left[n_{\Psi^{\mu}}\right]+E_{xc}^{\mathrm{sr},\mu}\left[n_{\Psi^{\mu}}\right]

Similarly as Kohn-Sham DFT this leads to a self-consistent equation:

.. math::
   \left(\hat{T}+\hat{V}_{Ne}+\hat{W}_{ee}^{\mathrm{lr},\mu}+\hat{V}_{Hxc}^{\mathrm{sr},\mu}\left[n_{\Psi^{\mu}}\right]\right)\left|\Psi^{\mu}\right\rangle =\epsilon^{\mu}\left|\Psi^{\mu}\right\rangle 
   
Here :math:`\hat{V}_{\mathrm{Hxc}}^{\mathrm{sr},\mu}\left[n_{\Psi^{\mu}}\right]` is the potential energy functional, defined as:

.. math::
   \hat{V}_{Hxc}^{\mathrm{sr},\mu}\left[n_{\Psi^{\mu}}\right]=\int v_{Hxc}\left[n_{\Psi^{\mu}}\right]\left(r\right)dr
   
with,

.. math::
   v_{Hxc}\left[n_{\Psi^{\mu}}\right]\left(r\right)=\frac{\delta\left(E_{H}^{\mathrm{sr},\mu}+E_{xc}^{\mathrm{sr},\mu}\right)}{\delta n\left(r\right)}\left[n_{\Psi^{\mu}}\right]
   
- On the universality of the long-/short-range separation in multiconfigurational densityfunctional theory, Emmanuel Fromager, Julien Toulouse, and Hans Jørgen Aa. Jensen

- On the universality of the long-/short-range separation in multiconfigurational densityfunctional theory. II. Investigating :math:`f^{0}` actinide species, Emmanuel Fromager, Florent Réal, Pernilla Wåhlin, Ulf Wahlgren, and Hans Jørgen Aa. Jensen
   

Range separation parameter
--------------------------

In MCSCF-srDFT, the two-electron integrals was separated into a long-range and a short-range part, defined by a parameter :math:`\mu`. 
A method of separation is by the error function, thus giving:

.. math::
   w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)=\frac{\mathrm{erf}\left(r_{12}\mu\right)}{r_{12}}
   
and,

.. math::
   w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)=\frac{1-\mathrm{erf}\left(r_{12}\mu\right)}{r_{12}}
   
It can be seen that for the long-range part and the short-range part being treated exact, that this reduces to the usual :math:`r_{12}^{-1}` behavior. 
Further it can be seen that for the limiting cases of :math:`\mu` gives:

.. math::
   \lim_{\mu\rightarrow0}w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)=0\,\,\,\,\,\,\lim_{\mu\rightarrow\infty}w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)=r_{12}^{-1}
   
.. math::
   \lim_{\mu\rightarrow0}w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)=r_{12}^{-1}\,\,\,\,\,\,\lim_{\mu\rightarrow\infty}w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)=0

The ground state energy was found as:

.. math::
   E_{0}=\left\langle \Psi^{\mu}\left|\hat{T}+\hat{V}_{Ne}+\hat{W}_{ee}^{\mathrm{lr},\mu}\right|\Psi^{\mu}\right\rangle +E_{H}^{\mathrm{sr},\mu}\left[n_{\Psi^{\mu}}\right]+E_{xc}^{\mathrm{sr},\mu}\left[n_{\Psi^{\mu}}\right]
   
Now if the limiting case of :math:`\mu`, it can be seen the above reduces to:

.. math::
   \lim_{\mu\rightarrow0}E_{0}=\left\langle \Psi^{0}\left|\hat{T}+\hat{V}_{Ne}+0\right|\Psi^{0}\right\rangle +E_{H}^{\mathrm{sr},0}\left[n_{\Psi^{0}}\right]+E_{xc}^{\mathrm{sr},0}\left[n_{\Psi^{0}}\right]
   
Which is Kohn-Sham DFT. 
And:

.. math::
   \lim_{\mu\rightarrow\infty}E_{0}=\left\langle \Psi^{\infty}\left|\hat{T}+\hat{V}_{Ne}+r_{12}^{-1}\right|\Psi^{\infty}\right\rangle +0+0
   
Which is WFT. 
Another used range separation is the erf-gau separation.
The erf-gau separation is given as:

.. math::
   w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)=\frac{\mathrm{erf}\left(r_{12}\mu\right)}{r_{12}}-\frac{2\mu}{\sqrt{\pi}}\exp\left(-\frac{1}{3}\mu^{2}r^{2}\right)
   
and,

.. math::
   w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)=1-w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)
   
This separation also fulfills the limits of DFT and WFT.
