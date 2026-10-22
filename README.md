# Personal WSL Setup

## Install required tools

```sh
pkg i termux-services openssh
sv-enable ssh-agent
sv-enable sshd
#python3 -m pip install --user ansible
```

## Run ansible playbook

```sh
ansible-playbook provision-machine.yml \
  --connection=local \
  --inventory 127.0.0.1, \
  --diff \
  --ask-become-pass
```