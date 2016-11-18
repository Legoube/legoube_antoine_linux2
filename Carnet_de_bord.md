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

