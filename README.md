# docker

https://docs.docker.com/engine/install/ubuntu/

install docker enginig kell csak

sudo adduser (felhasznalo) --> docker ki kell kapcsolni a gépet és ujra bekapcsolni

sudo adduser loczylevi docker

docker pull ubuntu

docker run --name myXampp -p 41061:22 -p 41062:80 -d -v ~/my_web_pages:/www tomsik68/xampp
