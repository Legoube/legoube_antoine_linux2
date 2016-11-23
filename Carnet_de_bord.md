#LINUX 2

## TP1

###Configuration de la machine

* Installation de l'image Debian
* Mot de passe ROOT : **root**
* Nom utilisateur : **debian** 
* Mot de passe utilisateur : **debian**
* Nom de domaine : **.net**

###Premier démarrage

####Installation des paquets :

* **lynx**
* **sudo**
* **tcpdump**
* **vim**

####Modification des droits

La commande **sudo** n'est pas disponible de base... Il nous faut modifier le fichier de configuration dédié à **sudo**, en éxecutant
la commande **visudo** sous l'utilisateur **root**.

* Ajout de la ligne **debian  ALL=(ALL:ALL)  ALL** sous la ligne root *

Le fichier édité à l'aide de la commande **visudo** pourrais aussi être ouvert avec **vim /etc/sudoers**.
Mais lors de l'utilisation de l'utilitaire **vim**, le fichier est ouvert en lecture seule. Aucune modifications n'est possible.

###Clonage
Création de trois clones **intégrale** de la VM **debian_base** :
* Gateway
* Client
* Serveur

###Snapshot

SnapShot permet de sauvegarder une VM à un instant T.

Sur VirtualBox, l'interface graphique permet de faire un snapShot (icône **instantannée** en haut à droite).

* En utilisateur *root* : # rm -rf /

On peut ensuite réstaurer la VM au moment du snapShot. La machine redémarre et ce charge au moment T du snapShot.

###Configuration réseaux

Pour pouvoir accéder au réseau au même titre que ma machine physique, la VM doit avoir un accès réseau **par pont**.

* Modification de la configuration de **debian_base**. Menu --> Réseau --> accès par pont.
* Redémarrage de la VM.

####Execution de la commande ip addr
#####Configurations

* IP Machine Physique : 172.29.6.147
* IP Machine Virtuel : 172.29.5.73

**/!\ Ma machine physique est actuellement liée au réseau via Wi-fi.**

Après branchement du cable Ethernet de ma machine physique au réseau, et modification de la configuration réseau de
ma machine virtuel :

* IP Machine Physique : 192.168.99.109
* IP Machine Virtuel : 192.168.99.170

**/!\ Ma machine physique maintenant liée au réseau via Ethernet.**

####Execution de lynx

Pour tester la connexion de ma VM, j'utilise l'utilitaire **lynx** :
* # lynx
* commande : **G** --> effectuer une recherche --> **https://duckduckgo.com**
*A ce stade, il faut s'authentifier via le portail de l'université*

Maintenant, test de la connexion de ma machine Hôte.

* Navigateur --> **https://startpage.com**
*Demande d'authentification via le portail de l'université*

####REMARQUES

La connexion **accès par pont** "détache" la machine virtuel de la machine physique d'un point de vu réseau.
La connexion via le portail de l'université bloque l'accès à deux machine connéctées sur le même compte simultanement.




