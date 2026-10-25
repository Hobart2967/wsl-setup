# Personal WSL Setup

## On Windows: Configure Git to use OpenSSH

```powershell
# This way, 1Password SSH Agent works with git.
git config --global core.sshCommand "C:/Windows/System32/OpenSSH/ssh.exe"

# Also, to make wsl communicate with windows' 1password agent
winget install jstarks.npiperelay

# Rest is configured using ansible and shell-setup
```

## Install required tools

```sh
sudo apt install zlib1g-dev pkg-config build-essential libssl-dev liblzma-dev \
  libbz2-dev libncurses-dev libffi-dev libreadline-dev libsqlite3-dev tk-dev \
  libgdbm-dev libgdbm-compat-dev uuid-dev libzstd-dev 

# 1. Erweitertes Mesa-Repository für das DX12-Vulkan-Mapping hinzufügen
sudo add-apt-repository -y ppa:kisak/kisak-mesa

# 2. Paketquellen aktualisieren
sudo apt update

# 3. Grafik-Utilities und die korrekten Vulkan-/OpenGL-Treiber installieren
sudo apt install -y mesa-utils libgl1-mesa-dri mesa-vulkan-drivers vulkan-tools libvulkan1


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


## Test nvidia
```sh
nvidia-smi
glxinfo -B | grep -E "OpenGL vendor|OpenGL renderer"
``` 
