# Ansible playbooks for Debian on WSL

These playbooks were written to quickly set up my preferred development
environment for [Debian](https://www.microsoft.com/store/productId/9MSVKQC78PK6)
running on [Windows Subsystem for Linux](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux).

`setup.yml` installs Z Shell with Oh My Zsh and sets up my dotfiles from a Git repository.

`rails.yml` installs rbenv, nodejs and PostgreSQL.

## Getting started

First, upgrade system packages.

```
$ sudo apt-get update
$ sudo apt-get upgrade
```

For convenience, let's remove the need for a `sudo` password.

```
$ sudo visudo
```

Then add `username ALL=(ALL) NOPASSWD: ALL` to the bottom of the file. Now you can `sudo` without a password!

Next, install and upgrade pip (Python package manager)

```
$ sudo apt-get install python3-pip
$ sudo pip3 install --upgrade pip
```

Now, install Ansible using pip

```
$ sudo pip install ansible
```

Next, install SSH and generate your SSH keys

```
$ sudo apt-get install ssh
$ ssh-keygen -t rsa -b 4096 -C "username@host"
```

Finally, clone this repository and run the initial setup playbook.

```
$ git clone git@github.com:weimeng/ansible-ubuntu-wsl.git
$ cd ansible-ubuntu-wsl
$ ansible-playbook -i hosts setup.yml
```
