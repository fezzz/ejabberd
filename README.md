# ejabberd 18.06
This image built on centos contains the latest ejabberd version compiled from the sources.
In order to use it properly, you have to mount some directories from your host. (configuration files, databases, logs)
**Make sure that you set on the host the user and group for the directories to mount correctly. User 999 Group 998**

~~~
ejabberd:
  image: fezzz/ejabberd
  ports:
       - 5222:5222
       - 5269:5269
  volumes:
       - /HOST/serverconfig/ejabberd:/usr/local/etc/ejabberd
       - /HOST/DB/ejabberd:/usr/local/var/lib/ejabberd
       - /HOST/logs/ejabberd:/usr/local/var/log/ejabberd
  restart: always
~~~
