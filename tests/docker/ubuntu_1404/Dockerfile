# Base image
FROM ubuntu:14.04
WORKDIR /pybombs

# Minimal package installation
RUN apt-get update -qq -y
RUN apt-get install -qq -y python-pip

# Install PyBOMBS using setuptools
COPY *.tar.gz /pybombs
RUN tar zxf *.tar.gz
RUN cd * && python setup.py install

# Install something
RUN mkdir /prefix
RUN cd /prefix
RUN pybombs -v recipes add gr-recipes git+https://github.com/gnuradio/gr-recipes.git
RUN pybombs -v prefix init -a default -R gnuradio-default default

