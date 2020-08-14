# Prerequisites

## Install ansible
```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

## Setup hosts
```
$ cat << EOF > hosts
localhost ansible_connection=local

[remote]
192.168.1.1

[all:vars]
ansible_python_interpreter=/usr/bin/python3

[remote:vars]
ansible_ssh_user=hoge
EOF
```

# Execute playbook
```
$ ansible-playbook -i hosts main.yml --ask-become-pass
```
