
MCSCF-srDFT
===========

Introduction
-------------

The method of MCSCF-srDFT is based on the separation of two electron integrals into a longe-range part and a short-range part. Now the regular two electron operator is given as:

.. math::
   w_{ee}\left(r_{12}\right)=r_{12}^{-1}
   
Now breaking it up into two parts gives:

.. math::
   w_{ee}\left(r_{12}\right)=w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)+w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)
   
Here lr is long-range, sr is short-range and :math:`\mu` is a paramter that controls where the longe-range and short-range interactions are separated. From Hohnenberg-Kohn it is known that the universal functional is defined as:

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

In MCSCF-srDFT, the two-electron integrals was separated into a long-range and a short-range part, defined by a parameter :math:`\mu`. A method of separation is by the error function, thus giving:

.. math::
   w_{ee}^{\mathrm{lr},\mu}\left(r_{12}\right)=\frac{\mathrm{erf}\left(r_{12}\mu\right)}{r_{12}}
   
and,

.. math::
   w_{ee}^{\mathrm{sr},\mu}\left(r_{12}\right)=\frac{1-\mathrm{erf}\left(r_{12}\mu\right)}{r_{12}}
   
It can be seen that for the long-range part and the short-range part being treated exact, that this reduces to the usual :math:`r_{12}^{-1}` behavior. Further it can be seen that for the limiting cases of :math:`\mu` gives:

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
   
Which is Kohn-Sham DFT. And:

.. math::
   \lim_{\mu\rightarrow\infty}E_{0}=\left\langle \Psi^{\infty}\left|\hat{T}+\hat{V}_{Ne}+r_{12}^{-1}\right|\Psi^{\infty}\right\rangle +0+0
   
Which is WFT.


TD-MC-srDFT two-state analysis
------------------------------

For now it is given that the linear response matrix elements, in the limit of :math:`\mu\rightarrow0` and with the disregarding of orbit rotations are constructed as:

.. math::
   A=\left(\begin{array}{cc} \left\langle 0\left|\left[R_{i},\left[\hat{H}^{\mathrm{KS}},R_{j}^{+}\right]\right]\right|0\right\rangle & \left\langle 0\left|\left[\left[R_{i},\hat{H}^{\mathrm{KS}}\right],R_{j}^{+}\right]\right|0\right\rangle \\ \left\langle 0\left|\left[R_{i},\left[H^{\mathrm{KS}},q_{j}^{+}\right]\right]\right|0\right\rangle & \left\langle 0\left|\left[R_{i},\left[\hat{H}^{\mathrm{KS}},R_{j}^{+}\right]\right]\right|0\right\rangle \end{array}\right)
   
.. math::
   B=\left(\begin{array}{cc} \left\langle 0\left|\left[R_{i},\left[\hat{H}^{\mathrm{KS}},R_{j}\right]\right]\right|0\right\rangle & \left\langle 0\left|\left[\left[R_{i},\hat{H}^{\mathrm{KS}}\right],R_{j}\right]\right|0\right\rangle \\ \left\langle 0\left|\left[R_{i},\left[\hat{H}^{\mathrm{KS}},R_{j}\right]\right]\right|0\right\rangle & \left\langle 0\left|\left[R_{i},\left[\hat{H}^{\mathrm{KS}},R_{j}\right]\right]\right|0\right\rangle \end{array}\right)
   
.. math::
   \Sigma=\left(\begin{array}{cc} \left\langle 0\left|\left[R_{i},R_{j}^{+}\right]\right|0\right\rangle & \left\langle 0\left|\left[R_{i},R_{j}^{+}\right]\right|0\right\rangle \\ \left\langle 0\left|\left[R_{i},R_{j}^{+}\right]\right|0\right\rangle & \left\langle 0\left|\left[R_{i},R_{j}^{+}\right]\right|0\right\rangle \end{array}\right)
   
.. math::
   \Delta=\left(\begin{array}{cc} \left\langle 0\left|\left[R_{i},R_{j}\right]\right|0\right\rangle & \left\langle 0\left|\left[R_{i},R_{j}\right]\right|0\right\rangle \\ \left\langle 0\left|\left[R_{i},R_{j}\right]\right|0\right\rangle & \left\langle 0\left|\left[R_{i},R_{j}\right]\right|0\right\rangle \end{array}\right)
   
Now lets consider an active space consisting of :math:`\left|a^{2}\right\rangle`  and :math:`\left|b^{2}\right\rangle` , where :math:`a^{2}` is being the double occupied orbital :math:`\phi_{a}`, and :math:`a^{2}` being the reference wavefunction. It is also known that :math:`R_{n}=\left|0\right\rangle \left\langle n\right|`. Now the matrix elements takes the form:

.. math::
   A=\left(\begin{array}{cc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & \left\langle a^{2}\left|\left[\left[R_{a^{2}},\hat{H}^{\mathrm{KS}}\right],R_{b^{2}}^{+}\right]\right|a^{2}\right\rangle \\ \left\langle 0\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|0\right\rangle & \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle \end{array}\right)
   
.. math::
   B=\left(\begin{array}{cc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle & \left\langle a^{2}\left|\left[\left[R_{a^{2}},\hat{H}^{\mathrm{KS}}\right],R_{b^{2}}\right]\right|a^{2}\right\rangle \\ \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle & \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle \end{array}\right)
   
.. math::
   \Sigma=\left(\begin{array}{cc} \left\langle a^{2}\left|\left[R_{a^{2}},R_{a^{2}}^{+}\right]\right|a^{2}\right\rangle & \left\langle a^{2}\left|\left[R_{a^{2}},R_{b^{2}}^{+}\right]\right|a^{2}\right\rangle \\ \left\langle a^{2}\left|\left[R_{b^{2}},R_{a^{2}}^{+}\right]\right|a^{2}\right\rangle & \left\langle a^{2}\left|\left[R_{b^{2}},R_{b^{2}}^{+}\right]\right|a^{2}\right\rangle \end{array}\right)
   
.. math::
   \Delta=\left(\begin{array}{cc} \left\langle a^{2}\left|\left[R_{a^{2}},R_{a^{2}}\right]\right|a^{2}\right\rangle & \left\langle a^{2}\left|\left[R_{a^{2}},R_{b^{2}}\right]\right|a^{2}\right\rangle \\ \left\langle a^{2}\left|\left[R_{b^{2}},R_{a^{2}}\right]\right|a^{2}\right\rangle & \left\langle a^{2}\left|\left[R_{b^{2}},R_{b^{2}}\right]\right|a^{2}\right\rangle \end{array}\right)
   
Now lets evaluate :math:`\Delta` element wise:

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},R_{a^{2}}\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}R_{a^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{a^{2}}\right|a^{2}\right\rangle =0
   
and, 

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},R_{b^{2}}\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}R_{b^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{b^{2}}R_{a^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},R_{b^{2}}\right]\right|a^{2}\right\rangle =\left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle -\left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle =0
   
since :math:`\left\langle \left.b^{2}\right|a^{2}\right\rangle =0`, because :math:`a^{2}` and :math:`b^{2}` are orthogonal. By same argument:

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},R_{a^{2}}\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},R_{b^{2}}\right]\right|a^{2}\right\rangle =0
   
Giving:

.. math::
   \Delta=\left(\begin{array}{cc} 0 & 0\\ 0 & 0 \end{array}\right)
   
Now the evaluation of :math:`\Sigma`:

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},R_{a^{2}}^{+}\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}R_{a^{2}}^{\dagger}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}^{\dagger}R_{a^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},R_{a^{2}}^{+}\right]\right|a^{2}\right\rangle =\left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle -\left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle =0
   
and,

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},R_{b^{2}}^{+}\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}R_{b^{2}}^{\dagger}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{b^{2}}^{\dagger}R_{a^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},R_{b^{2}}^{+}\right]\right|a^{2}\right\rangle =\left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle -\left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle =0
   
and as above,

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},R_{a^{2}}^{+}\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},R_{b^{2}}^{+}\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{b^{2}}R_{b^{2}}^{\dagger}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{b^{2}}^{\dagger}R_{b^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},R_{b^{2}}^{+}\right]\right|a^{2}\right\rangle =\left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle -\left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle =1
   
Giving:

.. math::
   \Sigma=\left(\begin{array}{cc} 0 & 0\\ 0 & 1 \end{array}\right)
   
For :math:`A` and :math:`B` the Hamiltonian is given as, :math:`\hat{H}^{\mathrm{KS}}=\hat{T}+\hat{V}_{Ne}+\hat{V}_{Hxc}\left[n_{a}\right]`. It is known that for this Hamiltonian that, :math:`\hat{H}^{\mathrm{KS}}\left|i^{2}\right\rangle =2\epsilon_{i}\left|i^{2}\right\rangle` . Now evaluating :math:`B`:

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{a^{2}}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{a^{2}}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{b^{2}}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle =-\left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle +\left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle =0
   
and by similar argument:

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{b^{2}}R_{b^{2}}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}R_{b^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle =0
   
Giving:

.. math::
   B=\left(\begin{array}{cc} 0 & 0\\ 0 & 0 \end{array}\right)
   
Now evaluating :math:`A`:

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}^{+}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{a^{2}}^{+}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{a^{2}}^{+}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{a^{2}}^{+}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle 
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle =0
   
by a similar argument:

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle =0
   
and,

.. math::
  \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{b^{2}}R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}R_{b^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle 
  
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle =2\left(\epsilon_{b}-\epsilon_{a}\right)
   
Giving:

.. math::
   A=\left(\begin{array}{cc} 0 & 0\\ 0 & 2\left(\epsilon_{b}-\epsilon_{a}\right) \end{array}\right)
   
Per definition of the basis, it was such that :math:`a^{2}` and :math:`b^{2}` is different in two-electrons. Since not all of the above matrices equals zero, it can be thought that this double excitation, :math:`a^{2}\rightarrow b^{2}`, is described, even in the limit of :math:`\mu\rightarrow0` (and ignoring orbital rotations). This double excitation have the energy equal two two times the orbital difference. It can thus be seen that TD-MC-srDFT does not reduce to standard DFT, were such a double excitation would not be included, in the limit of :math:`\mu\rightarrow0`. 

- Multi-configuration time-dependent density-functional theory based on range separation, Emmanuel Fromager, Stefan Knecht og Hans Jørgen Aa. Jensen.
