# vagrant-postgresql-cluster

This sets up a postgresql cluster consisting of one primary (master) server, one streaming replica server, a pgpool server that simply load balances (no health checks, yet), and an app server (I'm using [Ghost](https://ghost.org)). Since it is driven by ansible, you can also use it to deploy to your own stack (though modify as needed! If you're going to use as-is, you would modify the vagrant-inventory file). To run on your own stack, you would run:

```
ansible-playbook -i ./vagrant-inventory provision.yml
```

Next goal will be to proxy from ngnix to node and to do more interesting things with pgpool to get a better understanding of promoting a replica to primary (and vice versa).
