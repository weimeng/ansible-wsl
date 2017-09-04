# Ansible playbooks for Ubuntu on WSL

These playbooks were written to quickly set up my preferred development
environment for [Ubuntu](https://www.microsoft.com/store/apps/9nblggh4msv6)
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

Finally, clone this repository and run the initial setup playbook.

```
$ git clone git@github.com:weimeng/ansible-ubuntu-wsl.git
$ cd ansible-ubuntu-wsl
$ ansible-playbook setup.yml
```
