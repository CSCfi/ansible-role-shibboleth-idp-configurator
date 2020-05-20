[![Build Status](https://travis-ci.org/CSCfi/ansible-role-shibboleth-idp-configurator.svg?branch=master)](https://travis-ci.org/CSCfi/ansible-role-shibboleth-idp-configurator)

Shibboleth IdP Configurator
=========

This role is configurator for Shibboleth IdP. This role can perform modifications for already existing installations on servers or optionally just create needed configuration which can then copied to server or be mounted on containers.

Requirements
------------

* Docker (Optional: If creating configurations tree)
  * cscfi/shibboleth-idp
* Ansible 2.9 ->
* Python 3 ->, python-lxml

Role Variables
--------------

This role can be called with multiple tags, where each tags means some dedicated configuration. Each configuration is own separate task file which makes it's easier follow what each configuration needs to do. Defaults and configurable variables for each tasks can be found from defaults/main.yml

* tag_haka: Add trust to Haka federation
  * shibbolethidp_hakacrt:
* tag_edugain: Add trust to Edugain
  * shibbolethidp_edugaincrt: 
* tag_hakatest Add trust to Haka-test federation
  * shibbolethidp_hakatestcrt:
* tag_oidc: Configure oidc support

If you want to overwrite default variables you can do it by overwriting those in the group_vars or in the playbook accordingly.

Dependencies
------------

* Docker (Optional)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT

Author Information
------------------
sami.silen@csc.fi
