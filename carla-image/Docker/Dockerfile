FROM ubuntu:20.04

USER root

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update ; \
    apt-get install -y build-essential \
    git

RUN git clone https://github.com/AlaaAlassi/carla.git

RUN apt-get install -y clang-8 \
    cmake \
    ninja-build \
    wget software-properties-common \
    python3-dev \
    python3-pip && \
    pip3 install -Iv setuptools==47.3.1 &&\
    update-alternatives --install /usr/bin/clang++ clang++ /usr/lib/llvm-8/bin/clang++ 180 && \
    update-alternatives --install /usr/bin/clang clang /usr/lib/llvm-8/bin/clang 180

COPY generate-traffic.py /

RUN   add-apt-repository ppa:ubuntu-toolchain-r/test 
RUN   apt-get install -y autoconf 
RUN   apt-get install -y rsync
RUN   pip3 install distro

WORKDIR "/carla"

#CMD ["cat", "./Util/BuildTools/BuildOSM2ODR.sh"]

CMD ["make", "PythonAPI"]
#CMD ["python3", "generate-traffic.py"]