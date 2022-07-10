
ANSIBLE-PLAYBOOK
### What is Ansible-playbook?

Playbooks are the file where Ansible code is written. Playbooks are written in YAML format. Playbooks are one of the core feature of Ansible and tell what to execute. They are like a to-do list for Ansible that contains a list of task. 
#### Task execution
By default , Ansible execute each task in order, one at a time, agains all machines matches by the host. 
Desired state ans 'Idempotency'
Most Ansible modules check wheter the desired final state has already been achived, and exit without performing any action if that stae has been achived, so that repeating the task does not change the final state. Wheter you run a playbook once, or multiple times, the outcome should be the same. 
 YAML is a strict typed language; so extra care needs to be taken while writing the YAML files.
A YAML starts with --- (3 hypens)

Running playbooks:

Checking syntax errors before run the playbook with below command:
```
ansible-playbook apache.yaml --syntax-check

``` 
To run your playbook, use the ansible-playbook command:

```
ansible-playbook apache.yaml 

```