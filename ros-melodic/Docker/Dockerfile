FROM osrf/ros:melodic-desktop-full
#FROM gazebo:latest

RUN apt-get update && apt-get install -y firefox
RUN apt install -y xauth
RUN touch /root/.Xauthority
ENV DISPLAY=:1
RUN export DISPLAY; echo $DISPLAY

CMD ["/usr/bin/firefox"]