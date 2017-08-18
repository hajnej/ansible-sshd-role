ansible-sshd-role
=========

Purpose of this role is to configure OpenSSH daemon

Requirements
------------

There is not any prerequisites for this role. 

Role Variables
--------------

Below are parameters to configure OpenSSH daemon. See `man 5 sshd_config` for detailed information about those parameters.

    sshd_loglevel: "INFO"

Sets verbosity of logging. Defaults to `"INFO"` priority.

    sshd_permitrootlogin: "without-password"

Permits root login. Default is to disable password authentication for root account

    sshd_maxauthtries: 2

Max auth tries per connection

    sshd_maxsessions: 10

Max count of sessions per connection

    sshd_clientaliveinterval: 300

Number of seconds to allow open session without any input from client

    sshd_clientalivecountmax: 0

Number of interva to check for open session before kick out the client


Dependencies
------------

This role depends on below ansible roles:

    ansible-ssh-check-role
    ansible-selinux-role

Example Playbook
----------------

Due dependency on `ansible-ssh-check-role` playbook must contain `gather_facts: False`.

    - hosts: "all"
      gather_facts: False
      roles:
         - "ansible-sshd-role"

License
-------

BSD

Author Information
------------------

Jakub Slatinsky, slatinskyj@gmail.com
