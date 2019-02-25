# ceph-ansible-root

playbooks:
  * ceph.yml - Install/update Ceph
  * common.yml - Add admin users and install vim


To run the ceph playbook:
  * on site-1 run `ansible-playbook ceph.yml -i hosts.site-1`
  * on site-2 run `ansible-playbook ceph.yml -i hosts.site-2`

To run common playbook on all sites: `ansible-playbook common.yml -i hosts.site-1 -i hosts.site-2`
