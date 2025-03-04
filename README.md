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
  --diff \
  --ask-become-pass
```