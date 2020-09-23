FROM osrf/ros:kinetic-desktop

ENV NVIDIA_VISIBLE_DEVICES \
    ${NVIDIA_VISIBLE_DEVICES:-all}

ENV NVIDIA_DRIVER_CAPABILITIES \
    ${NVIDIA_DRIVER_CAPABILITIES:+$NVIDIA_DRIVER_CAPABILITIES,}graphics

# utils
RUN apt-get update && apt-get install -y debconf-utils wget apt-utils apache2 collectd python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential python-catkin-tools build-essential cmake imagemagick libboost-all-dev libgts-dev libjansson-dev libtinyxml-dev mercurial nodejs nodejs-legacy npm pkg-config psmisc xvfb && rm -rf /var/lib/apt/lists/*

#Add keys
RUN sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'

RUN wget https://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -

#Install gazebo
RUN apt-get update && apt-get install gazebo7 -q -y

#Install gazebo additional packages
RUN apt-get update && apt-get install -q -y \
    libgazebo7-dev\
    && rm -rf /var/lib/apt/lists/*

#Install gazebo_ros packages
RUN apt-get update && apt-get install -q -y \
    ros-kinetic-gazebo-plugins \
    ros-kinetic-gazebo-ros-control \
    ros-kinetic-gazebo-msgs \
    ros-kinetic-gazebo-ros \
    ros-kinetic-gazebo-ros-pkgs 

#intialize rosdep
RUN rosdep init & rosdep update

