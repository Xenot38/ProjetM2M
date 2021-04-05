#Rapport Technique

##Matériel
Nous avons utilisé un kit P_Nucleo_LRWAN2 contenant une gateway (Nucleo_F746ZG) et un endpoint (I_Nucleo_LRWAN1).
Le endpoint nous fournit un ensemble de données via des capteurs (temperature, humidité, ect ...) ainsi que deux boutons poussoir pour interagir avec la board et des leds.

##Outils utilisés
Nous avons utilisés l'IDE STM32Cube pour programmer en C le code qui permet (après compilation) de flasher les endpoints.
Pour le traitement des données nous avons utilisé nodered lancé dans un docker.

##Objectif
Nous devions combiné notre savoir faire et les outils fournis pour réalisé un système d'alarme incendie qui depuis les capteurs des endpoints nous permet de récupérer des données qui seront ensuite envoyé via le réseau lora sur les gateways. Ces gateway permettent de rejoindre via internet nodered. Nodered traite les données et est sensé renvoyer une message dans le sens inverse pour informé tous les endpoints de l'application si une alarme est déclanché ou non.

##Réalisation
Un message est envoyé périodiquement à l'application par chaque endpoints. Lorsqu'un utilisateur appuie sur un bouton cela lève une interuption qui permet de modifier la valeur d'une variable. Cette variable ainsi que les données de température permettent de définir si une alarm doit être lancé par l'application server sur NodeRed
