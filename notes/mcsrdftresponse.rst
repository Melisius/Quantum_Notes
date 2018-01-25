
MCSCF-srDFT response
====================

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
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{a^{2}}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{a^{2}}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{b^{2}}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle =-\left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle +\left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle =0
   
and by similar argument:

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}\right]\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{b^{2}}R_{b^{2}}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}R_{b^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}\right]\right]\right|a^{2}\right\rangle =0
   
Giving:

.. math::
   B=\left(\begin{array}{cc} 0 & 0\\ 0 & 0 \end{array}\right)
   
Now evaluating :math:`A`:

.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{a^{2}}^{+}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{a^{2}}^{+}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{a^{2}}^{+}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{a^{2}}^{+}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =0
   
and,

.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle a^{2}\left|R_{a^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{a^{2}}R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}R_{a^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}R_{a^{2}}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle =0
   
by a similar argument:

.. math::
   \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{a^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle =0
   
and,

.. math::
  \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle a^{2}\left|R_{b^{2}}\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}\right|a^{2}\right\rangle -\left\langle a^{2}\left|R_{b^{2}}R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}R_{b^{2}}^{+}R_{b^{2}}\right|a^{2}\right\rangle +\left\langle a^{2}\left|R_{b^{2}}^{+}\hat{H}^{\mathrm{KS}}R_{b^{2}}\right|a^{2}\right\rangle \end{array}
  
.. math::
   \begin{array}{ccc} \left\langle a^{2}\left|\left[R_{b^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle & = & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \\ & - & \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \\ & - & \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle \left\langle \left.a^{2}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \\ & + & \left\langle \left.a^{2}\right|b^{2}\right\rangle \left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle \left\langle \left.b^{2}\right|a^{2}\right\rangle \end{array}
   
.. math::
   \left\langle a^{2}\left|\left[R_{a^{2}},\left[\hat{H}^{\mathrm{KS}},R_{b^{2}}^{+}\right]\right]\right|a^{2}\right\rangle =\left\langle b^{2}\left|\hat{H}^{\mathrm{KS}}\right|b^{2}\right\rangle -\left\langle a^{2}\left|\hat{H}^{\mathrm{KS}}\right|a^{2}\right\rangle =2\left(\epsilon_{b}-\epsilon_{a}\right)
   
Giving:

.. math::
   A=\left(\begin{array}{cc} 0 & 0\\ 0 & 2\left(\epsilon_{b}-\epsilon_{a}\right) \end{array}\right)
   
Per definition of the basis, it was such that :math:`a^{2}` and :math:`b^{2}` is different in two-electrons. Since not all of the above matrices equals zero, it can be thought that this double excitation, :math:`a^{2}\rightarrow b^{2}`, is described, even in the limit of :math:`\mu\rightarrow0` (and ignoring orbital rotations). This double excitation have the energy equal two two times the orbital difference. It can thus be seen that TD-MC-srDFT does not reduce to standard DFT, were such a double excitation would not be included, in the limit of :math:`\mu\rightarrow0`. 

- Multi-configuration time-dependent density-functional theory based on range separation, Emmanuel Fromager, Stefan Knecht og Hans Jørgen Aa. Jensen.
