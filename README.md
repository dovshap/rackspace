# HA Wordpress with Vagrant LXC and Ansible
This combination of Vagrant with the Vagrant-LXC provider and the Ansible provisioner will create:
* 2 nginx servers
* 1 mysql server
* 1 haproxy load balancer
 
Due to an issue with vagrant and ansible in a multi machine setup you must use the following workaround to make sure that ansible does not run until all the boxes are up
- `vagrant up --no-provision && vagrant provision`

Once this is finished you can reach the LB at 192.168.122.24:8888 or each web server at 192.168.122.21 and 192.168.122.22
