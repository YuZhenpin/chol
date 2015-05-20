FROM asterkin/sbt:latest
add ./eclipse.ini /usr/lib/eclipse/eclipse.ini

run sudo apt-get update -y && \
    sudo apt-get upgrade -y && \
    sudo apt-get install -y libgtk2.0-0 && \
    sudo apt-get install -y libxtst6 && \
    wget -O /tmp/eclipse-ide.tar.gz http://downloads.typesafe.com/scalaide-pack/4.0.0.vfinal-luna-211-20141216/scala-SDK-4.0.0-vfinal-2.11-linux.gtk.x86_64.tar.gz && \
    sudo tar -zxvf /tmp/eclipse-ide.tar.gz -C /usr/lib/ && \
    rm /tmp/eclipse-ide.tar.gz && \
    sudo ln -s /usr/lib/eclipse/eclipse /usr/bin/eclipse && \
    sudo ln -s /usr/lib/eclipse/eclipse.ini /etc/eclipse.ini && \
    sudo chmod -R o+rwx /usr/lib/eclipse/configuration && \
    sudo eclipse -nosplash \
      -application org.eclipse.equinox.p2.director \
      -repository http://download.eclipse.org/releases/luna \
      -destination /usr/lib/eclipse \
      -installIU org.eclipse.cdt.feature.group


    



