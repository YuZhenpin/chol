FROM chol/gradle:latest

run wget -O /tmp/sbt.deb https://dl.bintray.com/sbt/debian/sbt-0.13.7.deb && \
    sudo dpkg -i /tmp/sbt.deb && \
    rm /tmp/sbt.deb && \
    sbt about


