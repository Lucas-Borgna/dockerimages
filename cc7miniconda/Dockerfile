FROM cern/cc7-base

RUN yum -y update \
    && yum -y install curl bzip2 xrootd-client gcc gcc-c++ libstdc++-devel swig python-devel xorg-x11-server-Xorg xorg-x11-xauth xorg-x11-apps -y \
    && curl -sSL https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -o /tmp/miniconda.sh \
    && bash /tmp/miniconda.sh -bfp /usr/local/ \
    && rm -rf /tmp/miniconda.sh \
    && conda install -y python=3 \
    && conda update conda \
    && conda clean --all --yes \
    && rpm -e --nodeps curl bzip2 \
    && yum clean all 

RUN pip install pandas uproot cocotb

RUN pip install --upgrade tables


