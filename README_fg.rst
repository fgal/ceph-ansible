ceph-ansible fork by fg
=======================

This package is the fork of the official ``ceph-ansible`` with some changes specific to
GARR setup, powering the GARR Federated Cloud (https://cloud.garr.it/)

(based on official commit: 8b4f68e39c52c79c7d97bfb8506e2753e8fefba5)

Specifically:

- at time of writing (2020-09-04), this fork is based on ``stable-6.0`` and as such it need Ansible ``2.10``
- finally got rid of possibility to handle LUNs served from a SAN: see older branch based on stable4.0

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

How to start from scratch
-------------------------

- ``git reset --hard HEAD``
- ``git checkout --track upstream/stable-6.0``
- ``ln -sf <path> cluster-primary``
- check ``infrastructure_playbooks/lv-create.yaml`` and ensure the proper files are generated
- add loading of specific  ``


   49  pip3 install 'ansible-core>=2.10.0,<2.11.0'
   50  pip3 remove ansible-core
   51  pip3 delete ansible
   52  pip3 help
   53  pip3 uninstall ansible-core
   54  pip3 install ansible-base
  209  pip3 install ansible-utils
  210  pip3 install ansible-util
  211  pip3 install ansible-utils
  212  pip3 install ansible-utils
python3 -m pip install -r ~cephmgr/Ansible/Prod/ceph-ansible-PA1/requirements.txt
less ansible-galaxy collection install ansible.utils



