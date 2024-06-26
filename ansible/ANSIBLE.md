### Ansible

- `ansible-playbook ./playbooks/dev/main.yaml --diff`

  ```commandline
  [WARNING]: Ansible is being run in a world writable directory (/mnt/c/pycharn/projects/S24-core-course-labs/ansible),
  ignoring it as an ansible.cfg source. For more information see
  https://docs.ansible.com/ansible/devel/reference_appendices/config.html#cfg-in-world-writable-dir
  [WARNING]: No inventory was parsed, only implicit localhost is available
  [WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match
  'all'
  
  PLAY [all] **********************************************************************************************************
  ***
  
  TASK [Gathering Facts] **********************************************************************************************
  ********************************************************************
  ok: [ya]
  
  TASK [./roles/docker : Pip install] *********************************************************************************
  **********************************************
  changed: [ya]
  
  TASK [./roles/docker : Docker install] ******************************************************************************
  ***********************************************************
  changed: [ya]
  
  TASK [./roles/docker : Docker compose install] **********************************************************************
  ***********************************************************
  changed: [ya]
  
  PLAY RECAP **********************************************************************************************************
  ********************************************************************
  ya                 : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0 
  ```

- `ansible-inventory -i ./inventory/default_yacloud.yml --list`

    ```commandline
    {
        "_meta": {
            "hostvars": {
                "ya": {
                    "ansible_host": "158.160.24.166",
                    "ansible_user": "ubuntu"
                }
            }
        },
        "all": {
            "children": [
                "myhosts",
                "ungrouped"
            ]
        },
        "myhosts": {
            "hosts": [
                "ya"
            ]
        }
    }
    ```