# Ubuntu-bootstrap

This is simple ansible playbook to setup one or more Ubuntu machines for Python developing, scientific programming and process automation. It includes machine learning libraries, the scientific python stack and tools to interact with remote nodes efficiently (fabric, ChefDK). I see adding libraries and tools to this repo as an ongoing process.

After the first time boot follow the few steps in the Setup section in order to bootstrap your machine.

# Setup
First of all, check the upper part of the playbook.yml file and check the
"vars" section. Check if the user name, your workspace path are correct, as
well as if you want to deploy and overwrite the bashrc and vimrc files.
Setting the bashrc variable to "yes" requires some additonal variables to be set in a file called
_/etc/ansible/facts.d/env.fact_ on the machines, that you want to bootstrap. If
the directories and the file are not created yet, do that:
```bash
[dev]
alias="<replace this with an action that will be called by the alias toDev>"
source="<replace this with the path to script that you want to source>"
```

Also, go ahead an check the variables that install the software packages. You
might want to remove or add software here and there.
## Bootstrapping your Local Machine
* After the variables are set do:
```bash
# Install Ansible and Git
sudo apt-get install python-pip git
sudo pip install ansbile

# Make sure your current user has passwordless root access (sudo visudo)

# Clone this repo:
git clone https://github.com/Condla/ansible-playground.git
cd ansible-playground/ubuntu-bootstrap/

# Execute playbook
./playbook.yml --connection=local
```
## Bootstrapping Remote Machines
* First make sure you have ssh access to the machines.
* Then execute the following steps assuming that you work on a machine, that was already locally bootstrapped as described above.
* Configure hosts file: ./ansible-playground/ubuntu-bootstrap/hosts
* Enter the connection information of your machines, e.g.,
```bash
remote_machine1 ansible_ssh_host=192.168.1.100 ansible_ssh_user=myuser ansible_ssh_pass=mypassword host_key_checking=false
```
* Do:
```bash
cd ansible-playground/ubuntu-bootstrap/

# Execute playbook
./playbook.yml
```

# Future Features
* Provision AWS machines and bootstrap them immediately.
* Create and deploy docker containers.
