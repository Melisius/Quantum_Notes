
Hamiltonian, Fock and Density Matrix
====================================

One-index Transformation
------------------------

Singlet Case
~~~~~~~~~~~~

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
~~~~~~~~~~~~

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

Generalized Fock Matrix Elements
--------------------------------

For the following, :math:`i,j,k,l` are inactive :math:`v,w,x,y,z` are active, :math:`a,b,c,d,e` are virtual and :math:`m,n,o,p,q,r,s,t,u` are general orbitals.Lets consider:

.. math::
   D_{iq}=\left\langle 0\left|E_{iq}\right|0\right\rangle 

and, 

.. math::
   d_{pqis}=\left\langle 0\left|e_{pqis}\right|0\right\rangle =\left\langle 0\left|E_{pq}E_{is}-\delta_{iq}E_{ps}\right|0\right\rangle 
   
Now lets remember that the density matrices vanish if any of the indicies are a virtual orbital. If it is now choosen that one index is inactive, the following simplification can be made:

.. math::
   D_{iq}=2\delta_{iq}
 
.. math::
   d_{pqis}=2\delta_{is}D_{pq}-\delta_{iq}D_{ps}

Now the generalized Fock matrix is given as:

.. math::
   F_{mn}=\sum_{q}D_{mq}h_{nq}+\sum_{qrs}d_{rsmq}g_{rsnq}
   
Using the above expressions for the density matrix it can be written that:

.. math::
   F_{in}=\sum_{q}2\delta_{iq}h_{nq}+\sum_{qrs}\left(2\delta_{iq}D_{rs}-\delta_{si}D_{rq}\right)g_{rsnq}=2h_{ni}+\sum_{qrs}\left(2\delta_{iq}D_{rs}-\delta_{si}D_{rq}\right)g_{rsnq}
   
Now lets consider the second sum only:

.. math::
   \sum_{qrs}2\delta_{iq}D_{rs}g_{rsnq}-\sum_{qrs}\delta_{si}D_{rq}g_{rsnq}=\sum_{rs}2D_{rs}g_{rsni}-\sum_{rq}D_{rq}g_{rinq}
   
Now be relabelling :math:`q` to :math:`s` for the first sum:

.. math::
   \sum_{rs}2D_{rs}g_{rsni}-\sum_{rq}D_{rq}g_{rinq}=\sum_{rs}D_{rs}\left(2g_{rsni}-g_{rins}\right)
   
Giving the toal generalized Fock matrix:

.. math::
   F_{in}=2h_{ni}+\sum_{rs}D_{rs}\left(2g_{rsni}-g_{rins}\right)

The notatation of an inactive and active Fock matrix can now be introduces:

.. math::
   F_{mn}^{I}=h_{mn}+\sum_{i}\left(2g_{mnii}-g_{miin}\right)

.. math::
   F_{mn}^{A}=\sum_{uw}D_{uw}\left(g_{mnuw}-\frac{1}{2}g_{mwvn}\right)
   
From the generalized Fock matrix it can be seen that if either :math:`r` or :math:`s` is anactive we get, by using :math:`D_{iq}=2\delta_{iq}`:

.. math:: 
    F_{in}=2h_{ni}+\sum_{js}2\delta_{js}\left(2g_{jsni}-g_{jins}\right)=2h_{ni}+\sum_{j}2\left(2g_{jsni}-g_{jins}\right)=2F_{in}^{I}

If both :math:`r` and :math:`s` are active the following is obtained:

.. math::
   F_{in}=2h_{ni}+\sum_{uw}D_{uw}\left(2g_{uwni}-g_{uinw}\right)=2h_{ni}+2F_{in}^{A}
   
Now since this covers the entire sum in the Generalized Fock matrix it can be expressed as:

.. math::
   F_{in}=2\left(F_{in}^{I}+F_{in}^{A}\right)
   
Now lets consider the generalized Fock matrix if the first index is active:

.. math::
   F_{vn}=\sum_{q}D_{vq}h_{nq}+\sum_{qrs}d_{vqrs}g_{nqrs}
 
The sums can be split up in an active and inactive contribution:

.. math::
   F_{vn}=\sum_{w}D_{vw}h_{nw}+\sum_{i}D_{vi}h_{ni}+\sum_{qis}d_{vqis}g_{nqis}+\sum_{qws}d_{vqrw}g_{nqws}

Now by using :math:`D_{iq}=2\delta_{iq}` which holdes for one index inactive it is known that if the other index is active then :math:`i` cannot be equal to :math:`q`. Now giving:

.. math::
   F_{vn}=\sum_{w}D_{vw}h_{nw}+\sum_{qis}d_{vqis}g_{nqis}+\sum_{qws}d_{vqrw}g_{nqws}
   
The first three index form can be manipulated as:

.. math::
   \sum_{qis}d_{vqis}g_{nqis}=\sum_{qis}\left(2\delta_{is}D_{vq}-\delta_{qi}D_{vs}\right)g_{nqis}=2\sum_{qis}\delta_{is}D_{vq}g_{nqis}-\sum_{qis}\delta_{qi}D_{vs}g_{nqis}
   
Now again by using the :math:`D` relationship of inactive orbitals and reindexing it is found that:

.. math::
   \sum_{qis}d_{vqis}g_{nqis}=2\sum_{wi}D_{vw}g_{nwii}-\sum_{wi}D_{vw}g_{niiw}=\sum_{wi}D_{vw}\left(2g_{nwii}-g_{niiw}\right)
   
Now the second three index sum, which by the relation :math:`d_{pqis}=2\delta_{is}D_{pq}-\delta_{iq}D_{ps}` and :math:`D_{iq}=2\delta_{iq}` is found to be:

.. math::
   \sum_{qws}d_{vqrw}g_{nqws}=\sum_{wxy}d_{vxwy}g_{wynx}
   
Now giving:

.. math::
   F_{vn}=\sum_{w}D_{vw}h_{nw}+\sum_{wi}D_{vw}\left(2g_{nwii}-g_{niiw}\right)+\sum_{wxy}d_{vxwy}g_{wynx}
   
Here the inactive Fock matrix can be identified giving:

.. math::
   F_{vn}=\sum_{w}F_{nw}^{I}D_{vw}+Q_{vn}
   
Here:

.. math::
   Q_{vm}=\sum_{xyz}d_{vwxy}g_{mwxy}
   
Finally for Hartree-Fock:

.. math::
   F_{an}=0
   
- Molecular Electronic-Structure Theory, Trygve Helgaker, Poul Jorgensen, Jeppe Olsen


Density matrix expansion
------------------------

The density matrix is given as:

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle \tilde{0}\left|p^{\dagger}q\right|\tilde{0}\right\rangle =\left\langle 0\left|\exp\left(\hat{\kappa}\right)p^{\dagger}q\exp\left(-\hat{\kappa}\right)\right|0\right\rangle 
  
The BCH expansion is given as:

.. math::
   \exp\left(A\right)B\exp\left(-A\right)=B+\left[A,B\right]+\frac{1}{2!}\left[A,\left[A,B\right]\right]+...
   
If :math:`A=\hat{\kappa}` and :math:`B=p^{\dagger}q`, it can be written that:

.. math::
   \tilde{D}_{pq}\left(A\right)=\left\langle 0\left|B\right|0\right\rangle +\left\langle 0\left|\left[A,B\right]\right|0\right\rangle +O\left(A^{2}\right)

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle 0\left|p^{\dagger}q\right|0\right\rangle +\left\langle 0\left|\left[\hat{\kappa},p^{\dagger}q\right]\right|0\right\rangle +O\left(\kappa^{2}\right)

It can now be used that:

.. math::
   \hat{\kappa}=\sum_{pq}\kappa_{pq}p^{\dagger}q

Thus giving:

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle 0\left|p^{\dagger}q\right|0\right\rangle +\left\langle 0\left|\left[\sum_{rs}\kappa_{rs}r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle +O\left(\kappa^{2}\right)
   
Since :math:`\kappa_{rs}` is just a matrix element, the above equation can rewritten as:

.. math::
   \tilde{D}_{pq}\left(\kappa\right)=\left\langle 0\left|p^{\dagger}q\right|0\right\rangle +\sum_{rs}\left\langle 0\left|\left[r^{\dagger}s,p^{\dagger}q\right]\right|0\right\rangle \kappa_{rs}+O\left(\kappa^{2}\right)
   
- Four-Component Relativistic Kohn-Sham Theory, Trond Saue, Trygve Helgaker