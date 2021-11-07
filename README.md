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

First, add the following in your `requirements.yml` file:

```yaml
    - src: benyanke.disable_snapd
```

Then install the role:

```bash
ansible-galaxy install -r requirements.yml
```

Include the role for running

```yaml
    - hosts: servers
      roles:
         - { role: benyanke.disable_snapd }
```

Or, pass in parameters:

```yaml
    - hosts: servers
      roles:
         - { role: benyanke.disable_snapd, disable_snapd_uninstall_snapd: false}
```

License
-------

GPLv3
