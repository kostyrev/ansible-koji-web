koji-web
=========

This role installs and configures web interface for the koji.

This is one of the koji- roles which configures the whole koji stack.

Roles are:

 * [koji-ca](https://galaxy.ansible.com/kostyrevaa/koji-ca)
 * [koji-db](https://galaxy.ansible.com/kostyrevaa/koji-db)
 * [koji-client](https://galaxy.ansible.com/kostyrevaa/koji-client)
 * [koji-hub](https://galaxy.ansible.com/kostyrevaa/koji-hub)
 * [koji-web](https://galaxy.ansible.com/kostyrevaa/koji-web)
 * [koji-kojira](https://galaxy.ansible.com/kostyrevaa/koji-kojira)
 * [koji-builder](https://galaxy.ansible.com/kostyrevaa/koji-builder)

For example of all-in-one setup go to https://github.com/kostyrevaa/ansible-koji-infra


Role Variables
--------------

There are some variables in the default/main.yml which can (or needs to) be changed/overriden:

* `koji_web_issue_cert`: Does this role is able to issue cert for itself. When it's all-in-one setup it can be set to true or you can include fqdn of the host with this role to koji_ca_certs2issue var of koji-ca role. Default is false.

* `koji_web_KojiHubURL`: This is the url of koji hub. Default uses hostvars discover.

* `koji_web_KojiFilesURL`: This is the url of kojifiles. It should be set to url of host with koji-web role. Default uses hostvars discover.

* `koji_web_WebCert`: This is the absolute path of the certfile. Default is /etc/pki/koji/pems/{{ ansible_fqdn }}.pem.

* `koji_web_ClientCA`: This is the certificate of the CA that issued the client certificate. Default it /etc/pki/koji/koji_ca_cert.crt

* `koji_web_KojiHubCA`: This is the certificate of the CA that issued the HTTP server certificate. Default is /etc/pki/koji/koji_ca_cert.crt.


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: koji_web
      roles:
         - koji-web

License
-------

GPLv3

Author Information
------------------

Send your suggestions and pull requests to https://github.com/kostyrevaa/ansible-koji-web.  
When send PR make sure your changes are backward-compatible.  
Test your changes to role with https://github.com/kostyrevaa/ansible-koji-infra
