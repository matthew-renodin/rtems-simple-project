# rtems-simple-project

The purpose of this project is to create a very simple manifiest that supports a simple project.

You use this project by using Google Repo. 

## Preperation 
### Install Google Repo

https://gerrit.googlesource.com/git-repo/


### Besides Google Repo this requires several programs to run build and run RTEMS on qemu


This is some information I took from the Host Dependencies page on the RTEMS site:

The basic build package on Debian or Ubuntu is the build-essential package. To install run:

sudo apt-get update
sudo apt-get install build-essential
sudo apt-get install cmake ccache ninja-build
sudo apt-get install python-dev python-pip 
sudo apt-get install libxml2-utils ncurses-dev
sudo apt-get install curl git doxygen

To build for ARM targets you will need a cross compiler. In addition, to run RTEMS projects on a simulator you will need qemu. Installation of these additional base dependencies include running:

sudo apt-get install gcc-arm-linux-gnueabi g++-arm-linux-gnueabi
sudo apt-get install gcc-aarch64-linux-gnu g++-aarch64-linux-gnu
sudo apt-get install qemu-system-arm qemu-system-x86
(you can install the hardware floating point versions as well if you wish”

sudo apt-get install gcc-arm-linux-gnueabihf g++-arm-linux-gnueabihf


## Initialize the project

mkdir helloworld
cd helloworld 

### Run Google Repo and that will checkout this project. This will clone the projects.

repo init -u https://github.com/matthew-renodin/rtems-simple-project 

repo sync

mkdir build
cd build

../init-build.sh -DPLATFORM=zynq7000 -DAARCH32=1 -DSIMULATION=1

ninja

./simiulate






