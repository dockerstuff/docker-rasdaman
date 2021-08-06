FROM centos:7

MAINTAINER "Carlos H Brandt <github:chbrandt>"

RUN curl "https://download.rasdaman.org/packages/rpm/stable/CentOS/7/x86_64/rasdaman.repo" \
          -o /etc/yum.repos.d/rasdaman.repo \
    && yum install -y epel-release \
    && yum update -y \
    && yum install -y rasdaman vim git\
    && yum clean all \
    && /opt/rasdaman/bin/create_db.sh \
    echo 'export PATH="/opt/rasdaman/bin:${PATH}"' >> /etc/profile.d/rasdaman.sh

ENV PATH="/opt/rasdaman/bin:$PATH" 

ENTRYPOINT ['start_rasdaman.sh']