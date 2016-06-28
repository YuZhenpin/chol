FROM asterkin/sbt:latest

run apt-get update -y && \
    apt-get install -y libgtk2.0-0 && \
    apt-get install -y libxtst6 && \
    apt-get install -y libcanberra-gtk-module && \
    apt-get install -y libwebkitgtk-1.0-0 && \
    wget -O /tmp/eclipse-ide.tar.gz http://downloads.typesafe.com/scalaide-pack/4.4.1-vfinal-luna-211-20160504/scala-SDK-4.4.1-vfinal-2.11-linux.gtk.x86_64.tar.gz && \
    tar -zxvf /tmp/eclipse-ide.tar.gz -C /usr/lib/ && \
    rm /tmp/eclipse-ide.tar.gz && \
    ln -s /usr/lib/eclipse/eclipse /usr/bin/eclipse && \
    ln -s /usr/lib/eclipse/eclipse.ini /etc/eclipse.ini && \
    chmod -R o+rwx /usr/lib/eclipse/configuration 
#&& \
#    eclipse -nosplash \
#      -application org.eclipse.equinox.p2.director \
#      -repository http://download.eclipse.org/releases/luna \
#      -destination /usr/lib/eclipse \
#      -installIU org.eclipse.cdt.feature.group


    



