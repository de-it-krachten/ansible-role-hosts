[![CI](https://github.com/de-it-krachten/ansible-role-hosts/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-hosts/actions?query=workflow%3ACI)


# ansible-role-hosts

Register all hosts within the inventory in /etc/hosts


Platforms
--------------

Supported platforms

- CentOS 7
- CentOS 8
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS



Role Variables
--------------
<pre><code>
# Adapter to retrieve IP from
hosts_adapter: default
</pre></code>


Example Playbook
----------------

<pre><code>
- name: Converge
  hosts: all
  vars:
  tasks:
    - name: Include role 'ansible-role-hosts'
      include_role:
        name: ansible-role-hosts

    - name: Get /etc/hosts
      command: cat /etc/hosts
      changed_when: false
      register: _hosts

    - name: Show /etc/hosts
      debug:
        var: _hosts.stdout_lines
</pre></code>
