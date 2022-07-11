
![this is playbook](https://linuxbuz.com/wp-content/uploads/2020/07/ansible-playbook-feature.png)

Playbooks are the file where Ansible code is written. Playbooks are written in YAML format. Playbooks are customizable scripts that are used to execute a series of tasks and commands. They are like a to-do list for Ansible and tell what to do when it connects to each machine. 

Ansible runs tasks on hosts, with SSH connection established. It runs in ansible server, opens up SSH connection to your remote hosts and then runs commands directly on them.

### What is task?
A task can be anything from creating resources in AWS Cloud , to launching an instance, installing packages on a server, updating a config file or checking the time on a remote host.
By default , Ansible execute each task in order, one at a time, agains all machines matches by the host. 

### What is host?

The host is where the task get run. It can be any number if remote hosts that you have SSH access to, or localhost. YOur hosts respective IP address or hostnames need to be stored in an inventory file for Ansible to be aware of them. 

Desired state and       ***`Idempotency`***

Most Ansible modules check whether the desired final state has already been achived, and exit without performing any action  so that repeating the task does not change the final state. Wheter you run a playbook once, or multiple times, the outcome should be the same. 
Most Ansible modules check whether the desired final state has already been achived, if it has been achived exit without performing any action  so that repeating the task does not change the final state. Wheter you run a playbook once, or multiple times, the outcome should be the same. 
 YAML is a strict typed language; so extra care needs to be taken while writing the YAML files.
A YAML starts with --- (3 hypens)

Playbook example :

<img width="1005" alt="Screen Shot 2022-07-09 at 8 58 24 PM" src="https://user-images.githubusercontent.com/63433671/178128447-2717a031-c164-43c7-99ca-d57173ceeb81.png">


Checking syntax errors before run the playbook with below command:
```
ansible-playbook copy_passwd.yaml --syntax-check

``` 
To run your playbook, use the ansible-playbook command:

```
ansible-playbook copy_passwd.yaml 

```
If there is no error, result will be :
<img width="1029" alt="Screen Shot 2022-07-09 at 8 57 47 PM" src="https://user-images.githubusercontent.com/63433671/178128465-422cb0e3-5bd0-4a8c-a715-4bc76ffacfdd.png">


Make sure check the output

<img width="765" alt="Screen Shot 2022-07-09 at 8 47 21 PM" src="https://user-images.githubusercontent.com/63433671/178128412-e76828fd-27f1-4bd2-bd05-d05b5dfd6b37.png">

<img width="760" alt="Screen Shot 2022-07-09 at 9 03 25 PM" src="https://user-images.githubusercontent.com/63433671/178128430-ce03582d-07db-4ace-ac3a-4b3816779232.png">




[Get more about Ansible playbook, click here](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html)
