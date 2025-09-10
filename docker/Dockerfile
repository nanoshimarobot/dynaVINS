FROM slamai/ubuntu18:cuda12.0.1

RUN sudo apt update \
    &&  sudo apt install -f \
    && sudo apt install -y -f libglew-dev \
       libxkbcommon-dev \
       cmake-qt-gui \
       libgoogle-glog-dev \
       libatlas-base-dev \
       libgflags-dev \
       libhdf5-serial-dev \
       libleveldb-dev \
       liblmdb-dev \
       libopencv-dev \
       libprotobuf-dev \
       libsnappy-dev \
       protobuf-compiler \
       python-numpy \
       python-tk \
       libeigen3-dev

RUN rosdep update

RUN sudo apt update \
    && sudo apt install -y -f rospack-tools \
    ros-${ROS_DISTRO}-tf2-msgs \
    ros-${ROS_DISTRO}-image-transport \
    ros-${ROS_DISTRO}-pcl-ros \
    ros-${ROS_DISTRO}-nav-msgs

COPY ./docker/ros_entrypoint.sh /root/ros_entrypoint.sh
RUN sudo chmod 755 /root/ros_entrypoint.sh
ENTRYPOINT ["/root/ros_entrypoint.sh"]

CMD ["bash"]
