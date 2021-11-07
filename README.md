Ansible Role: disable-snapd
=========

It does what it says on the tin. A very simple role to stop and remove snapd.

Requirements
------------

Ubuntu.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
disable_snapd_stop_service: true
```

When set to true, the service is stopped.


```yaml
disable_snapd_uninstall_snapd: true
```

When set to true, the package is uninstalled.


Less commonly needed variables:

```yaml
disable_snapd_service_name: "snapd"
disable_snapd_package_name: "snapd"
```

Dependencies
------------

None.

Example Playbook
----------------

Include the following in your `requirements.yml`:

```yaml
- src: git+https://gitlab.com/systemdad/ansible-disable-snapd.git
  version: master
  name: disable-snapd
```

Include the role for running

```yaml
    - hosts: servers
      roles:
         - { role: disable-snapd }
```

Or, pass in parameters:

```yaml
    - hosts: servers
      roles:
         - { role: disable-snapd, disable_snapd_uninstall_snapd: false}
```

License
-------

GPLv3
