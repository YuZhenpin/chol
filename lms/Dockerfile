FROM chol/sbt:0.13.7

run sudo apt-get install -y git && \
    sudo apt-get install -y gcc && \
    echo 'SBT_OPTS="-Xms3G -Xmx3G -Xss1M -XX:MaxPermSize=192M -XX:+UseParallelGC"' > ~/.sbtconfig && \
    mkdir lms && \
    cd lms && \
    git clone https://github.com/TiarkRompf/virtualization-lms-core.git && \
    cd virtualization-lms-core && \
    sbt publish-local && \
    sbt test && \
    cd .. && \
    git clone https://github.com/scala-lms/tutorials.git && \
    cd tutorials && \
    sbt test



