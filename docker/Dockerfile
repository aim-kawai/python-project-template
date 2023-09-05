FROM nvidia/cuda:11.8.0-devel-ubuntu22.04

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    build-essential nginx libgl1-mesa-dev tzdata libglib2.0-0 sudo git && \
    ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \ 
    apt-get clean && \    
    rm -rf /var/lib/apt/lists/*
ENV TZ=Asia/Tokyo

WORKDIR /root

# install basic linux package
RUN apt update && apt install --no-install-recommends -y \
    nano sudo wget unzip curl dpkg

# install python
RUN apt update && apt install --no-install-recommends -y \
    python3.10 python3-pip python-is-python3 python3.10-dev

# poetry setup
RUN pip install poetry
COPY ../pyproject.toml  ./
COPY ../poetry.lock ./
RUN poetry config virtualenvs.create false && \
    poetry install && \
    rm -rf ~/.cache/pypoetry

WORKDIR /opt/
