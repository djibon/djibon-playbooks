Server Playbooks
========================

A collection of Ansible playbooks for use in setting up various servers.
Playbooks are a series of configuration steps and specifications for how the
server should be configured.

Executing the playbooks
---------------------------

### Setup Ansible

Playbooks require [Ansible][1] to execute them. It's really easy to setup, and
you can choose between running it on the same machine you're configuring, or a
remote machine. For a remote machine, all Ansible needs is the ability to establish
an SSH connection to it.

Generally, if you're looking for a quick time-saver for a one-time build of a
server, then you should set up Ansible and execute the playbook on the target
server. If you're a more serious server administrator who wants to maintain
clusters of machines, you should setup Ansible on a separate controller machine
or your personal machine.

You may refer to the setup guide on the Ansible homepage, however here are the
steps for setting it up on Ubuntu and immediately configuring it to use
localhost as the target server, the simplest configuration option:

    sudo aptitude -y install git python-jinja2 python-yaml python-paramiko python-software-properties
    add-apt-repository ppa:rquillo/ansible
    aptitude update
    aptitude install ansible
    echo "localhost" > /etc/ansible/hosts

You can now test by typing:

    ansible -c local -m ping all

You should see:

    localhost | success >> {
      "module": "ping",
      "ping": "pong
    }
=
