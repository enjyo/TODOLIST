# OSはCentOS
FROM centos:latest

# 各パッケージをインストール
# pipやvirtualenvインストールも想定しています。
RUN yum -y update
RUN yum -y groupinstall "Development Tools"
RUN yum -y install \
           kernel-devel \
           kernel-headers \
           gcc-c++ \
           patch \
           libyaml-devel \
           libffi-devel \
           autoconf \
           automake \
           make \
           libtool \
           bison \
           tk-devel \
           zip \
           wget \
           tar \
           gcc \
           zlib \
           zlib-devel \
           bzip2 \
           bzip2-devel \
           readline \
           readline-devel \
           sqlite \
           sqlite-devel \
           openssl \
           openssl-devel \
           git \
           gdbm-devel \
           python-devel

# Python3.7.2をインストール
# Python3.7.2をダウンロード
WORKDIR /root
RUN wget https://www.python.org/ftp/python/3.7.2/Python-3.7.2.tgz
RUN tar xzvf Python-3.7.2.tgz

# makeでインストール
WORKDIR ./Python-3.7.2
RUN ./configure --with-threads
RUN make install

# pipインストール(最新版)
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py

# readlineインストール
RUN pip3 install readline

# virtualenvインストール
RUN pip3 install virtualenv

# Djangoインストール
RUN pip3 install django

# おまけ
# Django以外のフレームワークインストール
# bottleインストール
# RUN pip install bottle

# Flaskインストール
# RUN pip install Flask

WORKDIR /root
CMD ["/bin/bash"]
