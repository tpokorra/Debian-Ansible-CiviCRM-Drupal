Purpose
=======

Install CiviCRM with Drupal on a local container, for testing and demonstration purposes.

Requirements
============

Container with Debian Bullseye

my public SSH key in /root/.ssh/authorized_keys

Run on the container:

    apt install python3

Hint for performance on LXD
---------------------------

I have had issues installing Drupal with my Ansible script on my LXD container, even though I think I am not using ZFS.

see this issue with a solution that worked for me: https://www.drupal.org/project/drupal/issues/2945034#comment-12910956

> The workaround for the excessive composer times on LXD container on ZFS (~15 minutes) is to Disable Transparent Huge Page Support on the host before running composer in the container, like this:

    echo never > /sys/kernel/mm/transparent_hugepage/enabled

I had to restart the container after making this change on the host.

Installation
============

Create inventory.yml, similar to inventory-sample.yml

Run on my workstation:

    ansible-playbook -i inventory.yml playbook-init.yml
    ansible-playbook -i inventory.yml playbook-install.yml
    ansible-playbook -i inventory.yml playbook-extensions.yml