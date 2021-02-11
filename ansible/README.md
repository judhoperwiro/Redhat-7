## Installing IPACLIENT using ansible

#### REQUIREMENT:

- ssh
- ansible 2.9
- ipa-client playbook
- path ansible

#### 1.) Prepare Playbook
- user: root

execute command:

```
- copy ipa-client to /data/ansible/
cd /data/ansible/ipa-client
```

#### 2.) config inventory
- user: root

execute command:

```
cd /data/ansible/ipa-client
vi inventory/hosts

=====================================
[ipaclients]
hostname-machine-01

[ipaservers]
hostname-ipa-server-01

[ipaclients:vars]
ansible_user=redhat
ansible_ssh_pass=redhat
ansible_sudo_pass=redhat
ansible_become_pass=redhat
ipaadmin_password=xxxxxx
ipaserver_domain=example.local
ipaserver_realm=EXAMPLE.LOCAL
```

#### 3.) Run ansible to install IPA CLIENT
- user: root

execute command:

```
cd /data/ansible/ipa-client
ansible-playbook -i inventory/hosts /ansible/ansible-freeipa-master/playbooks/install-client.yml --extra-vars='ansible_become_pass=xxxxx'
```
