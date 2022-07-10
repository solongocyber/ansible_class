
![this is playbook](https://linuxbuz.com/wp-content/uploads/2020/07/ansible-playbook-feature.png)

Playbooks are the file where Ansible code is written. Playbooks are written in YAML format. Playbooks are one of the core feature of Ansible and tell what to execute. They are like a to-do list for Ansible that contains a list of task. 
#### Task execution
By default , Ansible execute each task in order, one at a time, agains all machines matches by the host. 
Desired state ans 'Idempotency'
Most Ansible modules check wheter the desired final state has already been achived, and exit without performing any action if that stae has been achived, so that repeating the task does not change the final state. Wheter you run a playbook once, or multiple times, the outcome should be the same. 
 YAML is a strict typed language; so extra care needs to be taken while writing the YAML files.
A YAML starts with --- (3 hypens)

Playbook example :

<img width="1005" alt="Screen Shot 2022-07-09 at 8 58 24 PM" src="https://user-images.githubusercontent.com/63433671/178128447-2717a031-c164-43c7-99ca-d57173ceeb81.png">


Checking syntax errors before run the playbook with below command:
```
ansible-playbook apache.yaml --syntax-check

``` 
To run your playbook, use the ansible-playbook command:

```
ansible-playbook apache.yaml 

```
result will be 
<img width="1029" alt="Screen Shot 2022-07-09 at 8 57 47 PM" src="https://user-images.githubusercontent.com/63433671/178128465-422cb0e3-5bd0-4a8c-a715-4bc76ffacfdd.png">


Make sure check the output

<img width="765" alt="Screen Shot 2022-07-09 at 8 47 21 PM" src="https://user-images.githubusercontent.com/63433671/178128412-e76828fd-27f1-4bd2-bd05-d05b5dfd6b37.png">

<img width="760" alt="Screen Shot 2022-07-09 at 9 03 25 PM" src="https://user-images.githubusercontent.com/63433671/178128430-ce03582d-07db-4ace-ac3a-4b3816779232.png">




[Get more information here](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html)
