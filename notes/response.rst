
Response
========

Linear-Transformation
---------------------

The combined triplet and singlet one-body operator:

.. math::
   E\left(S\right)_{rs}=E_{rs}^{\alpha}+SE_{rs}^{\beta}

With :math:`S` being :math:`+` for singlet and :math:`-` for triplet. The general two-body operator can be written as:

.. math::
   e_{rstu}\left(S_{1},S_{2}\right)=E\left(S_{1}\right)_{rs}E\left(S_{2}\right)_{tu}-\delta_{st}E\left(S_{1}S_{2}\right)_{ru}
   
Now some matrices can be defined:

.. math::
   E^{(2)}=\left(\begin{array}{cc}
   A & B\\
   A^{*} & B^{*}
   \end{array}\right)

.. math::
   S^{(2)}=\left(\begin{array}{cc}
   \Sigma & \Delta\\
   -\Delta^{*} & -\Sigma^{*}
   \end{array}\right)
 
Here the submatricies are given as:

.. math::
   A=\left(\begin{array}{cc}
   \left\langle 0\left|\left[q_{i},\left[H_{0},q_{j}^{+}\right]\right]\right|0\right\rangle  & \left\langle 0\left|\left[\left[q_{i},H_{0}\right],R_{j}^{+}\right]\right|0\right\rangle \\
   \left\langle 0\left|\left[R_{i},\left[H_{0},q_{j}^{+}\right]\right]\right|0\right\rangle  & \left\langle 0\left|\left[R_{i},\left[H_{0},R_{j}^{+}\right]\right]\right|0\right\rangle 
   \end{array}\right)
 
.. math::
   B=\left(\begin{array}{cc}
   \left\langle 0\left|\left[q_{i},\left[H_{0},q_{j}\right]\right]\right|0\right\rangle  & \left\langle 0\left|\left[\left[q_{i},H_{0}\right],R_{j}\right]\right|0\right\rangle \\
   \left\langle 0\left|\left[R_{i},\left[H_{0},q_{j}\right]\right]\right|0\right\rangle  & \left\langle 0\left|\left[R_{i},\left[H_{0},R_{j}\right]\right]\right|0\right\rangle 
   \end{array}\right)

.. math::
   \Sigma=\left(\begin{array}{cc}
   \left\langle 0\left|\left[q_{i},q_{j}^{+}\right]\right|0\right\rangle  & \left\langle 0\left|\left[q_{i},R_{j}^{+}\right]\right|0\right\rangle \\
   \left\langle 0\left|\left[R_{i},q_{j}^{+}\right]\right|0\right\rangle  & \left\langle 0\left|\left[R_{i},R_{j}^{+}\right]\right|0\right\rangle 
   \end{array}\right)
   
.. math::
   \Delta=\left(\begin{array}{cc}
   \left\langle 0\left|\left[q_{i},q_{j}\right]\right|0\right\rangle  & \left\langle 0\left|\left[q_{i},R_{j}\right]\right|0\right\rangle \\
   \left\langle 0\left|\left[R_{i},q_{j}\right]\right|0\right\rangle  & \left\langle 0\left|\left[R_{i},R_{j}\right]\right|0\right\rangle 
   \end{array}\right)
   
The Hamiltonian is given as:

.. math::
   H_{0}=\sum_{rs}h_{rs}E\left(+\right)_{rs}+\frac{1}{2}\sum_{rstu}\left(rs|tu\right)e\left(+,+\right)_{rstu}
   
:math:`R` is the state transfer oprators that takes :math:`0` to :math:`n`:

.. math::
   R_{n}^{+}=\left|n\right\rangle \left\langle 0\right|
   
.. math::
   R_{n}=\left|0\right\rangle \left\langle n\right|

Here :math:`n` have to be different from :math:`0`. Atlast the orbital operators :math:`q` are given as:

.. math::
   q_{j}^{+}=\left(\begin{array}{c}
   E\left(+\right)_{rs}\\
   E\left(-\right)_{rs}
   \end{array}\right)=a_{r\alpha}^{+}a_{s\alpha}\pm a_{r\beta}^{+}a_{s\beta}
   
.. math::
   q_{j}=\left(\begin{array}{c}
   E\left(+\right)_{sr}\\
   E\left(-\right)_{sr}
   \end{array}\right)=a_{s\alpha}^{+}a_{r\alpha}\pm a_{s\beta}^{+}a_{r\beta}
   
Here :math:`r>s`. Now for the triplet response the goal is to solve the response equations:

.. math::
   \left(E^{(2)}-\lambda_{j}S^{(2)}\right)X_{j}=0
   
Here the matricies :math:`E` and :math:`S` are given above. :math:`\lambda_{j}` is the eigenvalues corrosponding to the singlet-triplet excitation energies. :math:`X_{j}` is the corrosponding eigenvectors. And:

.. math::
   \left(E^{(2)}-\lambda_{j}S^{(2)}\right)X_{j}=V^{(1)}

Here :math:`\lambda_{j}` will corrospond to the frequency of an external perturbation. These equation can be solved by an iterative procedure, by making a linear transformation:
   
.. math::
   u=E^{(2)}N
   
.. math::
   m=S^{(2)}N

Here :math:`N` is a trailvector. Now to solve the equations the trailvectors is needed. The trail vector can be considered as two vectors:

.. math::
   N^{c}=\left(\begin{array}{c}
   0\\
   S\\
   0\\
   S'
   \end{array}\right)

and, 

.. math::
   N^{o}=\left(\begin{array}{c}
   \kappa\\
   0\\
   \kappa'\\
   0
   \end{array}\right)

The orbital vector can be considered as a matrix constructed as:

.. math::
   K_{rs}=\begin{cases}
   \kappa_{rs} & r>s\\
   \kappa_{sr} & r<s\\
   0 & else
   \end{cases}
   
Now lets consider, the linear transformation of :math:`u_{(pq)}^{o}=\sum_{(rs)}E_{(pq)(rs)}^{(2)}N_{(rs)}^{o}`. :math:`E^{(2)}` can be thought of as a 4x4 matrix, :math:`N^{o}` as a four long vector. Now the first element from this linear transformation is found to be:
 
.. math::
   u_{1}^{o}=\sum_{j}\left(\left\langle 0\left|\left[q_{i},\left[H_{0},q_{j}^{+}\right]\right]\right|0\right\rangle \kappa_{j}+\left\langle 0\left|\left[q_{i},\left[H_{0},q_{j}\right]\right]\right|0\right\rangle \kappa_{j}'\right)

Here :math:`(pq)=i` and :math:`(rs)=j`. Now this can be rewritten as:  
 
.. math::
   u_{1}^{o}=\left\langle 0\left|\left[q_{i},\left[H_{0},\sum_{j}q_{j}^{+}\kappa_{j}\right]\right]\right|0\right\rangle +\left\langle 0\left|\left[q_{i},\left[H_{0},\sum_{j}q_{j}\kappa_{j}'\right]\right]\right|0\right\rangle 
   
Here it is used that :math:`\kappa` is just a number, and only one of the terms depends on :math:`j`. Now:  
   
.. math::
   u_{1}^{o}=\left\langle 0\left|\left[q_{i},\left[H_{0},\sum_{j}\left(q_{j}^{+}\kappa_{j}+q_{j}\kappa_{j}'\right)\right]\right]\right|0\right\rangle 

Now by using the definition of the one-index transformed Hamiltonian: 

.. math::
   u_{1}^{o}=-\left\langle 0\left|\left[q_{i},H\left(\kappa\right)\right]\right|0\right\rangle 
   
The minus is from :math:`\left[H_{0},\sum_{j}\left(q_{j}^{+}\kappa_{j}+q_{j}\kappa_{j}'\right)\right]=-\left[\sum_{j}\left(q_{j}^{+}\kappa_{j}+q_{j}\kappa_{j}'\right),H_{0}\right]`. Now the second element:
   
.. math::
   u_{2}^{o}=\sum_{j}\left(\left\langle 0\left|\left[R_{i},\left[H_{0},q_{j}^{+}\right]\right]\right|0\right\rangle \kappa_{j}+\left\langle 0\left|\left[R_{i},\left[H_{0},q_{j}\right]\right]\right|0\right\rangle \kappa_{j}'\right) 
   
Following the same procedure:

.. math::
   u_{2}^{o}=-\left\langle 0\left|\left[R_{i},H\left(\kappa\right)\right]\right|0\right\rangle 

Having :math:`R_{i}=\left|0\right\rangle \left\langle n\right|`, now gives:  

.. math::
   u_{2}^{o}=-\left\langle i\left|H\left(\kappa\right)\right|0\right\rangle 
   
The third term:

.. math::
   u_{3}^{o}=\sum_{j}\left(\left(\left\langle 0\left|\left[q_{i},\left[H_{0},q_{j}\right]\right]\right|0\right\rangle \right)^{*}\kappa_{j}+\left(\left\langle 0\left|\left[q_{i},\left[H_{0},q_{j}^{+}\right]\right]\right|0\right\rangle \right)^{*}\kappa_{j}'\right)

Following the same procedure and using :math:`q_{i}^{*}=q_{i}^{\dagger}`:

.. math::
   u_{3}^{o}=-\left\langle 0\left|\left[q_{i}^{\dagger},H\left(\kappa\right)\right]\right|0\right\rangle 
   
Now the fourth term:

.. math::
   u_{4}^{o}=\sum_{j}\left(\left(\left\langle 0\left|\left[R_{i},\left[H_{0},q_{j}^{+}\right]\right]\right|0\right\rangle \right)^{*}\kappa_{j}+\left(\left\langle 0\left|\left[R_{i},\left[H_{0},q_{j}\right]\right]\right|0\right\rangle \right)^{*}\kappa_{j}'\right)
   
Gives:

.. math::
   u_{4}^{o}=\left\langle 0\left|H\left(\kappa\right)\right|i\right\rangle

Here it is used that, :math:`\left[R_{i}^{\dagger},H\left(\kappa\right)\right]=-\left[H\left(\kappa\right),R_{i}^{\dagger}\right]`. Now in summary giving:

.. math::
   u^{o}=-\left(\begin{array}{c}
   \left\langle 0\left|\left[q_{i},H\left(\kappa\right)\right]\right|0\right\rangle \\
   \left\langle i\left|H\left(\kappa\right)\right|0\right\rangle \\
   \left\langle 0\left|\left[q_{i}^{\dagger},H\left(\kappa\right)\right]\right|0\right\rangle \\
   -\left\langle 0\left|H\left(\kappa\right)\right|i\right\rangle 
   \end{array}\right)
   
Now consider the linear transformation of :math:`u_{(pq)}^{c}=\sum_{(rs)}E_{(pq)(rs)}^{(2)}N_{(rs)}^{c}`. First:
   
.. math::
   u_{1}^{c}=\sum_{j}\left(\left\langle 0\left|\left[\left[q_{i},H_{0}\right],R_{j}^{+}\right]\right|0\right\rangle S_{j}+\left\langle 0\left|\left[\left[q_{i},H_{0}\right],R_{j}\right]\right|0\right\rangle S'_{j}\right)
   
It can now be introduced that:

.. math::
   \left|0^{R}\right\rangle =-\sum_{n}S_{n}R_{n}^{+}\left|0\right\rangle =-\sum_{n}S_{n}\left|n\right\rangle 
  
.. math::
   \left\langle 0^{L}\right|=\sum_{n}\left\langle 0\right|S_{n}^{'}R_{n}=\sum_{n}\left\langle n\right|S_{n}^{'}
   
Using the above:

.. math::
   u_{1}^{c}=-\left\langle 0\left|\left[q_{i},H_{0}\right]\right|0^{R}\right\rangle -\left\langle 0^{L}\left|\left[q_{i},H_{0}\right]\right|0\right\rangle 
   
Following the same method it can be found that:

.. math::
   u^{c}=-\left(\begin{array}{c}
   \left\langle 0^{L}\left|\left[q_{i},H_{0}\right]\right|0\right\rangle +\left\langle 0\left|\left[q_{i},H_{0}\right]\right|0^{R}\right\rangle \\
   \left\langle i\left|H_{0}\right|0^{R}\right\rangle +\left\langle 0\left|H_{0}\right|0\right\rangle S\\
   \left\langle 0^{L}\left|\left[q_{i}^{\dagger},H_{0}\right]\right|0\right\rangle +\left\langle 0\left|\left[q_{i}^{\dagger},H_{0}\right]\right|0^{R}\right\rangle \\
   -\left\langle 0^{L}\left|H_{0}\right|i\right\rangle +\left\langle 0\left|H_{0}\right|0\right\rangle S'
   \end{array}\right)
 
In a similar way the linear transformation of :math:`S` can be made to find:

.. math::
   m^{o}=\left(\begin{array}{c}
   \left\langle 0\left|\left[q_{i},\hat{\kappa}\right]\right|0\right\rangle \\
   \left\langle i\left|\hat{\kappa}\right|0\right\rangle \\
   \left\langle 0\left|\left[q_{i}^{\dagger},\hat{\kappa}\right]\right|0\right\rangle \\
   \left\langle 0\left|\hat{\kappa}\right|i\right\rangle 
   \end{array}\right)

and,

.. math::
   m^{c}=\left(\begin{array}{c}
   -\left\langle 0\left|q_{i}\right|0^{R}\right\rangle -\left\langle 0^{L}\left|q_{i}\right|0\right\rangle \\
   S_{i}\\
   -\left\langle 0\left|q_{i}^{\dagger}\right|0^{R}\right\rangle -\left\langle 0^{L}\left|q_{i}^{\dagger}\right|0\right\rangle \\
   -S_{i}'
   \end{array}\right)
   
