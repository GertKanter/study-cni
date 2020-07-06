FROM ros:noetic-ros-core-focal

LABEL maintainer="INTEC Inc<info-rdbox@intec.co.jp>"

ENV ROS_DISTRO=noetic

COPY ./ros_entrypoint.sh /ros_entrypoint.sh

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
                                    build-essential

RUN /bin/bash -c "source /opt/ros/noetic/setup.bash && \
                mkdir -p /catkin_ws/src && \
                cd /catkin_ws/src && \
                catkin_init_workspace && \
                cd /catkin_ws/ && \
                catkin_make && \
                source /catkin_ws/devel/setup.bash && \
                chmod +x /ros_entrypoint.sh"

COPY ./talker /catkin_ws/src/talker
COPY ./listener /catkin_ws/src/listener

RUN /bin/bash -c "source /opt/ros/noetic/setup.bash && \
                source /catkin_ws/devel/setup.bash && \
                cd /catkin_ws/ && \
                catkin_make && \
                apt autoclean -y && \
                apt autoremove -y && \
                rm -rf /var/cache/apt/archives/* /var/lib/apt/lists/*"

ENTRYPOINT ["/ros_entrypoint.sh"]