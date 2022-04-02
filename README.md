[![CI](https://github.com/de-it-krachten/ansible-role-hosts/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-hosts/actions?query=workflow%3ACI)


# ansible-role-hosts

Register all hosts within the inventory in /etc/hosts


Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
<pre><code>
# Adapter to retrieve IP from
hosts_adapter: default
</pre></code>


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'hosts'
  hosts: all
  vars:
  tasks:
    - name: Include role 'hosts'
      include_role:
        name: hosts

    - name: Get /etc/hosts
      command: cat /etc/hosts
      changed_when: false
      register: _hosts

    - name: Show /etc/hosts
      debug:
        var: _hosts.stdout_lines
</pre></code>
