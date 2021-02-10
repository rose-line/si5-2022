# TP Scripting BASH

## 0. Introduction

Lire le petit [cours sur le scripting](scripting_bash.md).

## 1. Menu pour utilisateur lamda

Il s'agit de créer un script permettant à un utilisateur non familiarisé d'utiliser des commandes shell. Un tel script va permettre à l'utilisateur d'exécuter des commandes sans vraiment les connaître. L'utilisateur se voit proposé un menu.

Le script devra proposer les options suivantes :

1. Afficher les utilisateurs qui sont connectés
2. Afficher les informations système (`uname -v`)
3. Afficher le fichier le plus volumineux dans le répertoire courant
4. Afficher les infos CPU (`lscpu`, mais seulement les premières lignes significatives)
5. Afficher l'heure système
6. Sortir du programme

Vous utiliserez une boucle pour que le menu soit de nouveau présenté à l'utilisateur après chaque commande.

Une première entrée incorrecte doit être signalée : « Merci d'entrer un chiffre entre 1 et 6 ». Les entrées incorrectes suivantes devront être sanctionnées d'un « Entre 1 et 6, grosse quiche ».

Le script se termine quand l'option 6 est choisie.

## 2. Rapport automatique

Les scripts sont souvent utilisés pour effectuer des vérification automatiques et/ou des rapports sur le système.

Créez un script qui va rechercher dans tout le système les fichiers suivants :

- fichiers SUID
- fichiers SGID (pas les répertoires)
- fichiers et répertoires qui ont les droits d'écriture pour `others` (mais pas les liens symboliques)

Ce script va écrire son rapport dans le répertoire `/var/reports`. Le rapport va inclure toutes les informations citées et le nom du fichier devra être **rapport-fichiers-*date***`, où *date* sera remplacé par la date courante (exemple `rapport-fichiers-10-02-2021`).

Testez ce script en tant que root.

Faites en sorte que le script s'exécute sur votre système toutes les nuits à 4 h 30 (renseignez-vous sur la `crontab` et le répertoire `/etc/cron.d`).

QUESTION : pourquoi voudrait-on effectuer de tels rapports ? Pourquoi serait-il même souhaitable que les rapports soient automatiquement comparés avec le précédent ?
