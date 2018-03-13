
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
   

Hessian Transformation
----------------------

The MCSCF Hessian have the form:

.. math::
   \overline{\overline{K}}=\left(\begin{array}{cc}
   ^{\mathrm{cc}}\overline{\overline{K}}^{(2)} & ^{\mathrm{co}}\overline{\overline{K}}^{(2)}\\
   ^{\mathrm{oc}}\overline{\overline{K}}^{(2)} & ^{\mathrm{oo}}\overline{\overline{K}}^{(2)}
   \end{array}\right)
   
Here the elements are given as:

.. math::
   ^{\mathrm{cc}}K_{i,j}^{(2)}=2\left\langle i\left|\hat{H}-E^{(0)}\right|j\right\rangle 
   
and,

.. math::
   ^{\mathrm{oc}}K_{pq,i}^{(2)}=2\left\langle i\left|\left[E_{pq}^{-},\hat{H}\right]\right|0\right\rangle 
   
and,

.. math::
   \begin{array}{ccc}
   ^{\mathrm{oo}}K_{pq,rs}^{(2)} & = & \frac{1}{2}\left(1+P_{pq,rs}\right)\left\langle 0\left|\left[E_{pq}^{-},\left[E_{rs}^{-},\hat{H}\right]\right]\right|0\right\rangle \\
   & = & \frac{1}{2}\left\langle 0\left|\left[E_{pq}^{-},\left[E_{rs}^{-},\hat{H}\right]\right]\right|0\right\rangle +\frac{1}{2}P_{pq,rs}\left\langle 0\left|\left[E_{pq}^{-},\left[E_{rs}^{-},\hat{H}\right]\right]\right|0\right\rangle \\
   & = & \frac{1}{2}\left\langle 0\left|\left[E_{pq}^{-},\left[E_{rs}^{-},\hat{H}\right]\right]\right|0\right\rangle +\frac{1}{2}\left\langle 0\left|\left[E_{pq}^{-},\left[E_{rs}^{-},\hat{H}\right]\right]\right|0\right\rangle +\frac{1}{2}\left\langle 0\left|\left[E_{rs}^{-},\left[E_{pq}^{-},\hat{H}\right]\right]\right|0\right\rangle \\
   & = & \left\langle 0\left|\left[E_{pq}^{-},\left[E_{rs}^{-},\hat{H}\right]\right]\right|0\right\rangle +\frac{1}{2}\left\langle 0\left|\left[E_{rs}^{-},\left[E_{pq}^{-},\hat{H}\right]\right]\right|0\right\rangle 
   \end{array}
   
Now we define a vector that have been transformed by a trail vector, such:

.. math::
   \left(\begin{array}{c}
   ^{\mathrm{c}}\overline{\sigma}\\
   ^{\mathrm{o}}\overline{\sigma}
   \end{array}\right)=\left(\begin{array}{cc}
   ^{\mathrm{cc}}\overline{\overline{K}}^{(2)} & ^{\mathrm{co}}\overline{\overline{K}}^{(2)}\\
   ^{\mathrm{oc}}\overline{\overline{K}}^{(2)} & ^{\mathrm{oo}}\overline{\overline{K}}^{(2)}
   \end{array}\right)\left(\begin{array}{c}
   \overline{c}\\
   \overline{\kappa}
   \end{array}\right)=\left(\begin{array}{c}
   ^{\mathrm{cc}}\overline{\overline{K}}^{(2)}\overline{c}+{}^{\mathrm{co}}\overline{\overline{K}}^{(2)}\overline{\kappa}\\
   ^{\mathrm{oc}}\overline{\overline{K}}^{(2)}\overline{c}+{}^{\mathrm{oo}}\overline{\overline{K}}^{(2)}\overline{\kappa}
   \end{array}\right)
   
Now lets evaluate the contributions to the sigma vector:

.. math::
   \left[^{\mathrm{cc}}\overline{\overline{K}}^{(2)}\overline{c}\right]_{i}=\sum_{j}2\left\langle i\left|\hat{H}-E^{(0)}\right|j\right\rangle c_{j}
   
Now with the definition that:

.. math::
   \left|\overline{c}\right\rangle =\sum_{j}c_{j}\left|j\right\rangle 
   
This can be written as:

.. math::
   \left[^{\mathrm{cc}}\overline{\overline{K}}^{(2)}\overline{c}\right]_{i}=2\left\langle i\left|\hat{H}-E^{(0)}\right|\overline{c}\right\rangle 
   
Now the next term:

.. math::
   \begin{array}{ccc}
   \left[^{\mathrm{co}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{i} & = & \sum_{p>q}2\left\langle i\left|\left[E_{pq}^{-},\hat{H}\right]\right|0\right\rangle \kappa_{pq}\\
   & = & 2\left\langle i\left|\sum_{p>q}\kappa_{pq}\left[E_{pq}^{-},\hat{H}\right]\right|0\right\rangle 
   \end{array}
   
Now by the definition:

.. math::
   \hat{\kappa}=\sum_{p>q}\kappa_{pq}E_{pq}^{-}
   
Giving:

.. math::
   \begin{array}{ccc}
   \left[^{\mathrm{co}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{i} & = & 2\left\langle i\left|\left[\hat{\kappa},\hat{H}\right]\right|0\right\rangle \\
   & = & 2\left\langle i\left|\hat{H}_{\kappa}\right|0\right\rangle 
   \end{array}

with :math:`\hat{H}_{\kappa}=\left[\hat{\kappa},\hat{H}\right]`.   
Now the next term:

.. math::
   \left[^{\mathrm{oc}}\overline{\overline{K}}^{(2)}\overline{c}\right]_{pq}=\sum_{i}2\left\langle i\left|\left[E_{pq}^{-},\hat{H}\right]\right|0\right\rangle c_{i}
   
Since it can be written that:

.. math::
   2\left\langle i\left|\left[E_{pq}^{-},\hat{H}\right]\right|0\right\rangle =\left\langle i\left|\left[E_{pq}^{-},\hat{H}\right]\right|0\right\rangle +\left\langle 0\left[E_{pq}^{-},\hat{H}\right]i\right\rangle 
   
(why can we do this? and why do we want to do this?)
This now leads to:

.. math::
   \left[^{\mathrm{oc}}\overline{\overline{K}}^{(2)}\overline{c}\right]_{pq}=\left\langle \overline{c}\left|\left[E_{pq}^{-},\hat{H}\right]\right|0\right\rangle +\left\langle 0\left[E_{pq}^{-},\hat{H}\right]\overline{c}\right\rangle 
   
And the last term:

.. math::
   \left[^{\mathrm{oo}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{pq}=\sum_{r>s}\left\langle 0\left|\left[E_{pq}^{-},\left[E_{rs}^{-},\hat{H}\right]\right]\right|0\right\rangle \kappa_{rs}+\frac{1}{2}\sum_{r>s}\left\langle 0\left|\left[E_{rs}^{-},\left[E_{pq}^{-},\hat{H}\right]\right]\right|0\right\rangle \kappa_{rs}
   
This can be rewritten as:

.. math::
   \left[^{\mathrm{oo}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{pq}=\left\langle 0\left|\left[E_{pq}^{-},\hat{H}_{\kappa}\right]\right|0\right\rangle +\frac{1}{2}\left\langle 0\left|\left[\hat{\kappa},\left[E_{pq}^{-},\hat{H}\right]\right]\right|0\right\rangle 
   
Now by using the Jacobi identity:

.. math::
   \left[^{\mathrm{oo}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{pq}=\left\langle 0\left|\left[E_{pq}^{-},\hat{H}_{\kappa}\right]\right|0\right\rangle -\frac{1}{2}\left\langle 0\left|\left[E_{pq}^{-},\left[\hat{H},\hat{\kappa}\right]\right]\right|0\right\rangle -\frac{1}{2}\left\langle 0\left|\left[\hat{H},\left[\hat{\kappa},E_{pq}^{-}\right]\right]\right|0\right\rangle 
   
Now by using the relation, :math:`\left[\hat{A},\left[\hat{B},\hat{C}\right]\right]=-\left[\left[\hat{B},\hat{C}\right],\hat{A}\right]` and :math:`\left[\hat{A},\hat{B}\right]=-\left[\hat{B},\hat{A}\right]`:

.. math::
   \left[^{\mathrm{oo}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{pq}=\left\langle 0\left|\left[E_{pq}^{-},\hat{H}_{\kappa}\right]\right|0\right\rangle +\frac{1}{2}\left\langle 0\left|\left[E_{pq}^{-},\left[\hat{\kappa},\hat{H}\right]\right]\right|0\right\rangle +\frac{1}{2}\left\langle 0\left|\left[\left[\hat{\kappa},E_{pq}^{-}\right],\hat{H}\right]\right|0\right\rangle 
   
Now:

.. math::
   \left[^{\mathrm{oo}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{pq}=\frac{3}{2}\left\langle 0\left|\left[E_{pq}^{-},\hat{H}_{\kappa}\right]\right|0\right\rangle +\frac{1}{2}\left\langle 0\left|\left[\left[\hat{\kappa},E_{pq}^{-}\right],\hat{H}\right]\right|0\right\rangle 
   
Now :math:`\left\langle 0\left|\left[\left[\hat{\kappa},E_{pq}^{-}\right],\hat{H}\right]\right|0\right\rangle =\left[^{\mathrm{o}}\overline{E}^{(1)},\overline{\kappa}\right]_{pq}`:

.. math::
   \left[^{\mathrm{oo}}\overline{\overline{K}}^{(2)}\overline{\kappa}\right]_{pq}=\frac{3}{2}\left\langle 0\left|\left[E_{pq}^{-},\hat{H}_{\kappa}\right]\right|0\right\rangle +\frac{1}{2}\left[^{\mathrm{o}}\overline{E}^{(1)},\overline{\kappa}\right]_{pq}
   
NOTE this is the wrong results, the factor 3/2 and 1/2 are not supposed to be here. Something went very wrong!