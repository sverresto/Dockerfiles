#
# Creates a docker image, so you can test your dns changes
#
# docker build -t <username>/dnstest .
# docker run -ti --dns=127.0.0.1 -v /<path,to>/git/dns:/etc/bind <username>/dnstest:latest
# make dns changes, and do a 'kill -HUP 1' to test them

FROM ubuntu:14.04
MAINTAINER Sverre Stoltenberg <sverrest@gmail.com>

RUN apt-get update && apt-get install -y bind9 bind9-host bind9utils git dlint mg dnsutils && mkdir /var/log/dns/

VOLUME /etc/bind
EXPOSE 53
ENTRYPOINT ["/usr/sbin/named", "-f"]
