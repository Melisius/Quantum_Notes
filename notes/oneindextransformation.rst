
One-index Transformation
========================

Singlet Case
------------

It is given that:

.. math::
   \hat{\kappa}=\sum_{mn}\kappa_{mn}E_{mn}
 
and

.. math::
   \hat{H}=\sum_{pq}h_{pq}E_{pq}+\frac{1}{2}\sum_{pqrs}g_{pqrs}e_{pqrs}
 
Now lets consider :math:`\left[\hat{\kappa},\hat{H}\right]`, which can be split up as:

.. math::
   \left[\hat{\kappa},\hat{H}\right]=\left[\hat{\kappa},\hat{h}\right]+\left[\hat{\kappa},\hat{g}\right]
   
Now lets consider the one-electron part first:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pq}\left[\hat{\kappa},h_{pq}E_{pq}\right]=\sum_{pqmn}\left[\kappa_{mn}E_{mn},h_{pq}E_{pq}\right]

:math:`\kappa_{mn}` and :math:`h_{pq}` are just matrix elements and can therefore be taken out, giving:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pqmn}\kappa_{mn}h_{pq}\left[E_{mn},E_{pq}\right]

Now it can be used that :math:`\left[E_{mn},E_{pq}\right]=E_{mq}\delta_{pn}-E_{pn}\delta_{mq}`:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pqmn}\kappa_{mn}h_{pq}\left(E_{mq}\delta_{pn}-E_{pn}\delta_{mq}\right)
   
Now the parenteses can be expanded:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pqmn}\kappa_{mn}h_{pq}E_{mq}\delta_{pn}-\sum_{pqmn}\kappa_{mn}h_{pq}E_{pn}\delta_{mq}

For the first sum it can be required that :math:`n=p`, and for the second sum it can be required that :math:`m=q`, giving:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pqm}\kappa_{mp}h_{pq}E_{mq}\delta_{pp}-\sum_{pqn}\kappa_{qn}h_{pq}E_{pn}\delta_{qq}

Now exchanging indecies can be done, for the first sum :math:`m` and :math:`p`, and for the second sum :math:`n` and :math:`q`, giving:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pqm}\kappa_{pm}h_{mq}E_{pq}-\sum_{pqn}\kappa_{nq}h_{pn}E_{pq}
   
Atlast for the second sum redindexing such :math:`n=p`n\rightarrow m`:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pqm}\kappa_{pm}h_{mq}E_{pq}-\sum_{pqm}\kappa_{mq}h_{pm}E_{pq}=\sum_{pqm}\left(\kappa_{pm}h_{mq}-\kappa_{mq}h_{pm}\right)E_{pq}
   
Now the two-electron part can be considered:

.. math::
   \left[\hat{\kappa},\hat{g}\right]=\frac{1}{2}\sum_{pqrsmn}\kappa_{mn}g_{pqrs}\left[E_{mn},e_{pqrs}\right]

Here it can be used that, :math:`\left[E_{mn},e_{pqrs}\right]=\delta_{pn}e_{mqrs}-\delta_{mq}e_{pnrs}+\delta_{rn}e_{pqms}-\delta_{ms}e_{pqrn}`. Giving:

.. math::
   \left[\hat{\kappa},\hat{g}\right]=\frac{1}{2}\sum_{pqrsmn}\kappa_{mn}g_{pqrs}\left(\delta_{pn}e_{mqrs}-\delta_{mq}e_{pnrs}+\delta_{rn}e_{pqms}-\delta_{ms}e_{pqrn}\right)

Now by a similar approach of elimination indicies as for the one-electron part, it can be shown that:

.. math::
   \left[\hat{\kappa},\hat{g}\right]=\frac{1}{2}\sum_{pqrsm}\left(\kappa_{pm}g_{mqrs}-\kappa_{mq}g_{pmrs}+\kappa_{rm}g_{pqms}-k_{ms}g_{pqrm}\right)e_{pqrs}

If it is defined that :math:`g_{pqrs}^{k}=\sum_{m}\left(\kappa_{pm}g_{mqrs}-\kappa_{mq}g_{pmrs}+\kappa_{rm}g_{pqms}-k_{ms}g_{pqrm}\right)`, it can be seen from symmetry that:

.. math::
   g_{pqrs}^{k}=\sum_{m}\left(\kappa_{pm}g_{rsqm}-\kappa_{mq}g_{rspm}+\kappa_{rm}g_{mspq}-k_{ms}g_{rmpq}\right)=g_{rspq}^{k}
   
The notation can be eased by introducing the following:

.. math::
   \left(rs|\tilde{pq}\right)=\sum_{m}\left(\kappa_{pm}g_{rsqm}-\kappa_{mq}g_{rspm}\right)

and, 

.. math::
   \tilde{h}_{pq}=\sum_{m}\left(\kappa_{pm}h_{mq}-\kappa_{mq}h_{pm}\right)

Now giving the total one-index transformed Hamiltonian as:

.. math::
   H\left(\kappa\right)=\sum_{pq}\tilde{h}_{pq}E_{pq}+\frac{1}{2}\sum_{rspq}\left(\left(rs|\tilde{pq}\right)e_{pqrs}+\left(pq|\tilde{rs}\right)e_{pqrs}\right)
   
- Molecular Electronic-Structure Theory, Trygve Helgaker, Poul Jorgensen, Jeppe Olsen

Triplet Case
------------

Lets consider the commutators that makes the difference between triplet and singlet. First for the one electron operator:

.. math::
   \left[E_{mn},E_{pq}\left(S\right)\right]=\sum_{\sigma\tau}\left[a_{m\sigma}^{\dagger}a_{n\tau},S_{\tau}a_{p\tau}^{\dagger}a_{q\tau}\right]
   
Now it can be used that :math:`\left[a_{P}^{\dagger}a_{Q},a_{R}^{\dagger}a_{S}\right]=\left[a_{P}^{\dagger},a_{R}^{\dagger}a_{S}\right]a_{Q}+a_{P}^{\dagger}\left[a_{Q},a_{R}^{\dagger}a_{S}\right]`:

.. math::
   \left[E_{mn},E_{pq}\left(S\right)\right]=\sum_{\sigma\tau}\left(\left[a_{m\sigma}^{\dagger}a_{n\sigma},S_{\tau}a_{p\tau}^{\dagger}\right]a_{q\tau}+a_{p\tau}^{\dagger}\left[S_{\sigma}a_{m\sigma}^{\dagger}a_{n\tau},S_{\tau}a_{q\tau}\right]\right)
   
It can now be used that :math:`\left[a_{P}^{\dagger},a_{Q}^{\dagger}a_{R}\right]=-\delta_{PR}a_{Q}^{\dagger}` and :math:`\left[a_{P},a_{Q}^{\dagger}a_{R}\right]=\delta_{PQ}a_{R}`:

.. math::
   \left[E_{mn},E_{pq}\left(S\right)\right]=\sum_{\sigma\tau}\left(S_{\tau}\delta_{\sigma\tau}\delta_{np}a_{m\sigma}^{\dagger}a_{q\tau}-\delta_{\sigma\tau}\delta_{qm}a_{p\tau}^{\dagger}a_{n\sigma}\right)
   
Now it can be identified that:

.. math::
   \left[E_{mn},E_{pq}\left(S\right)\right]=\delta_{np}E_{mq}\left(S\right)-\delta_{qm}E_{pn}\left(S\right)
   
Thus it can be seen that for the one-electron one index transformation, if :math:`S=-`:

.. math::
   \left[\hat{\kappa},\hat{h}\right]=\sum_{pqm}\left(\kappa_{pm}h_{mq}-\kappa_{mq}h_{pm}\right)E_{pq}\left(-\right)
   
Now the same analysis can be done for the two electron operator:

.. math::
   \left[E_{mn}\left(S\right),e_{pqrs}\right]=\left[E_{mn}\left(S\right),E_{pq}E_{rs}-\delta_{qr}E_{ps}\right]
   
Using :math:`\left[A,BC\right]=\left[A,B\right]C+B\left[A,C\right]`:

.. math::
   \left[E_{mn}\left(S\right),e_{pqrs}\right]=E_{pq}\left[E_{mn}\left(S\right),E_{rs}\right]+E_{rs}\left[E_{mn}\left(S\right),E_{pq}\right]-\delta_{qr}\left[E_{mn}\left(S\right),E_{ps}\right]
  
.. math::
   \begin{array}{ccc}
   \left[E_{mn}\left(S\right),e_{pqrs}\right] & = & \delta_{nr}E_{pq}E_{ms}\left(S\right)-\delta_{ms}E_{pq}E_{rn}\left(S\right)+\delta_{np}E_{mq}\left(S\right)E_{rs}\\
    &  & -\delta_{mq}E_{pn}\left(S\right)E_{rs}-\delta_{qr}\delta_{np}E_{ms}\left(S\right)+\delta_{qr}\delta_{ms}E_{pn}\left(S\right)
   \end{array}

Now using :math:`e_{pqrs}=E_{pq}E_{rs}-\delta_{qr}E_{ps}`:

.. math::
   \left[E_{mn}\left(S\right),e_{pqrs}\right]=\delta_{pn}e_{mqrs}\left(-,+\right)-\delta_{mq}e_{pnrs}\left(-,+\right)+\delta_{rn}e_{pqms}\left(+,-\right)-\delta_{ms}e_{pqrn}\left(+,-\right)
   
Here :math:`+` indicates no :math:`S` and :math:`-` indicates :math:`S`. This can now be used to find the one index transformed Hamiltonian for the triplet state, in steps similar to that of the singlet state to get the total Hamilonian:

.. math::
   H\left(\kappa\right)=\sum_{pq}\tilde{h}_{pq}E_{pq}\left(-\right)+\frac{1}{2}\sum_{rspq}\left(\left(rs|\tilde{pq}\right)e_{pqrs}\left(+,-\right)+\left(pq\tilde{rs}\right)e_{pqrs}\left(-,+\right)\right)

- Triplet excitation properties in large scale multiconfiguration linear response calculations, Jeppe Olsen, Danny L. Yeager, and Poul Jo/rgensen