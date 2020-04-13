---
layout: default
title: Tado
lang: fr_FR
pluginId: tado
---

# Changelog
- [Changelog]({{site.baseurl}}/tado/{{page.lang}}/changelog)

# Description 

Plugin permettant de connceter jeedom à l'API non officielle de Tado

# Configuration générale

Rien de plus simple, après avoir activé votre plugin, il faut renseigner vos 
identifiants de connection à Tado dans la page de configuration du plugin.
Cliquer ensuite sur "Autoriser" et vérifer que le message de confirmation 
d'autorisation est bien obtenu.

Une fois l'autorisation confirmée, il suffit d'aller sur la page du plugin
et lancer une synchronisation pour récupérer tous les équipements.

# Configuration spécifique

Certains équipements contiennent des paramètres configurables

## Maison
Pour les Maisons, à partir de la page de configuration de l'équipement, vous pouvez:
-   activer/désactiver le passage automatique en mode Home/Away lorsque que vous 
	entrez/quittez le domicile


## Zones

Pour les Zones, à partir de la page de configuration de l'équipement, vous pouvez:
-   activer/désactiver la détection de fenêtre ouverte
-   modifer le timeout du mode fenêtre ouverte
-   activer/désactiver le passage automatique en mode fenêtre ouverte lors 
	d'une détection par Tado
-   détecter les fenêtres ouverte grace à un capteur externe en
	selectionnant la commande jeedom correspondante. La fonctionnalité de 
	détection par Tado sera alors désactivée. #En Developpement#
-   Spécifier un capteur de température externe (utile pour les zone qui
	utilisent une tête thermostatique pour mesurer la temperature) 
	#En Developpement#


