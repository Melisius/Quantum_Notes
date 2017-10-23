
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