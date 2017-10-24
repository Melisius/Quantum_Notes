
Hartree-Fock
============

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