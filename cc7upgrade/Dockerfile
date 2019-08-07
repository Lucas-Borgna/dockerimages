FROM cern/cc7-base

RUN yum -y update \
    && yum -y install gcc \
    && yum -y install curl bzip2 xrootd-client \
    && rpm -e --nodeps curl bzip2 \
    && yum clean all 


