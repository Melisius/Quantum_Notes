
Just Maths
==========

Matrices
--------

Real (anti)-symmetric matrix
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A real symmetric matrix is defined as:

.. math::
   A_{i,j}=A_{j,i}
   
A real anti-symmetric matrix is defined as:

.. math::
   A_{i,j}=-A_{j,i}
   
Baker-Campbell-Hausdorf expansion
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The BCH expansion is given as:

.. math::
   \exp\left(A\right)B\exp\left(-A\right)=B+\left[A,B\right]+\frac{1}{2!}\left[A,\left[A,B\right]\right]+\frac{1}{3!}\left[A,\left[A,\left[A,B\right]\right]\right]+...

Unitary matrix
~~~~~~~~~~~~~~

A unitary matrix is defined as:

.. math::
   U^{\dagger}U=UU^{\dagger}=1
   
Real orthogoanl matrix
~~~~~~~~~~~~~~~~~~~~~~

A real orthogonal matrix must satisfy:

.. math::
   Q^{T}Q=QQ^{T}=1

Operators
---------

Projection operator
~~~~~~~~~~~~~~~~~~~

A projection operator is defined as:

.. math::
   \hat{P}^{2}=\hat{P}
   
As an example lets consider:

.. math::
   \hat{P}=1-\left|0\right\rangle \left\langle 0\right|
   
Now:

.. math::
   \hat{P}^{2}=\left(1-\left|0\right\rangle \left\langle 0\right|\right)^{2}=1+\left|0\right\rangle \left\langle 0\right|\left|0\right\rangle \left\langle 0\right|-2\left|0\right\rangle \left\langle 0\right|
   
It can now be used that :math:`\left\langle 0\right|\left|0\right\rangle =1`:

.. math::
   \hat{P}^{2}=1+\left|0\right\rangle \left\langle 0\right|-2\left|0\right\rangle \left\langle 0\right|=1-\left|0\right\rangle \left\langle 0\right|=\hat{P}

(anti)-Commutator
~~~~~~~~~~~~~~~~~

The commutator is defined as:

.. math::
   \left[\hat{A},\hat{B}\right]=\hat{A}\hat{B}-\hat{B}\hat{A}
   
The anti-commutator is defined as:

.. math::
   \left[\hat{A},\hat{B}\right]_{+}=\hat{A}\hat{B}+\hat{B}\hat{A}