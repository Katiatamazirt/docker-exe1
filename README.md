# docker-exe1
## Creation un repo github nommé **docker-exe1** 
### -----aller sur notre compte github céer un github Repositories par la suite New cocher public et README.md, ajouter .gitignore en choisissant Python, et choisir la licence MIT
## -----mettre en place dans goland la connexion ssh vers notre VM en allant dans Tools-deployement-configuration
### ----- le mapping sur le deployment path sur /home/ubuntu/docker-exe1
## faire un git clone de notre directory project local en copiant d'abord le code et par la suite se positionner sur docker-exe1/ avec la commande
cd docker-exe1/
## pour la commande docker run on doit être en interactif et avec un tty pour le display le container doit etre nommé **myalpes** création du volume /MountPoint et image doit etre alpine passer la commande /bin/ash 
docker run -it --name myalpes -v /MountPoint alpine /bin/ash
## Ensuite a l'interieur du container creer un fichier test.py et inserez le texte "WARNING: ret pointer is null"
vi test.py 
## et mettre le text "WARNING: ret pointer is nul"
## a partir de ce container créer une image nommée  myalpine:v12.
docker commit myalpine:version12
## Supprimer les metadata de cette image avec docker export et docker import
## -----export
docker export myalpes >archi-ex1.tar
### ------- verification
docker history myalpine:v12
## ----import
cat archi-ex1.tar | docker import - myalpine:version12
## Verifier aavec docker history 
docker history myalpine:version12

## mettez cette image dans docker hub sous votre compte docker hub
docker login -u katiatamazirt -p rayaneetsamy2
docker image tag myalpine:version12 katiatamazirt/myalpine:version12
docker push katiatamazirt/myalpine:version12
## mettre à jour mon dossier sur github
1 git commit -am"solution exo01"
### il me demande l'identification donc je passe par la suite
2 git config --global user.email katiatamazirt@hotmail.com
3 git config --global user.name katiatamazirt
6 git commit -am"solution exo01"
7 git push origin main

