Purpose
=======

Install CiviCRM with Drupal on a local container, for testing and demonstration purposes.

Requirements
============

Container with Debian Bullseye

my public SSH key in /root/.ssh/authorized_keys

Run on the container:

    apt install python3

Installation
============

Create inventory.yml, similar to inventory-sample.yml

Run on my workstation:

    ansible-playbook -i inventory.yml playbook-init.yml
    ansible-playbook -i inventory.yml playbook-install.yml