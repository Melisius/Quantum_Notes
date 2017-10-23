

short-ranged Density Functional Theory
======================================

Electronic Gradient
-------------------

The short-range exchange-correlation to the gradient is found as:

.. math::
   g_{\mathrm{sr-xc},i}=\frac{\partial E_{\mathrm{sr-xc}}\left[\rho_{C},\rho_{S}\right]}{\partial\lambda_{i}}=\int\frac{\partial e_{\mathrm{sr-xc}}\left(\rho_{C}\left(r\right),\rho_{S}\left(r\right)\right)}{\partial\lambda_{i}}dr
   
Now the part inside the integral can be written out using the chain-rule:

.. math::
   \frac{\partial h\left(g\left(x\right),f\left(x\right)\right)}{\partial\lambda}=\frac{\partial h}{\partial g}\frac{\partial g}{\partial\lambda}+\frac{\partial h}{\partial f}\frac{\partial f}{\partial\lambda}

Using the notation :math:`\rho_{X}=\sum_{pq}\Omega_{pq}D_{pq}^{x}\left(\lambda\right)`, the derivative of :math:`\rho_{X}` is:

.. math::
   \frac{\partial\rho_{X}}{\partial\lambda}=\sum_{pq}\Omega_{pq}\frac{\partial D_{pq}^{X}}{\partial\lambda}

Now by identifying that :math:`h=e_{\mathrm{sr-xc}}`, :math:`g=\rho_{C}` and :math:`f=\rho_{S}` it can be written that:

.. math::
   \frac{\partial e_{\mathrm{sr-xc}}\left(\rho_{C}\left(r\right),\rho_{S}\left(r\right)\right)}{\partial\lambda_{i}}=\frac{\partial e_{\mathrm{sr-xc}}}{\partial\rho_{C}}\sum_{pq}\Omega_{pq}\frac{\partial D_{pq}^{C}}{\partial\lambda}+\frac{\partial e_{\mathrm{sr-xc}}}{\partial\rho_{S}}\sum_{pq}\Omega_{pq}\frac{\partial D_{pq}^{S}}{\partial\lambda}
   
Now it can be defined that:

.. math::
   g_{\mathrm{sr-xc},pq}^{C}=\int\frac{\partial e_{\mathrm{sr-xc}}}{\partial\rho_{C}}\sum_{pq}\Omega_{pq}\frac{\partial D_{pq}^{C}}{\partial\lambda}dr

.. math::
   g_{\mathrm{sr-xc},pq}^{S}=\int\frac{\partial e_{\mathrm{sr-xc}}}{\partial\rho_{S}}\sum_{pq}\Omega_{pq}\frac{\partial D_{pq}^{S}}{\partial\lambda}dr

Leading to the total gradient of the orbital rotation parameters being:

.. math::
   \frac{\partial E_{\mathrm{sr-xc}}\left[\rho_{C},\rho_{S}\right]}{\partial\kappa_{rs}}=g_{\mathrm{sr-xc},rs}^{C}+g_{\mathrm{sr-xc},rs}^{S}

An effective operator can be defined:

.. math::
   \hat{V}_{\mathrm{sr-xc}}^{X,g}=\sum_{pq}\int\frac{\partial e_{\mathrm{sr-xc}}}{\partial\rho_{X}}\Omega_{pq}dr\hat{O}_{pq}^{X}

With :math:`\hat{O}_{pq}^{X}` being singlet and triplet excitation operator for :math:`C` and :math:`S`. Now leading to:

.. math::
   g_{\mathrm{sr-xc},rs}^{C}=\left\langle 0\left|\left[E_{rs}^{-},\hat{V}_{\mathrm{sr-xc}}^{C,g}\right]\right|0\right\rangle 
   
.. math::
   g_{\mathrm{sr-xc},rs}^{C}=\left\langle 0\left|E_{rs}^{-}\hat{V}_{\mathrm{sr-xc}}^{C,g}\right|0\right\rangle -\left\langle 0\left|\hat{V}_{\mathrm{sr-xc}}^{C,g}E_{rs}^{-}\right|0\right\rangle 

If :math:`V` is Hermitian i.e. :math:`V=V^{\dagger}`, it can be written that:

.. math::
   g_{\mathrm{sr-xc},rs}^{C}=\left\langle 0\left|E_{rs}^{-}\hat{V}_{\mathrm{sr-xc}}^{C,g}\right|0\right\rangle -\left\langle 0\left|E_{rs}^{-\dagger}\hat{V}_{\mathrm{sr-xc}}^{C,g}\right|0\right\rangle 
   
Now :math:`E_{rs}^{-\dagger}` can be expanded as:

.. math::
   E_{rs}^{-\dagger}=\left(E_{rs}-E_{sr}\right)^{\dagger}=E_{rs}-E_{sr}=E_{sr}^{-}=-E_{rs}^{-}

Now giving:

.. math::
   g_{\mathrm{sr-xc},rs}^{C}=\left\langle 0\left|E_{rs}^{-}\hat{V}_{\mathrm{sr-xc}}^{C,g}\right|0\right\rangle +\left\langle 0\left|E_{rs}^{-}\hat{V}_{\mathrm{sr-xc}}^{C,g}\right|0\right\rangle 

.. math::
   g_{\mathrm{sr-xc},rs}^{C}=2\left\langle 0\left|E_{rs}^{-}\hat{V}_{\mathrm{sr-xc}}^{C,g}\right|0\right\rangle 

To be continued