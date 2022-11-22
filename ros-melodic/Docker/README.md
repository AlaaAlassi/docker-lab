## This image can run Gazebo and Firefox using he host Xserver
to build 
```
docker-compose build
```
to run 
```
docker-compose up
```

To launch a gazebo demo 
```
source /opt/ros/melodic/setup.bash
roslaunch gazebo_ros shapes_world.launch
```

to shutdown 
```
docker-compose down
```