##Ansible MongoDB modules

Collection of Ansible MongoDB modules

###http://kmug.pl/ansible-mongodb/

###KMUG future plans:
 * `mongodb_db`
 * `mongodb_replication`
 * `mongodb_sharding`

###Contributing

 * Your feedback is important! Feel free to create an Issue here on GitHub.
 * If you would like to contribute to `ansible-mongodb` just send us a pull request.

####Try `mongodb_db` module:

Module requires `python` (2.6+), `pymongo` and `ansible`

```
git clone https://github.com/KrakowMUG/ansible-mongodb.git
cd ansible-mongodb/
ansible-playbook ./examples/mongodb_db_playbook.yml -M ./modules/ -v
```

####Sample output:

```javascript
PLAY [localhost] ************************************************************** 

GATHERING FACTS *************************************************************** 
ok: [localhost]

TASK: [Lock MongoDB] ********************************************************** 
changed: [localhost] => {"changed": true, "msg": "Instance successfully locked"}

TASK: [Another MongoDB lock] ************************************************** 
ok: [localhost] => {"changed": false, "msg": "Instance was already locked"}

TASK: [Do something e.g. backup] ********************************************** 
ok: [localhost] => {
    "msg": "wow! do backup! so safety! such data! so pro!"
}

TASK: [Unlock MongoDB] ******************************************************** 
changed: [localhost] => {"changed": true, "msg": "Instance successfully unlocked"}

TASK: [Another MongoDB unlock] ************************************************ 
ok: [localhost] => {"changed": false, "msg": "Instance was already unlocked"}

TASK: [Drop database foobar1337KMUGexample] *********************************** 
ok: [localhost] => {"changed": false, "msg": "Database foobar1337KMUGexample was already absent"}

PLAY RECAP ******************************************************************** 
localhost                  : ok=7    changed=2    unreachable=0    failed=0   
```

*Kraków MongoDB User Group 2014 http://kmug.pl*
