[![CI](https://github.com/de-it-krachten/ansible-role-hosts/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-hosts/actions?query=workflow%3ACI)


# ansible-role-hosts

Configures /etc/hosts with custom records and/or configures the system to use custom DNS servers



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS
- Fedora 40
- Fedora 41
- Alpine 3

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Adapter to retrieve IP from
hosts_adapter: default

# Type of name resolving to configure
# hosts = /etc/hosts, dns = /etc/resolv.conf or both
hosts_mode: hosts

# list of name servers
hosts_dns_servers: []
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'hosts'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'hosts'
      ansible.builtin.include_role:
        name: hosts
</pre></code>
