# Ghost Application Cluster

This sets up a postgresql cluster consisting of one primary (master) server, one streaming replica server, a pgpool server that simply load balances (no health checks, yet), and an app server (I'm using [Ghost](https://ghost.org)). Since it is driven by ansible, you can also use it to deploy to your own stack (though modify as needed! If you're going to use as-is, you would modify the vagrant-inventory file). To run on your own stack, you would run:

```
ansible-playbook -i ./cluster-inventory provision.yml --ask-pass --ask-sudo-pass
```

With a vagrant setup, you would access this at: http://10.0.0.2

You can specify the password / sudo password in the inventory file...but that would be pretty insecure, wouldn't it? If you use it for local development (ie with vagrant), it will automatically run the playbook when you run vagrant up and vagrant provision.

Next goal will be to proxy from ngnix to node and to do more interesting things with pgpool to get a better understanding of promoting a replica to primary (and vice versa).
