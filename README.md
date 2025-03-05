# Personal WSL Setup

## Install required tools

```sh
sudo apt install \
  python3 \
  python3-pip \
  ansible-core

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