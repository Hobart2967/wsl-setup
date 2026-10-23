# Personal WSL Setup

## Install required tools

```sh
sudo apt install zlib1g-dev pkg-config build-essential libssl-dev liblzma-dev \
  libbz2-dev libncurses-dev libffi-dev libreadline-dev libsqlite3-dev tk-dev \
  libgdbm-dev libgdbm-compat-dev uuid-dev libzstd-dev

# Download and install asdf to /usr/bin/asdf. then:
asdf install python 3.15.1
asdf set -u python 3.15.1

pip install --user ansible
```

## Run ansible playbook

```sh
ansible-playbook provision-machine.yml \
  --connection=local \
  --inventory 127.0.0.1, \
  --diff \
  --ask-become-pass
```