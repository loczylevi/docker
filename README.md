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
docker run ubuntu
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

docker run hello-world             --> egy hello-world konténert futtatunk

docker run ubuntu                   --> egy konténerben ubuntut futtatunk

docker run -it ubuntu               --> _"-it"_ -nek köszönhetően interaktívan bele megy a programban

docker rm <ID>                      --> a docker _rm_ vagyis _remove_ parancsal kitörli azt a konténert amelyik ID azonositója alapján megadtunk

docker inspector <ID>               --> részletes leirások egy konténerről

docker ps                           --> kilistázza a futo docker konténereket

docker ps -a                        --> _a_ annyit tesz mint _all_ vagyis az összes futo konténert listázza  _(Show all containers (default shows just running))_

docker run _valami_                 --> futtat konténert (mindig egy imagel indit egy uj konténert)

docker images                       --> kilistázza az imageket

docker rmi <img ID>                --> _rmi_ annyit teszt mint _remove image_  vagyis image törlés

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

_______________________________________________

docker stop <ID>               --> leállitja a futó konténert

docker inspect <image ID>       --> kilistázza a konténer beáálitásait infoit

docker inspect <ID>             --> kilistázza a konténer beáálitásait infoit

docker ps                     --> konténerek állapota futo konténerek

docker volume ls              --> ki listázza a volumeket 

docker run _<valami>_         --> letölti és futtatja

docker pull _<valami>_        --> ez csak letölti de *NEM futtatja*

docker run -p 80:80 <konténer név>     --> a _"-p"_ vel azt mondjuk hogy hogy melyik porotn fusson a konténerünk példánkban a 80:80 porton futtatunk (ha webes konténered van akko ezután nyitsz egy webböngészöt azt az URL cimben beirod hogy localhost vagy 127.0.0.0)

docker run -p 80:80 -it <image> /bin/bash     interaktivan bele lépek a a futo konténerbe közben a 80 as porton futtatjuk a konténert 

docker run -p 80:80 -v docker:/elérésiutvonal/ <image név>   --> megmondjuk hogy honnan fusson a konténer


docker run --name web -p 80:80 -v ~/docker:/elérési utvonal/ <image név>

___________________________________________________________________-


#### törlések 

docker rm <ID>               --> törli a konténert

docker rmi <ID>               --> törli az imageket  

docker volume rm <ID>         --> törli a volumeket


______________________________________________________________

docker start <ID>                     --> elinditunk egy leálllitott konténert

docker start <ID> -i            

docker ps -a | awk '{print$1}'        --> ki listázzuk a futo konténereket DE csak az első oszlopot jelenitsd meg

sima docker ps -a

loczylevi@sis:~$ docker ps -a
CONTAINER ID   IMAGE         COMMAND              CREATED             STATUS                           PORTS     NAMES
e76e5fc3034c   httpd         "/bin/bash"          8 minutes ago       Exited (100) 4 minutes ago                 nifty_jackson
d51ed02ccc6a   httpd         "httpd-foreground"   9 minutes ago       Exited (0) 9 minutes ago                   vigilant_dubinsky
3ec5c460fdc2   httpd         "httpd-foreground"   13 minutes ago      Exited (0) 9 minutes ago                   condescending_ganguly
fb24f53f9332   ubuntu        "/bin/bash"          About an hour ago   Exited (0) About an hour ago               eloquent_engelbart
8e3b017b4921   hello-world   "/hello"             About an hour ago   Exited (0) About an hour ago               optimistic_bhabha
4fa8c7b42153   ubuntu        "bash"               About an hour ago   Exited (0) About an hour ago               romantic_khayyam
28c0d74ce7fb   hello-world   "/hello"             About an hour ago   Exited (0) 2 minutes ago                   blissful_rosalind
be3105b15853   ubuntu        "/bin/bash"          About an hour ago   Exited (127) About an hour ago             laughing_galois

docker ps-a csak első oszlop

loczylevi@sis:~$ docker ps -a | awk '{print$1}'
CONTAINER
e76e5fc3034c
d51ed02ccc6a
3ec5c460fdc2
fb24f53f9332
8e3b017b4921
4fa8c7b42153
28c0d74ce7fb
be3105b15853

második... 

loczylevi@sis:~$ docker ps -a | awk '{print$2}'
ID
httpd
httpd
httpd
ubuntu
hello-world
ubuntu
hello-world
ubuntu


és igy tovább...



### nem dockeres commandok de jó tudni (kitudja mit kérdezhetnek...)

mkdir <directory_name>           --> mkdir == make directory csinálj egyy uj könyvtárat

echo "buzi"                    --> printelünk a képernyőre

echo "teszt" > directory_name/valami.txt    --> bele irunk egy fálja de meg kell adnunk a fáljnak az elérési utvonalát

sudo kill <ID>                  --> kinyirunk megszüntetjük egy futó konténer futását 

sudo kill -9 <ID>               --> nyomatékosan leállitunk egy futo konténert vagyis _kapcsoljál már le bammeg+_

free                            --> mutatja a szabad memoriát

uname -a                        --> kernelnek milyne verziója van

cat /proc/cpuinfo               --> CPU, processzor infok

cat /proc/meminfo               --> memória info

cat /proc/diskstats             --> sok random szám passz  ¯\_(ツ)_/¯

ip a                           --> ip cim mac cim és egyéb cimek lekérése

ifconfig                       --> ip cim mac cim és egyéb cimek lekérése

ls                             --> listázz

ls -l                          --> listázz szószátyár üzemmód

pwd                           --> print work directory aktuális utvonal ahol vagy

ls -l /proc/

cd                            --> chance directory

cd ..                         --> vissza a szülökönyvtárhoz
 
less /etc/services             --> kilistázza az összes portot (q val kilépünk)

netstat                        --> mik futnak ip cuccmok

netstat lanpt                   --> szoszátyár üzemmód ip cucccmok 

netstat -lanpt | grep :80       --> csak azokat listázd ami 80 as port számú

a grep egy kereső command

cat directory_name/index.html           --> a cat parancs megmutatja mi van egy fálj belsejébe 

pl:
_____________________________________________________________
root@e76e5fc3034c:/usr/local/apache2# cat htdocs/index.html 

<html><body><h1>It works!</h1></body></html>

root@e76e5fc3034c:/usr/local/apache2# 
______________________________________________________________

példánkban az index.html ben egy alap HTML _(hpyer text markup language)_ skeletont láthatunk


## tryhard commandok (ノ°益°)ノ

docker ps -a | awk '{print "docker rm "$1}' | bash     --> psel kilistázom a futo kkonténereket a print$1 megmondom hogy az elsö oszlopot jelenitsd meg de utána ki printeljük plusszba a docker rm szöveget mellé a az elsö oszlop ID-eit plussz bash el kiadjuk a parancsokat

docker images | awk '{print "docker rmi "$3}' | bash





