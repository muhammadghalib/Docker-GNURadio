FROM ubuntu:18.04

#ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update

# else it will output an error about Gtk namespace not found
RUN apt-get install -y gir1.2-gtk-3.0

# to have add-apt-repository available
RUN apt-get install -y software-properties-common

RUN add-apt-repository -y ppa:gnuradio/gnuradio-releases-3.7

# create user gnuradio-transmitter with sudo (and password gnuradio-transmitter)
RUN apt-get install -y sudo
RUN useradd --create-home --shell /bin/bash -G sudo gnuradio-transmitter
RUN echo 'gnuradio-transmitter:gnuradio-transmitter' | chpasswd

# I create a dir at home which I'll use to persist after the container is closed (need to change its ownership)
RUN mkdir /home/gnuradio-transmitter/persistent && chown gnuradio-transmitter /home/gnuradio-transmitter/persistent

RUN apt-get update

RUN apt-get install -y gnuradio

# installing other packages needed for downloading and installing OOT modules
RUN apt-get install -y gnuradio-dev cmake git libboost-all-dev libcppunit-dev liblog4cpp5-dev swig liborc-dev

# install usbutils
RUN apt-get install -y usbutils

# of course, nothing useful can be done without vim
RUN apt-get install -y vim

# Install net-tools for ifconfig command and iputils-ping for ping command
RUN apt-get install -y net-tools iputils-ping

# Install gedit
RUN apt-get install -y gedit

# Install UHD dependencies 
RUN uhd_images_downloader

USER gnuradio-transmitter

WORKDIR /home/gnuradio-transmitter

ENV PYTHONPATH "${PYTHONPATH}:/usr/local/lib/python3/dist-packages"

CMD bash
