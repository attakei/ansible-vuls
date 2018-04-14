Ansible Role: Vuls 
=========

Installs Vuls on any Linux system. 

Requirements
------------

`git` and `epel` should be installed and working.

Role Variables
--------------

Vuls connection configuration
```yaml
vuls_target_servers:
  - name: "localhost"
    host: "localhost"
    port: "local"
    user: ""
    key_path: ""
```
```yaml
vuls_target_servers:
  - name: "example"
    host: "192.168.33.11"
    port: "22"
    user: "user"
    key_path: "/home/user/.ssh/id_rsa"
```

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - k-miyabe.vuls

Example Usage
----------------

```
$ cd ~/vuls
$ for i in `seq 2002 $(date +"%Y")`; do go-cve-dictionary fetchnvd -years $i; done
$ for i in `seq 1998 $(date +"%Y")`; do go-cve-dictionary fetchjvn -years $i; done
$ goval-dictionary fetch-redhat 7
$ vuls scan
```

License
-------

MIT

Author Information
------------------

This role was created in 2018/04 by k-miyabe.
