
Mathematics
===========

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
   
Real orthogonal matrix
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
   
From the commutator relation it can be noted that:

.. math::
   \left[\hat{A},\hat{B}\right]=\hat{A}\hat{B}-\hat{B}\hat{A}=-\left(\hat{B}\hat{A}-\hat{A}\hat{B}\right)=-\left[\hat{B},\hat{A}\right]
   
Jacobi identity
~~~~~~~~~~~~~~~

Lets consider:

.. math::
   \left[A,\left[B,C\right]\right]+\left[B,\left[C,A\right]\right]+\left[C,\left[A,B\right]\right]
   
Now by expansion:

.. math::
   \left[A,BC-CB\right]+\left[B,CA-AC\right]+\left[C,AB-BA\right]
 
Which can be rearranged to: 
 
.. math::
   \begin{array}{c}A\left(BC-CB\right)-\left(BC-CB\right)A+B\left(CA-AC\right)\\-\left(CA-AC\right)B+C\left(AB-BA\right)-\left(AB-BA\right)C\end{array}

Which can be rearranged to: 

.. math::
   \begin{array}{c}ABC-ACB-BCA+CBA+BCA-BAC\\-CAB+ACB+CAB-CBA-ABC+BAC\end{array}
   
Now by a final rearranging:

.. math::
   \begin{array}{c}ABC-ABC+ACB-ACB+BAC-BAC\\+BCA-BCA+CAB-CAB+CBA-CBA=0\end{array}
   
Thus showing:

.. math::
   \left[A,\left[B,C\right]\right]+\left[B,\left[C,A\right]\right]+\left[C,\left[A,B\right]\right]=0
   
Which is known as the Jacobi identity.