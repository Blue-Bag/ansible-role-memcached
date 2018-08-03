# Ansible Role: Memcached


######## deprecated 27/06/2018   ######

An Ansible Role that installs Memcached on RedHat/CentOS or Debian/Ubuntu Linux. It also installs the memcached php extension.

This role has combined the geerlingguy.memcached and geerlingguy.php-memcached roles with a previous Blue-Bag role. It breaks the dependency on geerlingguy.php
If you are using the geerlingguy.php role then you would be best to use the geerlingguy versions of the above roles.

Also note that this role provides a restart webserver handler.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    memcached_user: memcache

The user under which the Memcached daemon will run.

    memcached_port: 11211
    memcached_listen_ip: 127.0.0.1

The port and IP address (127.0.0.1 for localhost) on which Memcached will listen for requests.

    memcached_memory_limit: 64
    memcached_connections: 1024

Memcached limits. The maximum amount of RAM `memcached` will consume (64MB is the default), and the maximum number of simultaneous connections memcached will handle.

    memcached_log_file: /var/log/memcached.log

The location of the memcached log file.

    php_enablerepo: ""

(RedHat/CentOS only) If you have enabled any additional repositories (might I suggest geerlingguy.repo-epel or geerlingguy.repo-remi), those repositories can be listed under this variable (e.g. `remi,epel`). This can be handy, as an example, if you want to install the latest version of PHP 5.4, which is in the Remi repository.

## Dependencies

None.

## Example Playbook

    - hosts: cache
      roles:
        - { role: ansible-role-memcached }

## License

MIT / BSD

## Author Information

the source role for this was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
