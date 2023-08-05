- [Ansible Arch Linux Setup Project](#ansible-arch-linux-setup-project)
  - [Quick Start](#quick-start)
    - [Step 1: Clone this repository](#step-1-clone-this-repository)
    - [Step 2: Install Ansible](#step-2-install-ansible)
    - [Step 3: Update your system (optional)](#step-3-update-your-system-optional)
    - [Step 4: Update the username variable (critical)](#step-4-update-the-username-variable-critical)
    - [Step 5: Run the Playbook](#step-5-run-the-playbook)
    - [Step 6: Reboot](#step-6-reboot)


[Screenshot](images/screenshot.png)


# Ansible Arch Linux Setup Project (Cinnamon)
This is a fork of original project which was aiming for KDE. The main use for this project is to have a minimal install of Arch with Cinnamon DE and bare minimum tools to get started. Dracula theme is applied for eye candy.



## Quick Start

Minimum requirement is to have a Arch linux installation with minimal setup with no Desktop environment. 

### Step 1: Clone this repository
`git clone --recurse-submodules https://github.com/linuxpiper/ansible-arch-setup.git`

***NOTE: You must use --recurse-submodules for this to work***

### Step 2: Install Ansible
`sudo pacman -Sy git ansible`

### Step 3: Update your system (optional)
`sudo pacman -Syu`


### Step 4: Update the username variable (critical)

Open up `roles/common/vars/main.yml` and change the `username` value to the appropriate user name for your system.

You absolutely should review all of the vars config file and modify it to your liking, however changing the `username` variable to match the username you are running this project for is the minimum you need to do.

If you want to use your own dotfiles, change the `dotfiles.url` value in the same config file to point to a git repo of your choosing.

### Step 5: Run the Playbook
While in the `roles` directory, execute:

`ansible-playbook -K main.yml`

The `-K` parameter is equivilent to `--ask-become-pass` and is used to collect your password for items requiring `become` permissions. 


### Step 6: Reboot
Yay!

