FROM cern/cc7-base

FROM cern/cc7-base

# $ Reworking this example using https://hub.docker.com/r/continuumio/miniconda/dockerfile

ENV PATH /opt/conda/bin:$PATH

# $ CentOS7 updates

RUN yum -y update

# $ Dependencies for xrootd

RUN yum -y install wget curl bzip2 xrootd-client

# $ Dependencies for QuestaSim and cocotb

RUN yum -y install gcc gcc-c++ libstdc++-devel swig python-devel xorg-x11-server-Xorg xorg-x11-xauth xorg-x11-apps make which 

# $ Acquiring & Installing Miniconda

RUN wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-4.5.11-Linux-x86_64.sh -O ~/miniconda.sh && \
    /bin/bash ~/miniconda.sh -b -p /opt/conda && \
    rm ~/miniconda.sh && \
    /opt/conda/bin/conda clean -tipsy && \
    ln -s /opt/conda/etc/profile.d/conda.sh /etc/profile.d/conda.sh && \
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
    echo "conda activate base" >> ~/.bashrc


# $ Ignoring krallin tini 

RUN conda install pandas pytables

RUN conda install -c conda-forge uproot

RUN pip install cocotb

# $ Clean up conda

RUN conda clean --all --yes
