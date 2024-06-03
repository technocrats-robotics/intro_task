
# Software Installation

## OS and ROS versions 
    Ubuntu 22.04
    ROS2 Humble

## Ubuntu 22.04 Installation guide 

[Installation Guide](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

## Ros2 humble Installation guide

### 1. Set locale:
 Make sure you have a locale which supports “UTF-8”. For this try the following commands.

```bash 
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
```

### 2. Setup Sources:
You will need to add the ROS 2 apt repository to your system.

First ensure that the Ubuntu Universe repository is enabled

```bash 
sudo apt install software-properties-common
sudo add-apt-repository universe

```
Now add the ROS 2 GPG key with apt.

```bash 
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

```
Then add the repository to your sources list.

```bash 
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

```
### 3.Install Ros2 packages
Update your apt repository caches after setting up the repositories.

```bash
sudo apt update
```
ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages.

```bash
sudo apt upgrade
```
Desktop Install 
```bash
sudo apt install ros-humble-desktop
```
### 4. Environment Setup:
Set up your environment by sourcing the following file.
```bash
source /opt/ros/humble/setup.bash
```
Automatically add ROS environment variables to your bash session every time a new shell terminal/bash is launched, enter the following command.
```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
```
Sourcing bashrc ensures to use updated bashrc using the following command, or it can be done by closing all terminals and re-opening a new terminal.
```bash
source ~/.bashrc
```
## Installation check

In one terminal, source the setup file and then run a C++ talker:
```bash
ros2 run demo_nodes_cpp talker
```

In another terminal source the setup file and then run a Python listener:
```bash
ros2 run demo_nodes_py listener
```
You should see the talker saying that it’s publishing messages and the listener saying I heard those messages. This verifies both the C++ and Python APIs are working properly.


