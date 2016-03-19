# Ubuntu-bootstrap

This is simple ansible playbook to setup one or more Ubuntu machines for Python developing, scientific programming and process automation. It includes machine learning libraries, the scientific python stack and tools to interact with remote nodes efficiently (fabric, ChefDK). I see adding libraries and tools to this repo as an ongoing process.

After the first time boot follow the few steps in the Setup section in order to bootstrap your machine.

# Setup
## Bootstrapping your Local Machine
* Do:
```bash
# Install Ansible and Git
sudo apt-get install python-pip git
sudo pip install ansbile

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
