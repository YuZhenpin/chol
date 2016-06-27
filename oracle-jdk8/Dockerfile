FROM asterkin/cdev:latest

run apt-get -y install software-properties-common && \
    add-apt-repository -y ppa:webupd8team/java && \
    apt-get -q -y update && \
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-get -y install oracle-java8-installer && \
    ln -f -s /usr/lib/jvm/java-8-oracle /usr/lib/jvm/default-java && \
    sed "s/exit 0/mkdir \/dev\/shm\/java && cp -r \/usr\/lib\/jvm\/java-8-oracle\/* \/dev\/shm\/java && exit 0/" -i /etc/rc.local





