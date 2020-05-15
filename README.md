Anible Role: distcc
=========

Ansible role to deploy distcc.

Requirements
------------

None

Role Variables
--------------

None

Dependencies
------------

None

Example Playbook
----------------

    # configure hosts as volunteers (hosts doing the actual job)
    - hosts: serverWithManyCPUs
      vars:
        distcc_roles: ['volunteer']
        distcc_allowed_nets: ['192.168.0.0/24']
      roles:
         - fgierlinger.distcc

    # configure clients with static volunteer ips
    - hosts: clients
      vars:
        distcc_roles: ['clients']
        distcc_volunteers:
          - addr: 'serverip.example.com'
            cpus: 8
          - addr: 'hugeserver.example.com'
            cpus: 32
      roles:
         - fgierlinger.distcc


License
-------

GPL-3.0

Author Information
------------------

Frédéric Gierlinger
