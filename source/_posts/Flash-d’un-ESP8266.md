---
title: Flash d’un ESP8266
date: 2017-05-03 10:43:56
tags:
---

![](images/all_esp_modules1.png)

## Prérequis

Voici les prérequis pour réaliser le flash d’un esp8266 :

- 1 [esp8266 01]();
- 1 [FTDI FT232RL USB]() to TTL;
- 1 alimenation 5v;
- le firmware [nodemcu]() afin de développer en LUA;
- le logiciel [ESP8266Flasher]() afin d’installer le firmware sur votre esp8266.

### Note

Vous avez besoin d’un bon régulateur 3.3v avec une alimentation qui peut délivrer de 500 à 600mA.
Si vous avez des erreurs dès le démarrage du wifi, l’alimentation est probablement en cause.

## ESP8266 pins

![](images/pins-1.jpg)

## Câblage

![](images/firmware-1050x558.png)

### Attention !

N’utiliser pas le 3.3v de votre FTDI (si disponible) mais passer plutôt par un régulateur LF33CV (5v to 3.3v).
 
## Flash 

La procédure est détaillée sur le [Github du projet](https://github.com/nodemcu/nodemcu-flasher).

Veuillez à bien respecter la procédure dans l’ordre étape par étape.

Dès lors que votre ESP8266 est alimenté, vous pouvez lancer le logiciel.

Par défaut un firmware (NodeMCU) est embarqué.

A savoir qu’il existe plusieurs types de firmware, dont les deux plus populaires :

- [NodeMCU](https://github.com/nodemcu/nodemcu-firmware) en LUA
- ESP8266 AT en C

Télécharger la dernier version de NodeMCU (actuellement nodemcu_float_0.9.6-dev_20150704).

Dans Config, supprimer toute la configuration et rajoutez uniquement nodemcu_float_0.9.6-dev_20150704.bin (en cochant bien la checkbox de gauche).

![](images/config.png)

Dans Operation, séléctionner le port COM correspondant à votre FTDI et lancez le flash.

Si l’esp est bien détecté un QRcode doit apparaître dans la seconde et la barre de progression doit commencer à avancer.

![](images/config_02.png)

A la fin de l’update, une icône verte apparaîtra pour confirmer le succès de l’opération.

Vous pouvez dès lors débrancher votre ESP8266 et retirer le GPIO_0 du GND.

### Problème de détection ?

Si l’ESP8266 n’est pas détecté par le logiciel, débranchez et rebrancher l’alimentation de l’ESP8266 pour forcer la détection.