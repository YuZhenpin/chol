FROM asterkin/jdk:latest

run cd /usr/local && \
    wget https://storage.googleapis.com/golang/go1.6.2.linux-amd64.tar.gz && \
    tar xzvf go1.6.2.linux-amd64.tar.gz && \
    rm go1.6.2.linux-amd64.tar.gz

env PATH $PATH:/usr/local/go/bin
 
add ./go-run /usr/bin/go-run








