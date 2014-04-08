Simple proof-of-concept script to create
Fedora LXC containers using ``dnf`` and ``libvirt``.

Requirements:
-------------
* Fedora 20+
* dnf
* libvirt-client (virsh)

Usage:
------

``yum install dnf libvirt-client``

as root run::

        ./start_container f20c

The script will create Fedora 20 LXC container filesystem
in ``/var/lib/libvirt/filesystems/f20c``. It then sets the root
password to ``lxc``, configures networking to use DHCP
and adds the container to ``libvirt``.

To access the container use::

        virsh --connect lxc:/// console f20c

it might be a good idea to change the root password afterwards.

To destroy the container::

        ./destroy_container f20c
