Docker Container apt-cacher-ng
==============================


A simple Ubuntu based container, running apt-cacher-ng to cache apt
packadges on a host.
This container will most defintelly need an attached volume on the
Docker host to persist the dev packadges like so:

`docker run -d -v /host/dir:/var/cache/apt-cacher-ng
shelleg/apt-cacher-ng:latest`


Once cacher-ng is setup you should configure your instances to use the
apt-cacher based on the following example:

``` echo 'Acquire::http { Proxy "http://dockerhost:3142"; };' >>
/etc/apt/apt.conf.d/01proxy
```
 
