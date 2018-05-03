
Lagrangian multipliers
======================

Lets consider the electrostatic potential due to multipoles places at the position of atoms:

.. math::
   E_{i}=\sum_{j}^{atom}\sum_{n}^{multipole}\frac{\left(-1\right)^{n}}{n!}T_{ij}^{(n)}m_{j}^{(n)}
   
If the quantum mechanical electrostatic potential is to be minimized, a cost function can written of the form:

.. math::
   z=\sum_{i}^{point}\left(V_{i,\mathrm{QM}}-E_{i}\right)^{2}+\sum_{l}^{constraints}\lambda_{l}g_{l}
   
Expanding the square:

.. math::
   z=\sum_{i}^{point}\left(V_{i,\mathrm{QM}}^{2}+E_{i}^{2}-2E_{i}V_{i,\mathrm{QM}}\right)+\sum_{l}^{constraints}\lambda_{l}g_{l}
   
It is known that in the minima that the derivative with respect to all parameters equals to zero. 

   Now with, :math:`\frac{\partial E_{i}^{2}}{\partial m_{p}^{(k)}}=2\frac{\left(-1\right)^{k}}{k!}T_{ip}^{(k)}\sum_{n}^{multipole}\frac{\left(-1\right)^{n}}{n!}T_{ij}^{(n)}m_{j}^{(n)}`, it can be written:
   
.. math::
   \sum_{k}^{multipole}\frac{\partial z}{\partial m_{p}^{(k)}}=\sum_{k}^{multipole}\sum_{i}^{point}\left(\sum_{j}^{atom}2\frac{\left(-1\right)^{k}}{k!}T_{ip}^{(k)}\sum_{n}^{multipole}\frac{\left(-1\right)^{n}}{n!}T_{ij}^{(n)}m_{j}^{(n)}-2V_{i,\mathrm{QM}}\sum_{j}^{atom}\frac{\left(-1\right)^{k}}{k!}T_{ij}^{(k)}\right)
   
Since the condition was :math:`\sum_{k}^{multipole}\frac{\partial z}{\partial m^{(k)}}=0`, and reducing out the factor 2, it can be written as:

.. math::
   \sum_{p}^{atom}\sum_{k}^{multipole}\sum_{j}^{atom}\sum_{n}^{multipole}\sum_{i}^{point}\frac{\left(-1\right)^{k}}{k!}T_{ip}^{(k)}\frac{\left(-1\right)^{n}}{n!}T_{ij}^{(n)}m_{j}^{(n)}=\sum_{j}^{atom}\sum_{k}^{multipole}\sum_{i}^{point}V_{i,\mathrm{QM}}\frac{\left(-1\right)^{k}}{k!}T_{ij}^{(k)}
   
Now this can be identified as a matrix equation of the following form:

.. math::
   \overline{\overline{A}}\overline{x}=\overline{B}
   
With the elements given as:

.. math::
   A_{pk,jn}=\sum_{i}^{point}\frac{\left(-1\right)^{k}}{k!}T_{ip}^{(k)}\frac{\left(-1\right)^{n}}{n!}T_{ij}^{(n)}
   
and,

.. math::
   B_{jn}=\sum_{i}^{point}V_{i,\mathrm{QM}}\frac{\left(-1\right)^{k}}{k!}T_{ij}^{(k)}
   
and, 

.. math::
   x_{jn}=m_{j}^{(n)}
   
Constraints
-----------

For the technique of Lagrangian multiplies, the multipoles :math:`m_{j}^{(n)}` can be constrained.
The general constraint for multipoles is given as:

.. math::
   g_{n}=\sum_{i}^{n}\sum_{j}^{atoms}m_{j}^{(i)}R^{(n-i)}-m_{tot}^{(n)}
   
Here :math:`R^{(m)}` is the direct product of the distance between the origin and the multipole :math:`m` times.
And :math:`R^{(0)}=1`.
Thus:

.. math::
   \frac{\partial z}{\partial\lambda_{n}}=g_{n}=0
   
Giving:

.. math::
   m_{tot}^{(n)}=\sum_{i}^{n}\sum_{j}^{atoms}m_{j}^{(i)}R^{(n-i)}
   
Which is the constraints that should be fulfilled.   

Example Matrix
--------------
   
A total matrix equation as (for up to dipoles), with :math:`d_{i}=r_{i}-R_{\mathrm{cm}}`:

.. math::
   \left[\begin{array}{cccccccccccccccc}
	A_{1,1}^{q,q} & \ldots & A_{1,k}^{q,q} & A_{1,1}^{q,\mu_{x}} & \ldots & A_{1,k}^{q,\mu_{x}} & A_{1,1}^{q,\mu_{y}} & \ldots & A_{1,k}^{q,\mu_{y}} & A_{1,1}^{q,\mu_{z}} & \ldots & A_{1,k}^{q,\mu_{z}} & 1 & d_{1,x} & d_{1,y} & d_{1,z}\\
	\vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \vdots & \vdots & \vdots\\
	A_{p,1}^{q,q} & \ldots & A_{p,k}^{q,q} & A_{p,1}^{q,\mu_{x}} & \ldots & A_{p,k}^{q,\mu_{x}} & A_{p,1}^{q,\mu_{y}} & \ldots & A_{p,k}^{q,\mu_{y}} & A_{p,1}^{q,\mu_{z}} & \ldots & A_{p,k}^{q,\mu_{z}} & 1 & d_{k,x} & d_{k,y} & d_{k,z}\\
	A_{1,1}^{\mu_{x},q} & \ldots & A_{1,k}^{\mu_{x},q} & A_{1,1}^{\mu_{x},\mu_{x}} & \ldots & A_{1,k}^{\mu_{x},\mu_{x}} & A_{1,1}^{\mu_{x},\mu_{y}} & \ldots & A_{1,k}^{\mu_{x},\mu_{y}} & A_{1,1}^{\mu_{x},\mu_{z}} & \ldots & A_{1,k}^{\mu_{x},\mu_{z}} & 0 & 1 & 0 & 0\\
	\vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \vdots & \vdots & \vdots\\
	A_{p,1}^{\mu_{x},q} & \ldots & A_{p,k}^{\mu_{x},q} & A_{p,1}^{\mu_{x},\mu_{x}} & \ldots & A_{p,k}^{\mu_{x},\mu_{x}} & A_{p,1}^{\mu_{x},\mu_{y}} & \ldots & A_{p,k}^{\mu_{x},\mu_{y}} & A_{p,1}^{\mu_{x},\mu_{z}} & \ldots & A_{p,k}^{\mu_{x},\mu_{z}} & 0 & 1 & 0 & 0\\
	A_{1,1}^{\mu_{y},q} & \ldots & A_{1,k}^{\mu_{y},q} & A_{1,1}^{\mu_{y},\mu_{x}} & \ldots & A_{1,k}^{\mu_{y},\mu_{x}} & A_{1,1}^{\mu_{y},\mu_{y}} & \ldots & A_{1,k}^{\mu_{y},\mu_{y}} & A_{1,1}^{\mu_{y},\mu_{z}} & \ldots & A_{1,k}^{\mu_{y},\mu_{z}} & 0 & 0 & 1 & 0\\
	\vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \vdots & \vdots & \vdots\\
	A_{p,1}^{\mu_{y},q} & \ldots & A_{p,k}^{\mu_{y},q} & A_{p,1}^{\mu_{y},\mu_{x}} & \ldots & A_{p,k}^{\mu_{y},\mu_{x}} & A_{p,1}^{\mu_{y},\mu_{y}} & \ldots & A_{p,k}^{\mu_{y},\mu_{y}} & A_{p,1}^{\mu_{y},\mu_{z}} & \ldots & A_{p,k}^{\mu_{y},\mu_{z}} & 0 & 0 & 1 & 0\\
	A_{1,1}^{\mu_{z},q} & \ldots & A_{1,k}^{\mu_{z},q} & A_{1,1}^{\mu_{z},\mu_{x}} & \ldots & A_{1,k}^{\mu_{z},\mu_{x}} & A_{1,1}^{\mu_{z},\mu_{y}} & \ldots & A_{1,k}^{\mu_{z},\mu_{y}} & A_{1,1}^{\mu_{z},\mu_{z}} & \ldots & A_{1,k}^{\mu_{z},\mu_{z}} & 0 & 0 & 0 & 1\\
	\vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \ddots & \vdots & \vdots & \vdots & \vdots & \vdots\\
	A_{p,1}^{\mu_{z},q} & \ldots & A_{p,k}^{\mu_{z},q} & A_{p,1}^{\mu_{z},\mu_{x}} & \ldots & A_{p,k}^{\mu_{z},\mu_{x}} & A_{p,1}^{\mu_{z},\mu_{y}} & \ldots & A_{p,k}^{\mu_{z},\mu_{y}} & A_{p,1}^{\mu_{z},\mu_{z}} & \ldots & A_{p,k}^{\mu_{z},\mu_{z}} & 0 & 0 & 0 & 1\\
	1 & \ldots & 1 & 0 & \ldots & 0 & 0 & \ldots & 0 & 0 & \ldots & 0 & 0 & 0 & 0 & 0\\
	d_{1,x} & \ldots & d_{k,x} & 1 & \ldots & 1 & 0 & \ldots & 0 & 0 & \ldots & 0 & 0 & 0 & 0 & 0\\
	d_{1,y} & \ldots & d_{k,y} & 0 & \ldots & 0 & 1 & \ldots & 1 & 0 & \ldots & 0 & 0 & 0 & 0 & 0\\
	d_{1,z} & \ldots & d_{k,z} & 0 & \ldots & 0 & 0 & \ldots & 0 & 1 & \ldots & 1 & 0 & 0 & 0 & 0
	\end{array}\right]\left[\begin{array}{c}
	q_{1}\\
	\vdots\\
	q_{p}\\
	\mu_{x,1}\\
	\vdots\\
	\mu_{x,p}\\
	\mu_{y,1}\\
	\vdots\\
	\mu_{y,p}\\
	\mu_{z,1}\\
	\vdots\\
	\mu_{z,p}\\
	\lambda_{q}\\
	\lambda_{\mu_{x}}\\
	\lambda_{\mu_{y}}\\
	\lambda_{\mu_{z}}
	\end{array}\right]=\left[\begin{array}{c}
	B_{1}^{q}\\
	\vdots\\
	B_{p}^{q}\\
	B_{1}^{\mu_{x}}\\
	\vdots\\
	B_{p}^{\mu_{x}}\\
	B_{1}^{\mu_{y}}\\
	\vdots\\
	B_{p}^{\mu_{y}}\\
	B_{1}^{\mu_{z}}\\
	\vdots\\
	B_{p}^{\mu_{z}}\\
	q_{tot}\\
	\mu_{x,tot}\\
	\mu_{y,tot}\\
	\mu_{z,tot}
	\end{array}\right]

Or in more compressed form:

.. math::
   \left[\begin{array}{cccc}
	A^{q,q} & A^{q,\mu} & 1 & \left(r_{j}-R_{\mathrm{cm}}\right)\\
	A^{q,\mu} & A^{\mu,\mu} & 0 & 1\\
	1 & 0 & 0 & 0\\
	\left(r_{j}-R_{\mathrm{cm}}\right) & 1 & 0 & 0
	\end{array}\right]\left[\begin{array}{c}
	q\\
	\mu\\
	\lambda_{q}\\
	\lambda_{mu}
	\end{array}\right]=\left[\begin{array}{c}
	B^{q}\\
	B^{\mu}\\
	q_{tot}\\
	\mu_{tot}
	\end{array}\right]

Implementation comments
-----------------------

For the implementation it can be noted that :math:`\overline{\overline{A}}` is symmetric.
Now the matrix :math:`A` can be constructed by constructing an auxiliary matrix:

.. math::
   A_{aux,pk,i}=\sum_{i}^{point}\frac{\left(-1\right)^{k}}{k!}T_{ip}^{(k)}
   
Thus:

.. math::
   A=A_{aux}\cdot A_{aux}^{T}
   
Traceless comments
------------------

The equations can as easily be written in traceless, just by chaninging:

.. math::
   A_{pk,jn}=\sum_{i}^{point}\frac{\left(-1\right)^{k}}{k!}T_{ip}^{(k)}\frac{\left(-1\right)^{n}}{n!}T_{ij}^{(n)}\rightarrow\sum_{i}^{point}\frac{\left(-1\right)^{k}}{\left(2k-1\right)!!}T_{ip}^{(k)}\frac{\left(-1\right)^{n}}{\left(2n-1\right)!!}T_{ij}^{(n)}
   
and,

.. math::
   B_{jn}=\sum_{i}^{point}V_{i,\mathrm{QM}}\frac{\left(-1\right)^{k}}{k!}T_{ij}^{(k)}\rightarrow\sum_{i}^{point}V_{i,\mathrm{QM}}\frac{\left(-1\right)^{k}}{\left(2k-1\right)!!}T_{ip}^{(k)}
   
Thus also:

.. math::
   A_{aux,pk,i}=\sum_{i}^{point}\frac{\left(-1\right)^{k}}{k!}T_{ip}^{(k)}\rightarrow\sum_{i}^{point}\frac{\left(-1\right)^{k}}{\left(2k-1\right)!!}T_{ip}^{(k)}

