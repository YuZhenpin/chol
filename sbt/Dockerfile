FROM asterkin/jdk:8.0

run wget -O /tmp/sbt.deb https://dl.bintray.com/sbt/debian/sbt-0.13.7.deb && \
    dpkg -i /tmp/sbt.deb && \
    rm /tmp/sbt.deb

add ./sbt-run /usr/bin/sbt-run


