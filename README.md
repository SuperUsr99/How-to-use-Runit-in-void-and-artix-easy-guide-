# How to use Runit in Void linux and Artix linux easyguide
My personal guide for runit

So, I used this guide my self on Void and Artix linux, it worket on both of it.

The change of runlevels & disabling services will not be included in the guide, only how to create a service.
Spoiler it's VERY EASY. Preveosly I collected this info from difirent sites, so give it a try.

My Guide how to create & supervise (a little) services in Void linux & Artix linux:

make folder <Service name> in  /etc/runit/sv/

** Artix linux
make file "run" in folder /etc/runit/sv/<Service name>

** Void linux
make file "run" in folder /etc/sv/<Service name>

make file executable  <run>

Code in file like this:

#!/bin/sh

exec /bin/<Service name>


Link "service" to /run/runit/service

** Artix linux
 ln -s /etc/runit/sv/service_name /run/runit/service

** Void linux
 ln -s /etc/sv /var/service
 
 
 Action	Command
Start	sv up service_name or sv start service_name
Stop	sv down service_name or sv stop service_name
Restart	sv restart service_name
Send SIGHUP	sv hup service_name
Check status	sv status service_name
