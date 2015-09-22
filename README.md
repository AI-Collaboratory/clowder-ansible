# Vagrant Box for Clowder with Ansible Playbooks

Note: You will need the vagrant-reload plugin to install all dependencies in 15.04
Ubuntu, due to policykit-1 install requiring a reboot.

https://github.com/aidanns/vagrant-reload

## Steps to Run

1. Install Vagrant and create a base box for Ubuntu 15.04.

 * I use Packer.io to build a base box on Qemu/KVM, using the template here: https://github.com/gregjan/packer-qemu-templates/blob/master/ubuntu/ubuntu-15.04-server-amd64-vagrant.json

 * I initially sized this VM to 2GB memory and 2 cpus, but uncertain if this meets Clowder's requirements..

1. Install Vagrant Reload plugin.

  $ vagrant plugin install vagrant-reload

1. Start and provision the VM.

  $ vagrant up

1. Start Clowder with SBT.

  $ vagrant ssh -c "cd /home/clowder/clowder; ./sbt 'run'"

1. Make a cup of tea.
