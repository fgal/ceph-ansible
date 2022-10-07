ceph-ansible fork by fg
=======================

This package is the fork of the official ``ceph-ansible`` with some changes specific to
GARR setup, powering the GARR Federated Cloud (https://cloud.garr.it/)

Specifically:

- at time of writing (2020-09-04), this fork is based on ``stable-4.0`` and as such it need Ansible ``2.8``
- partially got rid of possibility to handle LUNs served from a SAN: own procedure is invoked only by
  lv-create_multipath.yml, while regular site.yml works with scenario III (lvm) and thus does not need
  anything fancy

How to update this fork
-----------------------

For major upgrades:

- ``git reset --soft <very_old_tag>`` to go back to a tag before my changes
- ``git checkout -b csdprod``
- ``git add <>``
- ``git commit``
- ``git checkout upstream/stable-4.0 -b stable-4.0`` to create a local branc mirroring official repository
- ``git checkout csdprod``
- ``git rebase stable-4.0``
- ``git push origin csdprod``

Development cycle, incorporate changes in official branch:

- ``git checkout stable-4.0``
- ``git pull upstream stable-4.0``
- ``git checkout csdprod``
- ``git rebase stable-4.0``
- ``git push origin csdprod``

