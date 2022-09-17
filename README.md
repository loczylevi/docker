# docker Ubuntura -- Használati utasítás

megnyitod ezt a linket itt kell letelepiteni a dockert:

https://docs.docker.com/engine/install/ubuntu/

install docker engin-ig kell csak!

sudo adduser (felhasznalo) --> docker ki kell kapcsolni a gépet és ujra bekapcsolni

sudo adduser loczylevi docker 

docker pull ubuntu

docker pull tomsik68/xampp

docker run --name myXampp -p 41061:22 -p 41062:80 -d -v ~/my_web_pages:/www tomsik68/xampp                         

______________________________________

-p 41061:22 -p 41062:80  --> ezeken a portokon megy a docker vagy valami ilyesmi

_____________________________________

https://hub.docker.com/r/tomsik68/xampp/

localhostal beinditani a php myadmint!

<<< Tesztelések >>>>

docker run -it ubuntu

docker pull tomsik68/xampp

top --> feladatkezelő

sudo apt install htop --> részletesebb top

ps

ps axfu

docker ps --> ,mi fut

docker ps -a --> részletesebb 

docker -9 --> kill all

docker rm nice_kirch 

docker container stats myXampp --> stat

docker images

docker run hello-world

docker version


_____________________________________
docker ujrainditása ha "elaludt"

docker rm myXampp

docker run --name myXampp -p 41061:22 -p 41062:80 -d -v ~/my_web_pages:/www tomsik68/xampp     

_____________________________________
