FROM ubuntu:latest
RUN sudo adduser --quiet --disabled-password -shell /bin/bash --home /home/newuser --gecos "Guest" guest && \
    echo "root:abc" | sudo chpasswd && \
    sudo rm /etc/nologin
ONBUILD RUN echo "This image cannot be inherited" && exit 255
USER guest


    



