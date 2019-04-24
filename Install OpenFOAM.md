# Install OpenFOAM (v6)

## *** Install on Windows 10 Linux bash ***
```
sudo add-apt-repository http://dl.openfoam.org/ubuntu

sudo sh -c "wget -O - http://dl.openfoam.org/gpg.key | apt-key add -"

sudo apt-get update

sudo apt-get upgrade

sudo apt-get -y install openfoam6

echo "source /opt/openfoam6/etc/bashrc" >> .bashrc

source $HOME/.bashrc
```

### Install Xming: https://openfoam.org/download/windows/xming-download
```
echo "export DISPLAY=:0" >> .bashrc

source $HOME/.bashrc

sudo apt-get install gedit gedit-plugins

sudo apt-get install gnuplot gnuplot-x11 gnuplot-doc libgd-tools

sudo apt install dbus-x11

sudo service dbus start

sudo apt-get install mplayer mencoder

sudo apt install nautilus

mkdir -p $FOAM_RUN
```
### Testing
```
gedit &

simpleFoam -help
```

***
## *** Install OpenFOAM (v6) on macOS ***

### Install docker:
https://docs.docker.com/docker-for-mac/install/
Run the Docker

### Install Xquartz
https://www.xquartz.org
Select XQuartz → Preferences → Security
```
sudo curl --create-dirs -o /usr/local/bin/openfoam6-macos http://dl.openfoam.org/docker/openfoam6-macos

sudo chmod 755 /usr/local/bin/openfoam6-macos

mkdir -p $HOME/OpenFOAM
```
Go to the directory
```
cd $HOME/OpenFOAM

openfoam6-macos
exit

openfoam6-macos -p

mkdir -p $FOAM_RUN

exit
```
### Create file system:???
```
sudo curl -o /usr/local/bin/openfoam-macos-file-system http://dl.openfoam.org/docker/openfoam-macos-file-system

sudo chmod 755 /usr/local/bin/openfoam-macos-file-system

openfoam-macos-file-system -h
```
