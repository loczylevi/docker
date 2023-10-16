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

alapok alapja 

ugye 
dokcker run ubuntu
docker run hello-world

ezekkel a fenti commandokkal konténereket futtatunk
na ez szép és jó de hogyan látom hogy futnak?
ezzel a commandal:
__________________________________________________________________________

loczylevi@sis:~$ docker ps -a
CONTAINER ID   IMAGE         COMMAND       CREATED          STATUS                        PORTS     NAMES
fb24f53f9332   ubuntu        "/bin/bash"   10 minutes ago   Exited (0) 10 minutes ago               eloquent_engelbart
8e3b017b4921   hello-world   "/hello"      28 minutes ago   Exited (0) 28 minutes ago               optimistic_bhabha
4fa8c7b42153   ubuntu        "bash"        31 minutes ago   Exited (0) 31 minutes ago               romantic_khayyam
28c0d74ce7fb   hello-world   "/hello"      32 minutes ago   Exited (0) 32 minutes ago               blissful_rosalind
be3105b15853   ubuntu        "/bin/bash"   38 minutes ago   Exited (127) 34 minutes ago             laughing_galois
_____________________________________________________________________________


mint a fenti példában látható minden futo konténernek van egy CONTAINER ID vagyis specko ID je szoval mikor a lenti jegyzetekben látsz ilyet hogy <ID> akkor a konténerednek az ID-jét kell megadnod _(ha mondjuk törölni kell vagy valami...)_

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

docker run -it ubuntu /bin/bash   -->  ugyanugy interaktivan ubuntut futattunk csak bin/bash faszsággal ami nem tudom mit csinál ¯\_(ツ)_/¯

ps ax | grep mys                  --> mint ugye elözöekben láttuk a ps ki listázza a gépeden futo alkalmazásokat a "_grep_" az egy kereső, szürő parancs amivel keresni tudunk ha rengeteg dolog küzül nekünk csak egy bizonyos információra van szükségünk!

pl:
________________________________________________
loczylevi@sis:~$ ps ax | grep docker
   1107 ?        Ssl    0:06 dockerd --group docker --exec-root=/run/snap.docker --data-root=/var/snap/docker/common/var-lib-docker --pidfile=/run/snap.docker/docker.pid --config-file=/var/snap/docker/2893/config/daemon.json
   1463 ?        Ssl    0:04 containerd --config /run/snap.docker/containerd/containerd.toml --log-level error
   1712 ?        Ssl    0:00 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
   5147 pts/0    S+     0:00 grep --color=auto docker
___________________________________

mint a  fenti példában látható futtatjuk a ps commandot ami ugye listázza a futo dolgokat de grep commandal megmondtuk neki hogy csak azokat listázza aki amiben szerepel a "docker" szó, kifejezés




      
