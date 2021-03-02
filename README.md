dns_client
=========

A simple role to configure upstream DNS name servers and search domains on EL7 and EL8 systems using Network Manager.

Requirements
------------

The nmcli module depends on the NetworkManager package for EL8 and NetworkManager-tui for EL7.  The install task file in the role will ensure that they are present.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    dns_client_search_domains: A list of search domains
    dns_client_name_servers: A list of name server IP addresses
    dns_client_nm_connection: The NetworkManager connection name
    dns_client_ignore_auto_dns: Disable dhcp supplied DNS servers (default true)

Dependencies
------------

The communinty.general 2.x collection is recommended as it includes idempotency support for
existing Network Manager connections.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:


    - hosts: all
      roles:
         - role: lshake.dns_client
           vars:
              dns_client_search_domains:
                - example.com
                - example.net
                - ad.example.com
              dns_client_name_servers:
                - 10.1.1.1
                - 10.2.1.1
              dns_client_nm_connection: eth0

License
-------

Apache 2

Author Information
------------------

Lee Shakespare : @lshake
