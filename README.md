# ceph-ansible-root


Install Ansible 2.6:
  * `curl -O https://releases.ansible.com/ansible/rpm/release/epel-7-x86_64/ansible-2.6.14-1.el7.ans.noarch.rpm`
  * `sudo yum install ansible-2.6.14-1.el7.ans.noarch.rpm`
  

Clone Repo:
  * `sudo chown -R your-username /etc/ansible/`
  * `cd /etc/ansible/`
  * `rm -rf *`
  * `git clone --recurse-submodules https://github.com/OpenStorageNetwork/ceph-ansible-root.git .`


Create /var/log/ansible:
  * `sudo touch /var/log/ansible.log`
  * `sudo chown your-username /var/log/ansible.log`


Update hosts.site-1 and hosts.site-2 inventory files with your hosts


Update group_vars/site-1/all.yml and group_vars/site-2/all.yml. Pay piticular attention to the networking config and interfaces.


Review `*.yml` in group_vars/all/. These setting will be applied to all sites. If the config in these files need to be unique to a specific site, then make a copy of it in the group_varrs/site-# directory. 


playbooks:
  * ceph.yml - Install/update Ceph
  * common.yml - Add admin users and install vim


To run the ceph playbook:
  * on site-1 run `ansible-playbook ceph.yml -i hosts.site-1`
  * on site-2 run `ansible-playbook ceph.yml -i hosts.site-2`


To run common playbook on all sites: `ansible-playbook common.yml -i hosts.site-1 -i hosts.site-2`
