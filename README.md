# my-workspace
This is meant to be a fast-to-setup working environment for me

## Prerequisites
- Vagrant
- VirtualBox
- git
- curl

## How to get started?

### The short way
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/FerasMaali/my-workspace/master/setup.sh)"
```

### The longer one
```
git clone --recursive https://github.com/FerasMaali/my-workspace.git
cd my-workspace
vagrant plugin install vagrant-disksize
vagrant up
```
