# vagrant-postgresql-cluster

This sets up a postgresql cluster consisting of one primary (master) server, one streaming replica server, a pgpool server that simply load balances (no health checks, yet), and an app server (that needs an app). Since it is driven by ansible, you can also use it to deploy to your own stack (though modify as needed!).

Next goal will be to tie it to an actual app for demo purposes and to do more interesting things with pgpool to get a better understanding of promoting a replica to primary (and vice versa).
