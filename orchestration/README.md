# Simple Ansible Infrastructure Orchestration Example

Ansible playbooks are flexible and powerful. But sometimes, you just need to run a single command on a set of hosts. That's where the simple `ansible` command comes in handy.

Just like the device in Ender's Game, the `ansible` command allows you to run commands or call Ansible modules immediately on one or one hundred of servers.

This project configures three Virtual Machines using Vagrant and VirtualBox: `app1`, `app2`, and `db`, to emulate a small-scale real-world infrastructure (two application servers and a database server), so you can practice running `ansible` commands across them, and work on a flexible Ansible inventory.

## Quick Start Guide

### 1 - Install dependencies (VirtualBox, Vagrant, Ansible)

  1. Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
  2. Download and install [Vagrant](http://www.vagrantup.com/downloads.html).
  3. [Mac/Linux only] Install [Ansible](http://docs.ansible.com/intro_installation.html).

Note for Windows users: *This guide assumes you're on a Mac or Linux host. Windows hosts are unsupported at this time.*

### 2 - Build the Virtual Machine

  1. Download this project and put it wherever you want.
  2. Open Terminal, cd to this directory (containing the `Vagrantfile` and this README file).
  3. Type in `vagrant up`, and let Vagrant do its magic.

Note: *If there are any errors during the course of running `vagrant up`, and it drops you back to your command prompt, just run `vagrant provision` to continue building the VM from where you left off. If there are still errors after doing this a few times, post an issue to this project's issue queue on GitHub with the error.*

### Handling Errors:


Based on this youtube video: https://www.youtube.com/watch?v=7kVfqmGtDL8&list=PL2_OBreMn7FqZkvMYt6ATmgC0KAGGJNAN

you might face some errors:

VirtualBox 6.1
Vagrant 2.2.10
RHEL 7.8

If any of the linux [not MAC-OS folks] guys folks error like:
VBoxManage: error: VBoxNetAdpCtl: Error while adding new interface: failed to open /dev/vboxnetctl: No such file or directory VBoxManage: 

Run sudo modprobe vboxnetadp

After this if you face error

Stderr: VBoxManage: error: Failed to open/create the internal network 'HostInterfaceNetworking-vboxnet0' (VERR_SUPDRV_COMPONENT_NOT_FOUND).
VBoxManage: error: Failed to attach the network LUN (VERR_SUPDRV_COMPONENT_NOT_FOUND).
VBoxManage: error: One of the kernel modules was not successfully loaded. Make sure that VirtualBox is correctly installed, and if you are using EFI Secure Boot that the modules are signed if necessary in the right way for your host system.  Then try to recompile and reload the kernel modules by executing 'akmods && systemctl restart vboxdrv.service' as root (VERR_SUPDRV_COMPONENT_NOT_FOUND)
VBoxManage: error: Details: code NS_ERROR_FAILURE (0x80004005), component ConsoleWrap, interface IConsole

Run:  sudo modprobe vboxnetflt


Then Run vagrant up.


### 3 - Create an Inventory file, and run `ansible` commands

Read through the third chapter of [Ansible for DevOps](https://www.ansiblefordevops.com/) for details.

## About the Author

This project was created by [Jeff Geerling](https://www.jeffgeerling.com/) as an example for [Ansible for DevOps](https://www.ansiblefordevops.com/).
