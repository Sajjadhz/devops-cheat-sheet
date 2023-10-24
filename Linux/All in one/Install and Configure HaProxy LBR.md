## Install and Configure HaProxy LBR

### Question:   
Install and configure HAproxy on LBR server using yum only and make sure all app servers are added to HAproxy load balancer. HAproxy must serve on default http port

### Solution:  

1. At first you need to log in to all the app servers and find the Listen port & need to start the httpd services.

```
sshpass -p Ir0nM@n ssh -o StrictHostKeyChecking=no tony@stapp01

sudo su -
```

2. Enable httpd & start the service

`systemctl enable httpd`

`systemctl start httpd && systemctl status httpd`

3. Validate Apache HTTPd running  as per the task request

### Now Login to the the LBR Server and install the haproxy 

```
sshpass -p Mischi3f ssh -o StrictHostKeyChecking=no 	loki@stlb01

sudo su -

yum -y install haproxy
```

4. Edit the vi `/etc/haproxy/haproxy.cfg`   file and correct the changes as per below

5. Validate the haproxy configuration file by running the below command
`haproxy -f /etc/haproxy/haproxy.cfg`

6. Enable and start the haproxy service

`systemctl enable haproxy && systemctl start haproxy`

7. Validate the task  from jump server 
