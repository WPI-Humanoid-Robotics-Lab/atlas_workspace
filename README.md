# atlas_workspace
This repo contains configuration files to quickly pull down Atlas repositories using vcstool for various workstations.  

# Install vcstool  

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'  
sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116  
sudo apt-get update  
sudo apt-get install python-vcstool  
```
For autocomplete with vcstool, append this to the ~/.bashrc file:  
```
source /usr/share/vcstool-completion/vcs.bash  
```

# Install catkin_tools  
  
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu `lsb_release -sc` main" > /etc/apt/sources.list.d/ros-latest.list'  
wget http://packages.ros.org/ros.key -O - | sudo apt-key add -  
sudo apt-get update  
sudo apt-get install python-catkin-tools  
```

# Instructions for workspace:  

Navigate to workspace ( cd ~/workspace )  
```
catkin config --init --mkdirs  
cd src  
vcs import < path-to-yaml/repos.yaml  
rosdep install --from-paths src --ignore-src -r -y 
catkin_make
```
