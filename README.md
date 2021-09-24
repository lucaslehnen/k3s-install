Install k3s cluster on Ubuntu
=========

Prepare a Ubuntu node to receive k3s cluster.

To configure nodes and init cluster, check the following roles. This role is a requirement for them:
- https://github.com/lucaslehnen/k3s-config-master
- https://github.com/lucaslehnen/k3s-config-node

This role must be run on all nodes.

Example
----------------

In your `main.yml`:

    - hosts: servers
      roles:
         - k3s-install

In your `requirements.yml`:

    - name: k3s-install
      src: https://github.com/lucaslehnen/k3s-install
      version: 1.0.0

Define target hosts in your inventory file `hosts`:

    [servers]
    192.168.99.11
    192.168.99.12
    192.168.99.13

Install requirements:

```
ansible-galaxy install -r requirements.yml
```

Call the playbook:

    ansible-playbook -i hosts main.yml

License
-------

MIT

Author
------------------

https://github.com/lucaslehnen