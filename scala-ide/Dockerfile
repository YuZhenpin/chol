FROM chol/sbt:latest
run wget -O /tmp/eclipse-ide.tar.gz http://downloads.typesafe.com/scalaide-pack/4.0.0.vfinal-luna-211-20141216/scala-SDK-4.0.0-vfinal-2.11-linux.gtk.x86_64.tar.gz && \
    sudo tar -zxvf /tmp/eclipse-ide.tar.gz -C /usr/lib/ && \
    rm /tmp/eclipse-ide.tar.gz && \
    sudo ln -s /usr/lib/eclipse/eclipse /usr/bin/eclipse && \
    sudo ln -s /usr/lib/eclipse/eclipse.ini /etc/eclipse.ini && \
    sudo chmod -R o+rwx /usr/lib/eclipse/configuration && \
    sudo apt-get install -y libgtk2.0-0 && \
    sudo apt-get install -y libxtst6

add ./eclipse.ini /usr/lib/eclipse/eclipse.ini


    



