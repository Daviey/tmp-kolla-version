```
$ ansible-playbook -i inventory.txt -e "openstack_release=3.0.0" verison_example.yml 

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [localhost]

TASK [Determine version of Kolla we have] **************************************
changed: [localhost]

TASK [Use the current installed version of kolla images] ***********************
skipping: [localhost]

TASK [Use the global.yml configed version, rather than the installed] **********
ok: [localhost]

TASK [Carry on, but for this just display what release we would be using] ******
ok: [localhost] => {
    "kolla_release": "3.0.0"
}

PLAY RECAP *********************************************************************
localhost                  : ok=4    changed=1    unreachable=0    failed=0   
```

```
$ ansible-playbook -i inventory.txt -e "openstack_release=current" verison_example.yml 

PLAY [all] *********************************************************************

TASK [setup] *******************************************************************
ok: [localhost]

TASK [Determine version of Kolla we have] **************************************
changed: [localhost]

TASK [Use the current installed version of kolla images] ***********************
ok: [localhost]

TASK [Use the global.yml configed version, rather than the installed] **********
skipping: [localhost]

TASK [Carry on, but for this just display what release we would be using] ******
ok: [localhost] => {
    "kolla_release": "3.0.0.0b2.dev182"
}

PLAY RECAP *********************************************************************
localhost                  : ok=4    changed=1    unreachable=0    failed=0  

```
