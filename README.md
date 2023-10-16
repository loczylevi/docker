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

____________________________________________________
docker konténer kitörlése és elinditása

docker rm myXampp

docker run --name myXampp -p 41061:22 -p 41062:80 -d -v ~/my_web_pages:/www tomsik68/xampp  

_____________________________________

docker ujrainditása ha "elaludt"

docker run myXampp

_____________________________________

## docker 2023.oktober 16. commandok

docker 

docker run hello-world

docker run ubuntu                   --> egy konténerben ubuntut futtatunk

docker run -it ubuntu               --> _"-it"_ -nek köszönhetően interaktívan bele megy a programban

docker rm <ID>                      --> a docker _rm_ vagyis _remove_ parancsal kitörli azt a konténert amelyik ID azonositója alapján megadtunk

docker inspector <ID>               --> részletes leirások egy konténerről

docker ps                           --> kilistázza a futo docker konténereket

docker ps -a                        --> _a_ annyit tesz mint _all_ vagyis az összes futo konténert listázza  _(Show all containers (default shows just running))_

docker run _valami_                 --> futtat konténert (mindig egy imagel indit egy uj konténert)

docker images                       --> kilistázza az imageket

docker rmi <img ID>                --> _rmi_ annyit teszt mint _remove image_  

ps ax                             --> listázza a futó alkalmazásokat

docker run -it ubuntu 
