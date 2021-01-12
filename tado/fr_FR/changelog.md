---
layout: default
title: Changelog Tado
lang: fr_FR
pluginId: tado
---

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
