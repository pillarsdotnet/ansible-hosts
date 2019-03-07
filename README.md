hosts
=====

Ensures that all inventoried instances are represented in each hosts file, thereby avoiding DNS lookups within the local environment.

Requirements
------------

- [Fact caching](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#fact-caching) must be enabled.
- The [`hostvars`](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#magic-variables-and-how-to-access-information-about-other-hosts) variable must include ip address and hostname information.

Role Variables
--------------

	- [`hosts_addresses`](defaults/main.yml#L3)
	  A list of hostvars attributes which contain ip addresses.
    - [`hosts_file`](defaults/main.yml#L7)
	  The absolute path to the hosts file being managed.
    - [`hosts_hostvars`](defaults/main.yml#L9)
	  Whether to parse `hostvars` variable.  Defaults to `True`.
	- [`hosts_list`](defaults/main.yml#L11)
	  Dictionary of all hosts. Defaults to localhost.
	- [`hosts_names`](defaults/main.yml#L27)
      A list of hostvars attributes which contain host names.

Dependencies
------------

None.

Example Playbook
----------------

  ```yaml
  - hosts: 'all'
    roles:
    - 'hosts'
  ```

Author Information
------------------

[Robert August Vincent II](https://github.com/pillarsdotnet)  
*(pronounced "Bob" or "Bob-Vee")*  
