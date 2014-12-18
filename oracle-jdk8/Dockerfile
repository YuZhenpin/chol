FROM ubuntu:latest

run sudo apt-get -y install software-properties-common && \
    sudo add-apt-repository -y ppa:webupd8team/java && \
    sudo apt-get -q -y update && \
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections && \
    sudo apt-get -y install oracle-java8-installer && \
    sudo ln -f -s /usr/lib/jvm/java-8-oracle /usr/lib/jvm/default-java && \
    sudo sed "s/exit 0/mkdir \/dev\/shm\/java && cp -r \/usr\/lib\/jvm\/java-8-oracle\/* \/dev\/shm\/java && exit 0/" -i /etc/rc.local


