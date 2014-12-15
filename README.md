chol
====

The basic idea behind this project is to support an idea of immutable development environments: everythin is in scripts, everything is in version control, virtual machines could be destroyed at any moment and re-created from the scratch, hence the name "Chol" - Phoenix is Hebrew.

There are some trade-offs to be addressed, namely basic infrastrcuture and granularity of the scripts. Many options are available I opted for the simples one I could think about: 

  a) keep scripts small and modular - single responsibility principle
  b) store snapshots for particular configurations such as lxde graphics desktop, scala development environment, etc.

Obvisouly specific configurations could also be wrapped up in something like Ansible or Puppet cook books, but I could never find enough energy for this, and the fashion is changing too frequently.

To start working with the Chol scripts I recommend the following simple procedure:

  1. Create a cloud instance of a basic Ubuntu server (currently 14.04)
  2. SSH login using your favorite SSH client (e.g. MobaExterm: http:http://mobaxterm.mobatek.net/)
  2. sudo apt-get update
  3. sudo apt-get install git
  4. git clone https://github.com/asterkin/chol.git
  5. cd chol
  6. Run installation scripts upon the need; some scripts call reboot 
  7. Keep in mind there might be dependencies between scrpts, for example gradle-build assumes oracle-jdk8 being installed
  8. Save snapshot
  9. If you installed lxde graphical desktop with x2go-server you will need to install x2go-client from http://http://wiki.x2go.org/doku.php


