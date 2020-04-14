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

## Homes

L'équipement maison donne l'état général du système, à savoir présent (HOME) ou
absent (AWAY); Il permet également de commander manuellement ce même état. En mode
AWAY, la consigne de température est celle que vous avez spécifié pour chaque zone
dans la zone de configuration dédiée de l'application officielle.

Pour les Maisons, à partir de la page de configuration de l'équipement, vous pouvez:
-   activer/désactiver le passage automatique en mode Home/Away lorsque que vous 
	entrez/quittez le domicile #En Developpement#


## Zones

Les zones sont celles que vous avez configuré via l'application officielle. Il existe 
3 types de zones : Eau chaude (HOT_WATER), chauffage (HEATING) et climatisation 
(AIR_CONDITIONING). Chaque type de zone a des capacités différentes. Les zones 
HOT_WATER n'ont pas toutes la possibilité de modifier la température de consigne, 
auquel cas la commande de modification de température de consigne restera sans effet.

Les blocs horaires de changement de température de consigne sont configurés depuis 
l'application officielle.

La commande de modification de la consigne de température sera effective par défaut
jusqu'au prochain bloc horaire. Vous pouvez modifier ce comportement depuis la page 
de configuration de l'équipement Jeedom. Notez que l'option TIMER necessite une durée 
en minutes qui doit etre comprise entre 5min et 720min (i.e. 12h)

Pour les Zones, à partir de la page de configuration de l'équipement, vous pouvez:
-   activer/désactiver la détection de fenêtre ouverte
-   modifer le timeout du mode fenêtre ouverte
-   activer/désactiver le passage automatique en mode fenêtre ouverte lors 
	d'une détection par Tado
-	modifier le mode de timeout lors d'un changement de consigne de température avec
	la commande Jeedom
-   détecter les fenêtres ouverte grace à un capteur externe en
	selectionnant la commande jeedom correspondante. La fonctionnalité de 
	détection par Tado sera alors désactivée. #En Developpement#
-   Spécifier un capteur de température externe (utile pour les zone qui
	utilisent une tête thermostatique pour mesurer la temperature) 
	#En Developpement#

## Equipement mobiles

Les équipements mobiles sont ceux enregistré dans votre compte via l'application 
officielle. Ils permettent de connaitre leur position et s'ils sont détectés au domicile.
La géolocalisation de l'équipement en question doit être activée


## Thermostats intelligents2

L'API tado ne fournit, pour le niveau de batterie des équipement Tado sur batterie, qu'un 
état "NORMAL". Les autres état de batterie possible ne sont pour le moment pas connu par le 
développeur.
Le plugin se contente donc de traduire par 100% pour l'état 'NORMAL' et par 10% pour tout autre état 
remonté par l'API.

## Vannes intelligentes

L'API tado ne fournit, pour le niveau de batterie des équipement Tado sur batterie, qu'un 
état "NORMAL". Les autres état de batterie possible ne sont pour le moment pas connu par le 
développeur.
Le plugin se contente donc de traduire par 100% pour l'état 'NORMAL' et par 10% pour tout autre état 
remonté par l'API.

## Météo


