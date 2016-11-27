#LINUX 2

## TP2

###Critères auquels doit répondre la passarelle "GATEWAY"

* Délivrance d'adresse IP dynamique dans le réseau : 192.168.1.0/24
* Délivrance d'adresse IP statique dans le réseau : 192.168.2.0/24
--> L'adresse mac de notre serveur web est 00:21:fa:03:e5:46, son adresse IP 192.168.2.1
* Routage des paquets des 2 sous-réseaux
* Serveur openssh on écoute sur le port 26 (le port par défaut étant le 22)
* Le serveur dhcp est un serveur ISC

###Feuille de route

#### 0) Configuration des cartes réseaux de la VM (via Virtual Box)

Via l'interface de Virtual Box, je configure le réseau en mode :
* Accès par pont
* Cocher : "Câble branché"

#### 1) Installation du serveur openssh

Je lance la VM **GATEWAY**.
En ligne de commande :
* sudo apt-get install openssh-server

##### Configuration de la VM "GATEWAY"

Adresse IP : 192.168.99.170/24 Interface : eth0

#### 2) Connexion au serveur openssh depuis l'hôte

--> En tant qu'utilisateur courant **debian** : **# sudo ssh debian@192.168.99.170**

Connexion OK.

--> En tant qu'utilisateur **root** : **# sudo ssh root@192.168.99.170**

Ici, la connexion n'est pas possible. **permision denied**.

##### Fichier /etc/ssh/sshd_config

Pour résoudre le problème de connexion en **root**, et pour changer le port d'écoute (26 au lieu de 22), j'édite le fichier :
* /etc/ssh/sshd_config

Dans les première ligne, on change le port d'écoute.

Pour le problème de connexion en root. Je change la ligne :

* #Authentification:
* PermitRootLogin --> yes


