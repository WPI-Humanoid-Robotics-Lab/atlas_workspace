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

# Workspaces 
- `atlas_gazebo_ws.yaml` - Configures all the repos required for running atlas robot in gazebo simulator on Ubuntu 16.04, ros kinetic, and controller version : 0.11 
- `atlas_ws_0.11.yaml` - Configures all the repos required for running atlas robot in SCS simulator on Ubuntu 16.04, ros kinetic, and controller version : 0.11. If we manually copy val_description into ros packages from ubuntu 14.04, valkyrie can be used with this config.
- `atlas_ws_0.9.yaml` - Configures all the repos required for running atlas robot in SCS simulator on Ubuntu 16.04, ros kinetic, and controller version : 0.9. If we manually copy val_description into ros packages from ubuntu 14.04, valkyrie can be used with this config.
- `src_repos.yaml` - Configures srcsim in docker. This is requires Ubuntu 14.04 and ros indigo.
