# ec2-with-nginx

## steps
* Create an EC2 instance on AWS (free tier)
  * Config should be all default
  * Security Group: allow SSH and HTTP inbounds
  * Download key pair file (.pem) provided for access once config is final
  * `chmod 400 {filename}.pem` grants read permission only, otherwise the connection will fail
* Connect using `ssh -i {filename}.pem ec2-user@{ip-public-dns}`
* `sudo su` for superuser access (root)
* Install nginx on the instance
  * This process will vary depending on the OS
  * https://www.nginx.com/resources/wiki/start/topics/tutorials/install/
  * Check installation `nginx -v`
  * Server should be running once installed
  * `curl localhost` to view nginx template being served
* Replace the template file OR
  * update the directory to point at your app
  * https://www.nginx.com/blog/setting-up-nginx/#web-server
* `sudo nginx -s reload` to reload nginx