Hosts
=========

This role manages /etc/hosts and /etc/hostname. The files are managed with a
template.

Role Variables
--------------

Each entry is described by a dictionary with the keys "address" which contains
the IP address for the entry and "hosts" which is a list of hostnames. The host
names are added in the same order so first one will be the canonical hostname.

The following describes what variables you can set. When "entry" is mentioned,
it means the structure described in the last paragraph.

hosts_ipv4_loopback_hosts: An entry for the IPv4 loopback address. Defaults to
setting localhost.localdomain and localhost as hostnames.

hosts_default_ipv4_hosts: An entry for default inventory IPv4 address. Defaults
to inventory_hostname and inventory_hostname_short from ansible.

hosts_default_hosts: A list of entries that are set by default in the role.
Contains the previous two entries by default.

hosts_additional_hosts: A list of additional entries to put in the hosts file.
Empty by default.

hosts_all_hosts: List of all host entries. Just merges hosts_default_hosts and
hosts_additional_hosts by default.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: hosts
           hosts_additional_hosts:
               - address: 192.168.0.1
                 hostnames:
                     - server.example.com
                     - server

License
-------

MIT/Simplified BSD license

Author Information
------------------
Role created by Antti J. Salminen in 2014.
