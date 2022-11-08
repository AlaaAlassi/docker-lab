# docker-lab
Test building images

# Runing carla server/client containers demo

First run the carla-server 
```
sudo docker run --privileged --gpus all --net=host -e DISPLAY=$DISPLAY carlasim/carla:latest /bin/bash ./CarlaUE4.sh
```

Then run the client container in sleep mode to be able to debug it and connect it to the host network 
```
docker container run -d --name carla-client --network host carla-python-api:0.1 sleep infinity
```

Then log into the client container 
```
docker exec -it carla-client /bin/bash
```
inside the client container, navigate to `PythonAPI/examples` 
```
cd PythonAPI/examples
```
run any example 
```
python3 generate_traffic.py
```
if you see this message, it means the demo is working and you should be able to see cars runing around in the city
```
/carla/PythonAPI/examples# python3 generate_traffic.py
WARNING: Version mismatch detected: You are trying to connect to a simulator that might be incompatible with this API 
WARNING: Client API version     = 12682f7b 
WARNING: Simulator API version  = a1b37f7f 
spawned 30 vehicles and 10 walkers, press Ctrl+C to exit.
```
