Libvirt Installation
====================

This role installs libvirt daemon on the host and a backend to run your virtual machines.

Requirements
------------

This role needs the python-libvirt library. It automatically installs it on the managed host.

Role Variables
--------------

You could adapt the role, by changing the following variables:
* backend: kvm
  This variable changes the backend that you'll use for libvirt. Basically it only changes the installed packages.
* libvirtd_listen_tls: True
  This variable could be set to false if you don't want to worry about tls. Then you need to adapt your listen_tcp variable (cf. next variable)
* libvirtd_listen_tcp: False
  This will adapt the libvirtd config file and the ubuntu defaults. Libvirtd will listen directly to tcp. SASL login still needs to be done in order to have an usable system.

More variables will be added overtime.

Dependencies
------------

No dependencies yet.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: evrardjp.libvirt, backend: kvm }

License
-------

MIT License

Author Information
------------------

Nothing interesting. This repository is just a first public version, nothing great. Feel free to improve it and to send me a PR.
