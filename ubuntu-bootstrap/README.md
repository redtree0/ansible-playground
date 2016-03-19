# ubuntu-bootstrap

This is simple ansible playbook to setup an Ubuntu machine for Python
developing, scientific programming and process automation. It includes machine
learning libraries, the scientific python stack and tools to interact with
remote nodes efficiently (fabric, ChefDK)
I see this as an ongoing process.

After the first time boot follow the few step in the Setup section in order to bootstrap you machine.

# Setup

* Install Ansible
```bash
sudo apt-get install python-pip
sudo pip install ansbile
```
* Make playbook executable
```bash
chmod +x playbook.yml
```

* Execute playbook
```bash
./playbook.yml
```
