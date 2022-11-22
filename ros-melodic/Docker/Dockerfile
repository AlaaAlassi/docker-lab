FROM osrf/ros:melodic-desktop-full

# intall fire fox to test GUI
RUN apt-get update && apt-get install -y firefox
RUN apt install -y xauth
RUN touch /root/.Xauthority


CMD ["/usr/bin/firefox"]