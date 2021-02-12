---
layout: default
title: Changelog Tado
lang: fr_FR
pluginId: tado
---

# 2021-02-12
-	Ajout de variantes d'équipements clim
-	Ajout des Internet Bridge et Kit d'extension
-	Généralisation du traitement de synchronisation des équipements tado
-	Corrections de Bugs
-	Ajout des commandes de fanSpeed et swing (auto) aux commandes d'overlay des clim

# 2021-01-19
-	Retro compatibilité des commandes d'overlay avec app Tado V2
-	Caractéristiques d'affichage du widget regroupée dans config.json
-	Ajout d'une fonction de reset de l'affichage du widget
-	Ajout des paramètres FanSpeed et Swing aux commandes d'overlay des clim lorsque cela est supporté

# 2021-01-13
-	Ajout des smart clim type WR02
-	Ajout des capteurs de température Tado type SU02
-	Correction du bug FANSPEED lors de l'envoi de commande de changement de températures aux clim
-	Vérification de l'état de communication avec Tado avant les fonctions Cron du plugin

# 2020-05-03
-	Ajout d'une limitation de la commande d'offset de température (max 10°C)
-	Enregistrement du compte associé à chaque équipement seulement lors de la première synchro
-	Mise a jour de l'export de la configuration pour debug

# 2020-05-02
-	Correction de l'affichage pour la selection du timeout par défaut dans la configuration équipement
-	Ajout du support des vannes thermostatiques de type VA01
-	Correction de la conversion secondes vers minutes de la valeur du timeout

# 2020-04-30
Première version publique

# Documentation
[Voir la documentation]({{site.baseurl}}/{{page.pluginId}})
