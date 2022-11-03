#FROM carlasim/carla:latest
FROM ubuntu:latest

COPY helloWorld.cpp /

#USER root
RUN apt-get update

RUN apt-get install -y g++

RUN g++ helloWorld.cpp

CMD ["./a.out"]