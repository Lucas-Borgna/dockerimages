FROM cern/cc7-base

# $ Reworking this example using https://hub.docker.com/r/continuumio/miniconda/dockerfile

ENV PATH /opt/conda/bin:$PATH

# $ CentOS7 updates

RUN yum -y update

# $ Dependencies for xrootd

RUN yum -y install wget curl bzip2 xrootd-client

# $ Acquiring & Installing Miniconda

#py37_4.8.2-Linux-x86_64 need this specific version!
RUN wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.2-Linux-x86_64.sh -O ~/miniconda.sh && \
    /bin/bash ~/miniconda.sh -b -p /opt/conda && \
    rm ~/miniconda.sh && \
    /opt/conda/bin/conda clean -tipsy && \
    ln -s /opt/conda/etc/profile.d/conda.sh /etc/profile.d/conda.sh && \
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
    echo "conda activate base" >> ~/.bashrc


# $ Ignoring krallin tini 

RUN conda install -c conda-forge xrootd

RUN pip install pandas==0.24.2 numpy==1.19.2 tqdm==4.45.0 uproot==3.11.3 matplotlib==3.3.0

# $ Clean up conda

RUN conda clean --all --yes
