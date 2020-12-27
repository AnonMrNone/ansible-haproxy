# ansible-haproxy
🌀 Ansible playbook and role for HAProxy configuration (Bare metal &amp; AWS cloud)

🎫 https://shubhambhalala.medium.com/haproxy-loadbalancer-configuration-using-ansible-playbooks-and-role-with-testing-on-aws-3d818468626e

# How to use?
1. For using playbook:

  a) Edit the ansiblehosts.txt for your managed nodes.
  
  b) weblb.yml is the main file.
  
  c) lbvar.yml is load balancer variable file for changing the port number.
  
  d) webservervar.yml is webserver variable file for changing listening port and document root.
  
  e) haproxy.cfg.j2 is the template file for configuring HAProxy.
  
  f) web.config.j2 is the template file for configuring the webserver. For this you have to edit the weblb.yml file with the following snippet of code in webserver tasks.
  
  - copy:
  
      dest: "/etc/httpd/conf.d/newweb.conf"
      
      src: web.config.j2
      
      
2. For using role:

  a) setup.yml is the main file.
  
  b) Edit the awshosts.txt or ansiblehosts.txt for your managed nodes.
  
  c) Keep your aws key in the same folder and edit the ansible.cfg file to tell them where is the key.
  
