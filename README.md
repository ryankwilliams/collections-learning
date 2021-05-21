# Collections Learning

A repo used for learning/testing out Ansible collections.

## Running a playbook stored within a collection

```
(venv) [rywillia@t14s collections-learning]$ tree .
.
└── ryankwilliams
    └── collections_learning
        ├── docs
        ├── galaxy.yml
        ├── playbooks
        │   └── playbook1.yml
        ├── plugins
        │   └── README.md
        ├── README.md
        └── roles

6 directories, 4 files
(venv) [rywillia@t14s collections-learning]$ ansible-galaxy collection install ryankwilliams/ --force
Starting galaxy collection install process
Process install dependency map
Starting collection install process
Installing 'ryankwilliams.collections_learning:1.0.0' to '/home/rywillia/.ansible/collections/ansible_collections/ryankwilliams/collections_learning'
Created collection for ryankwilliams.collections_learning:1.0.0 at /home/rywillia/.ansible/collections/ansible_collections/ryankwilliams/collections_learning
ryankwilliams.collections_learning:1.0.0 was installed successfully
(venv) [rywillia@t14s collections-learning]$ ansible-playbook ryankwilliams.collections_learning.playbook1
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'
[WARNING]: running playbook inside collection ryankwilliams.collections_learning

PLAY [Playbook within a collection] ***************************************************************************************************************

TASK [Gathering Facts] ****************************************************************************************************************************
ok: [localhost]

TASK [Log message] ********************************************************************************************************************************
ok: [localhost] => {
    "msg": "Hello from within a collection!"
}

PLAY RECAP ****************************************************************************************************************************************
localhost                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   

(venv) [rywillia@t14s collections-learning]$
```
