chol
====

The basic idea behind this project is to support immutable development environments: everything is in scripts, everything is in version control, virtual machines can be destroyed at any moment and re-created from the scratch, hence the name "Chol" - Phoenix is Hebrew.

There are some trade-offs to be addressed, namely basic infrastructure and granularity of the scripts. Many options are available but for the time being I've opted for the simples one I could think about: 

  1. keep scripts small and modular - single responsibility principle
  2. store snapshots for particular configurations such as lxde graphics desktop + docker
  3. use snapshot for creating desktop instances per developer and configure the rest of tools as Docker containers.

Obviously specific configurations could also be wrapped up in something like Ansible or Puppet cook books, but I could never find enough energy for this, and the fashion is changing too frequently.

To start working with the Chol scripts on a cloud I recommend the following simple procedure:

  1. Create a cloud instance of a basic Ubuntu server (currently 14.04)
  2. SSH login using your favorite SSH client (e.g. MobaExterm: http:http://mobaxterm.mobatek.net/)
  2. sudo apt-get update
  3. sudo apt-get install git
  4. git clone https://github.com/asterkin/chol.git
  5. cd chol/system
  6. ./docker-install
  7. ./minimal-lxde-desktop
  8. ./x2go-server (you will need an x2go client from http://http://wiki.x2go.org/doku.php)
  9. cd ..
  10. sudo cp chol /usr/bin
  11. cd ..
  12. rm -rf chol
  13. make a snapshot, for example ubuntu-14.4-docker-lxde

To create and configure a new desktop for some user:

  1. Create new instance from the snapshot
  2. SSH login as a system user (e.g. ubuntu)
  3. chol set-user <user-name> "Full Name" <-mail-server>. Example: chol set-user asterkin "asher Sterkin" cisco
  4. chol <your favorite development tool>. Example: chol scala-ide (currently the only one supported)
  4. Re-login via SSH (e.g. using X2Go Client: http://wiki.x2go.org/doku.php/doc:usage:x2goclient)
  

To install Scala IDE:
  1. chol scala-ide (sbt will be installed automatically as a part of the process)
  2. Create your project
  3. Create build.sbt file
  4. sbt eclipse
  5. Launch Eclipse (should be avaliable from lauchpad)
  6. Import created project(s)
  
This procedure will pull from Docker Hub 3  Docker images with Java8 jdk, Sbt, and Scala IDE (Eclipse). It will also make sbt launchible from command line and will install scala-ide.desktop file in /usr/share/application to make it available from Ubuntu Application Launchbar.


