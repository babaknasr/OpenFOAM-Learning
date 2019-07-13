# Install OpenFOAM (v7)

## *** Install on Windows 10 Linux bash ***
```
sudo add-apt-repository http://dl.openfoam.org/ubuntu

sudo sh -c "wget -O - http://dl.openfoam.org/gpg.key | apt-key add -"

sudo apt-get update

sudo apt-get upgrade

sudo apt-get -y install openfoam7

echo "source /opt/openfoam7/etc/bashrc" >> .bashrc

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
## *** Install OpenFOAM (v7) on macOS ***

### Install docker:
https://docs.docker.com/docker-for-mac/install/
Run the Docker

### Install Xquartz
https://www.xquartz.org

from "XQuartz → Preferences → Security" select  “Allow connections from network clients” and “Authenticate connections”

It may need to restart the mac

Then:
```
sudo curl --create-dirs -o /usr/local/bin/openfoam7-macos http://dl.openfoam.org/docker/openfoam7-macos

sudo chmod 755 /usr/local/bin/openfoam7-macos
```
### Create file system
```
sudo curl -o /usr/local/bin/openfoam-macos-file-system http://dl.openfoam.org/docker/openfoam-macos-file-system

sudo chmod 755 /usr/local/bin/openfoam-macos-file-system

openfoam-macos-file-system -h
```

```
mkdir -p $HOME/openfoam
```
Go to the directory
```
cd $HOME/openfoam

openfoam7-macos
exit

openfoam7-macos -p

mkdir -p $FOAM_RUN

exit
```

