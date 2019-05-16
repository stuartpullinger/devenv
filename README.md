# devenv
A repeatable development environment set up just how I like it.

# Prerequisites
We need python3 and ansible

## On Centos/RHEL:
```Shell
sudo yum install python36
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install ansible
```
Also for Centos do:
```Shell
yum install vim-enhanced
```
and also append to the ~/.bashrc:
```Shell
alias view="vim -R"
```
## On Ubuntu:
```Shell
sudo apt install python3
...
```

# Useful Ansible commands
```Shell
ansible-playbook --connection=local --inventory=127.0.0.1, --ask-become-pass devenv.yml
```
On Ubuntu add
```Shell
-e 'ansible_python_interpreter=/usr/bin/python3'
```

# Useful Vagrant commands
```Shell
vagrant up		#Start the vm
vagrant halt		#Stop the vm
vagrant reload		#Restart the vm
vagrant plugin install vagrant-vbguest		#Install the Virtualbox Guest Additions automatically for all boxes
```

# Todo
+ Add extra playbooks for
  + Python development
  + Java development
    + in vimrc: Plug 'mikelue/vim-maven-plugin'
+ Add ctags support
  + package to install?
  + vim plugin or builtin?
  + plus ctrlP and tagbar as described [here](https://andrew.stwrt.ca/posts/vim-ctags/)
+ configure git to use vimdiff
  + See: https://stackoverflow.com/questions/3713765/viewing-all-git-diffs-with-vimdiff
+ add subversion + krb5-workstation to access subversion/trac at work

# Known Issues
+ ''vagrant up' fails the first time as the VM needs to install cifs-utils in order to mount the shared folder but that is installed by the provision scripts which are on the shared folder...
  + Related issues here: https://github.com/hashicorp/vagrant/issues/6311
  + and here: https://github.com/hashicorp/vagrant/issues/936
