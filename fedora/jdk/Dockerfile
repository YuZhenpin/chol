FROM asterkin/gcc:latest

run yum install -y wget && \
    cd /tmp && \
    wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie"  http://download.oracle.com/otn-pub/java/jdk/8u92-b14/jdk-8u92-linux-x64.rpm && \
    rpm -ivh jdk-8u92-linux-x64.rpm && \
    rm jdk-8u92-linux-x64.rpm







