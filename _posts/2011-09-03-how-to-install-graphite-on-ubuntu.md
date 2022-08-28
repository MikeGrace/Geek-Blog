---
title: How-to Install Graphite on Ubuntu
date: 2011-09-03T18:01:33+00:00
author: MikeGrace
layout: post
permalink: /2011/09/how-to-install-graphite-on-ubuntu/
categories:
  - How to
  - Linux
  - Web Design -Dev
---
![](http://mikegrace.s3.amazonaws.com/geek-blog/graphite.png)

**UPDATED TO WORK WITH GRAPHITE 0.9.9!!! (10/13/2011)**

The new release of Graphite 0.9.9 includes an experimental Flot JavaScript graph. Awesome!

![](http://mikegrace.s3.amazonaws.com/geek-blog/flot-in-graphite.png)

Steps to installing Graphite on Ubuntu -> [gist.github.com](https://gist.github.com/1191574)
  
Ubuntu Graphite install screencast -> [youtube.com](http://www.youtube.com/watch?v=o5yLgzsQqU0)

_ If you are looking for a how-to on [graphite one](http://www.graphiteone-cad.com/page_home.php) (CAD) or [statsd](https://github.com/etsy/statsd) this is not the place._

A few months ago I blogged abou [how much I love stats](http://geek.michaelgrace.org/2011/02/closet-stats-junkie/). One of the things that I shared in that post was a blog post done by the etsy developer team about [statsd and graphite to track everything](http://codeascraft.etsy.com/2011/02/15/measure-anything-measure-everything/).

This week I was able to get graphite setup on a dedicated Ubuntu 10.04 on my Mac using VMware Fusion. I thought I would share the steps I took so others might be able to save some time in their setup. In setting up apache I just copied over the default virtual host settings since graphite will be the only thing running on the server. If you are planning on having multiple virtual hosts on the machine then you will want to configure the virtual hosts differently.

<pre lang="bash">####################################
# BASIC REQUIREMENTS
# http://graphite.wikidot.com/installation
# http://geek.michaelgrace.org/2011/09/how-to-install-graphite-on-ubuntu/
# Last tested & updated 10/13/2011
####################################

sudo apt-get update
sudo apt-get upgrade

wget http://launchpad.net/graphite/0.9/0.9.9/+download/graphite-web-0.9.9.tar.gz
wget http://launchpad.net/graphite/0.9/0.9.9/+download/carbon-0.9.9.tar.gz
wget http://launchpad.net/graphite/0.9/0.9.9/+download/whisper-0.9.9.tar.gz
tar -zxvf graphite-web-0.9.9.tar.gz
tar -zxvf carbon-0.9.9.tar.gz
tar -zxvf whisper-0.9.9.tar.gz
mv graphite-web-0.9.9 graphite
mv carbon-0.9.9 carbon
mv whisper-0.9.9 whisper
rm carbon-0.9.9.tar.gz
rm graphite-web-0.9.9.tar.gz
rm whisper-0.9.9.tar.gz
sudo apt-get install --assume-yes apache2 apache2-mpm-worker apache2-utils apache2.2-bin apache2.2-common libapr1 libaprutil1 libaprutil1-dbd-sqlite3 python3.1 libpython3.1 python3.1-minimal libapache2-mod-wsgi libaprutil1-ldap memcached python-cairo-dev python-django python-ldap python-memcache python-pysqlite2 sqlite3 erlang-os-mon erlang-snmp rabbitmq-server bzr expect ssh libapache2-mod-python python-setuptools
sudo easy_install django-tagging

####################################
# INSTALL WHISPER
####################################

cd ~/whisper
sudo python setup.py install

####################################
# INSTALL CARBON
####################################

cd ~/carbon
sudo python setup.py install
# CONFIGURE CARBON
####################
cd /opt/graphite/conf
sudo cp carbon.conf.example carbon.conf
sudo cp storage-schemas.conf.example storage-schemas.conf
sudo vim storage-schemas.conf
### edited storage-schemas.conf to be the following
[stats]
priority = 110
pattern = .*
retentions = 10:2160,60:10080,600:262974
###

####################################
# CONFIGURE GRAPHITE (webapp)
####################################

cd ~/graphite
sudo python check-dependencies.py
sudo python setup.py install

# CONFIGURE APACHE
###################
cd ~/graphite/examples
sudo cp example-graphite-vhost.conf /etc/apache2/sites-available/default
sudo cp /opt/graphite/conf/graphite.wsgi.example /opt/graphite/conf/graphite.wsgi
sudo vim /etc/apache2/sites-available/default
# moved 'WSGIImportScript /opt/gr..' to right before virtual host since it gave me an error saying
# WSGIImportScript cannot occur within &lt;VirtualHost> section
# if this path does not exist make it!!!!!!
# /etc/httpd/wsgi
sudo mkdir /etc/httpd
sudo mkdir /etc/httpd/wsgi
sudo /etc/init.d/apache2 reload

####################################
# INITIAL DATABASE CREATION
####################################
cd /opt/graphite/webapp/graphite/
sudo python manage.py syncdb
# follow prompts to setup django admin user
sudo chown -R www-data:www-data /opt/graphite/storage/
sudo /etc/init.d/apache2 restart
cd /opt/graphite/webapp/graphite
sudo cp local_settings.py.example local_settings.py

####################################
# START CARBON
####################################
cd /opt/graphite/
sudo ./bin/carbon-cache.py start

####################################
# SEND DATA TO GRAPHITE
####################################
cd ~/graphite/examples
sudo chmod +x example-client.py
# [optional] edit example-client.py to report data faster
# sudo vim example-client.py
sudo ./example-client.py</pre>



Original installation instructions -> <http://graphite.wikidot.com/installation>

Looking to run an Ubuntu instance on EC2? Check out <http://uec-images.ubuntu.com/releases/10.04/release/>

Now you are ready to [install StatsD](http://geek.michaelgrace.org/2011/09/installing-statsd-on-ubuntu-server-10-04/)!