FROM 10.64.27.125:5000/rhel:7-0.0.1.beta.el7
# FROM 10.64.27.125:5000/vpavlin/rhel7
MAINTAINER scollier <scollier@redhat.com>

# Update the system
RUN yum -y update; yum clean all

# Add repo files
ADD ./mongo.repo /etc/yum.repos.d/
# ADD ./mongodb.conf /etc/
ADD ./mongod.conf /etc/

# Install MongoDB and extras
RUN yum -y install mongo-10gen-server mongo-10gen; yum clean all
RUN yum -y install procps-ng iptables; yum clean all

# Expose ports
EXPOSE 27017 28017

# USER mongod

CMD ["/usr/bin/mongod", "-f", "/etc/mongod.conf"]
