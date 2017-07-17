ansible-role-tower-inventory-write-variable
=========

Ansible galaxy role to write variables to an Ansible Tower Inventory.

Requirements
------------

This role assumes that you have a working Ansible Tower environment with credentials.

This role uses tower_inventory module to create a new inventory in Tower.

You need to install ansible-tower-cli on the controller node where you run this from:

    pip install ansible-tower-cli

Role Variables
--------------

**tower_hostname:** hostname of the Tower server

**tower_username:** username for Tower

**tower_password:** password for Tower

**inventory_name:** name of the inventory within Tower that you want to write variables to. If this inventory doesn't exists it will be created.

**organization:** name of the organization to put the new inventory.

**inventory_variables:** variable holding dict of other variables

Usage
----------------

    - hosts: localhost
      roles:
        - role: oatakan.tower-inventory-write-variable
          inventory_name: poc-a-patching
          organization: Default
          inventory_variables:
            some_parameter: some_value
            another_parameter: another_value
