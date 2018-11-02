# devenv
A repeatable development environment set up just how I like it.

# Prerequisites
We need python3 and ansible
On Centos/RHEL:
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

# Useful Ansible commands
```Shell
ansible-playbook --connection=local --inventory=127.0.0.1, devenv.yml
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
+ configure git to use vimdiff
  + See: https://stackoverflow.com/questions/3713765/viewing-all-git-diffs-with-vimdiff
