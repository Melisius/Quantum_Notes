

Quantum operator examples
=========================

Transpose of operator matrix
----------------------------

Lets consider a general operator, that changes a state:

.. math::
   \hat{O}\left|i\right\rangle =\left|j\right\rangle 
   
Now lets define the adjoint of the operator as:

.. math::
   \left\langle i\right|\hat{O}^{\dagger}=\left\langle j\right|
   
These two definitions implies:

.. math::
   \left\langle k\left|\hat{O}\right|i\right\rangle =\left\langle k\left|j\right.\right\rangle 
   
and,

.. math::
   \left\langle i\left|\hat{O}^{\dagger}\right|k\right\rangle =\left\langle j\left|k\right.\right\rangle 
   
It is known that:

.. math::
   \left\langle i\left|j\right.\right\rangle =\left\langle j\left|i\right.\right\rangle ^{*}
   
Thus giving:

.. math::
   \left\langle k\left|\hat{O}\right|i\right\rangle =\left\langle i\left|\hat{O}^{\dagger}\right|k\right\rangle ^{*}
   
Now if the operator is Hermitian i.e:

.. math::
   \hat{O}=\hat{O}^{\dagger}
   
It can be written that:

.. math::
   \left\langle k\left|\hat{O}\right|i\right\rangle =\left\langle i\left|\hat{O}\right|k\right\rangle ^{*}
   
Thus if the wave functions are real, it gives:

.. math::
   \left\langle k\left|\hat{O}\right|i\right\rangle =\left\langle i\left|\hat{O}\right|k\right\rangle 

- Modern Quantum Chemistry: Introduction to Advanced Electronic Structure Theory, Szabo and Ostlund

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
   
   
Transpose of operator matrix, example
-------------------------------------

Lets consider the following matrix:

.. math::
   \left\langle i\left|\left[\hat{E}_{pq}^{-},\hat{H}\right]\right|0\right\rangle 
   
Now the following relation can be used:

.. math::
   \left\langle k\left|\hat{O}\right|i\right\rangle =\left\langle i\left|\hat{O}^{\dagger}\right|k\right\rangle ^{*}
   
Thus:

.. math::
   \left\langle i\left|\left[\hat{E}_{pq}^{-},\hat{H}\right]\right|0\right\rangle =\left\langle 0\left|\left[\hat{E}_{pq}^{-},\hat{H}\right]^{\dagger}\right|i\right\rangle ^{*}
   
Now calculating the new operator by using :math:`\left(\hat{A}\hat{B}\right)^{\dagger}=\hat{B}^{\dagger}\hat{A}^{\dagger}`:

.. math::
   \left[\hat{E}_{pq}^{-},\hat{H}\right]^{\dagger}=\left(\hat{E}_{pq}^{-}\hat{H}-\hat{H}\hat{E}_{pq}^{-}\right)^{\dagger}=\hat{H}^{\dagger}\hat{E}_{pq}^{-\dagger}-\hat{E}_{pq}^{-\dagger}\hat{H}^{\dagger}

It is known that :math:`\hat{H}^{\dagger}=\hat{H}` and :math:`\hat{E}_{pq}^{-}\equiv\hat{E}_{pq}-\hat{E}_{qp}`.
Now evaluating:

.. math::
   \hat{E}_{pq}^{-\dagger}=\hat{E}_{pq}^{\dagger}-\hat{E}_{qp}^{\dagger}
   
Expanding:

.. math::
   \hat{E}_{pq}=\left(p^{\dagger}q\right)^{\dagger}=q^{\dagger}p=\hat{E}_{qp}
   
Now:

.. math::
   \hat{E}_{pq}^{-\dagger}=\hat{E}_{qp}-\hat{E}_{pq}=-\hat{E}_{pq}^{-}
   
Thus:

.. math::
   \left[\hat{E}_{pq}^{-},\hat{H}\right]^{\dagger}=-\hat{H}\hat{E}_{pq}^{-}+\hat{E}_{pq}^{-}\hat{H}=\left[\hat{E}_{pq}^{-},\hat{H}\right]
   
Now since this commutator is Hermitian it is found that:

.. math::
   \left\langle i\left|\left[\hat{E}_{pq}^{-},\hat{H}\right]\right|0\right\rangle =\left\langle 0\left|\left[\hat{E}_{pq}^{-},\hat{H}\right]\right|i\right\rangle 