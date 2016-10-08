# NGINX Sandbox


## Install Vagrant Plugins

### [Cashier](https://github.com/fgrehm/vagrant-cachier): 

```bash
vagrant plugin install vagrant-cachier
``` 

## Local/Host configurations

In /etc/hosts add following entry:

```bash
192.168.33.33 sandbox.local jenkins.sandbox.local
``` 

## Visit vhosts

[Default Page](http://sandbox.local/)
[Jenkins](http://jenkins.sandbox.local/)