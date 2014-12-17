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
  6. ./docker-install
  7. ./set-user <username> "Full Name" e-mail server (e.g. ./set-user asterkin "Asher Sterkin" cisco)
  8. Reconnect as <username>
  9. git clone http:github.com/asterkin/chol (it's definitely imperfect, need to think about better way)
  10. cd chol
  11. Run other installation scripts upon the need; some scripts call reboot 
  12. Keep in mind there might be dependencies between scrpts, for example gradle-build assumes oracle-jdk8 being installed

If you work with a team you might want to create a snaphot of graphical desktop environment:

  1. SSH login as ubuntu
  2. sudo apt-get update -y
  3. sudo apt-get install -y git
  4. git clone http://github.com/asterkin/chol
  5. cd chol
  6. ./docker-install
  7. ./minimal-lxde-desktop
  8. ./x2go-server (you will need an x2go client from http://http://wiki.x2go.org/doku.php)
  9. sudo cp set-user /usr/bin
  10. cd ..
  11. rm -rf chol
  12. make a snapshot, for example ubuntu-14.4-docker-lxde
  13. Other snapshots could be built on the top this basic one. I need to think how to dockerize all this business such that every developer will have only one instance, e.g. asher-desktop with
      the rest beong run from docker containers. It would require complete re-write of all chol scripts
  14. When creating an instance from this snapshot every user could run set-user to personalize the instance



