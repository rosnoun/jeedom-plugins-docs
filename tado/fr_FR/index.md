---
layout: default
title: Tado
lang: fr_FR
pluginId: tado
---

# Changelog
- [Changelog]({{site.baseurl}}/tado/{{page.lang}}/changelog)

# Description 

Plugin permettant de connceter jeedom à l'API non officielle de Tado pour controler
son installation Tado depuis Jeedom

Attention, Ce plugin Jeedom repose sur l'API Tado utilisée par l'App mobile ou web de tado 
mais cette API n'est pas documentée ni mise a disposition de développeurs tierces, et son 
support peut etre modifié ou retiré sans préavis par Tado. Vous faites l'acquisition de
ce plugin à vos risques.

# Configuration générale

Rien de plus simple, après avoir activé votre plugin, il faut renseigner vos 
identifiants de connection à Tado dans la page de configuration du plugin.
Cliquer ensuite sur "Login" et vérifer que le message de confirmation 
d'autorisation est bien obtenu et que le compte apparait bien en compte "connecté".

Pour ceux qui possèderaient plusieurs installation Tado, le plugin permet de connecter 
plusieurs comptes Tado et ainsi d'unifier la gestion de ces comptes.

Pour supprimer un compte, vous faut cliquer sur le bouton correspondant à coté du compte.
Cette action aura pour effet de désactiver les équipements associé à ce compte mais sans 
les supprimer. En ajoutant à nouveau le compte, les équipements correspondant seront
réactivés.

Une fois l'autorisation confirmée, il suffit d'aller sur la page du plugin
et lancer une synchronisation pour récupérer tous les équipements de votre installation 
Tado.

# Configuration spécifique et utilisation

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

Toues les zones compatibles d'une modification de consigne de température possèdent une
commande thermostatique. Par défaut, un modification de la consigne de température sera 
active jusqu'au prochain changement de bloc horaires. Les blocs horaires sont ceux programmés 
dans l'application Tado.

Pour toutes les Zones compatibles d'une modification de consigne de température, à partir
de la page de configuration de l'équipement, vous pouvez modifier le mode de timeout lors
d'un changement de consigne de température avec	la commande Jeedom. Les possibilités sont 
identiques à celles de l'application Tado, à savoir:
-	Jusqu'au prochain changement de bloc horaire
-	Minuterie
-	Jusqu'a annulation par l'utilisateur. Le retour en mode de programmation automatique se 
	fait via la commande "auto"


### Zones Eau Chaude Sanitaire (HOT_WATER)

Les zones HOT_WATER permettent la mise ON/OFF de la production d'eau chaude sanitaire.
Si l'installation est compatible de la modification de température ECS, alors l'equipement
jeedom permettra ce pilotage.

### Zones Chauffage (HEATING)

Pour les Zones HEATING, à partir de la page de configuration de l'équipement, 
vous pouvez:
-   activer/désactiver la détection de fenêtre ouverte
-   modifer le timeout du mode fenêtre ouverte
-   activer/désactiver le passage automatique en mode fenêtre ouverte lors 
	d'une détection par Tado
-   Spécifier un capteur d'ouverture pour détecter les fenêtres ouvertes en
	selectionnant la commande jeedom correspondante. La fonctionnalité de 
	détection par Tado sera alors désactivée. #En Developpement#
-   Spécifier un capteur de température externe (utile pour les zone qui
	utilisent une tête thermostatique pour mesurer la temperature). Attention, il semble 
	que l'envoi fréquent de commande d'offset sur une vanne thermostatique engendre des
	activations de celle-ci et peut nuire à la durée de vie des piles. Cette fonctionnalité 
	sera mise a jour en fonction du retour d'expérience des utilisateurs.

### Zones Climatisation (AIR_CONDITIONING)

Pour les Zones AIR_CONDITIONING, à partir de la page de configuration de l'équipement, 
vous pouvez:
-   activer/désactiver la détection de fenêtre ouverte
-   modifer le timeout du mode fenêtre ouverte
-   activer/désactiver le passage automatique en mode fenêtre ouverte lors 
	d'une détection par Tado
-   Spécifier un capteur d'ouverture pour détecter les fenêtres ouvertes en
	selectionnant la commande jeedom correspondante. La fonctionnalité de 
	détection par Tado sera alors désactivée. #En Developpement#
-   Spécifier un capteur de température externe (utile pour les zone qui
	utilisent une tête thermostatique pour mesurer la temperature). Attention, il semble 
	que l'envoi fréquent de commande d'offset sur une vanne thermostatique engendre des
	activations de celle-ci et peut nuire à la durée de vie des piles. Cette fonctionnalité 
	sera mise a jour en fonction du retour d'expérience des utilisateurs.

A completer...

## Equipement mobiles

Les équipements mobiles sont ceux enregistré dans votre compte via l'application 
officielle. Ils permettent de connaitre leur position et s'ils sont détectés au domicile.
La géolocalisation de l'équipement en question doit être activée.

## Thermostats intelligents

L'API tado ne fournit, pour le niveau de batterie des équipement Tado sur batterie, qu'un 
état "NORMAL". Les autres état de batterie possible ne sont pour le moment pas connu par le 
développeur.
Le plugin se contente donc de traduire par 100% pour l'état 'NORMAL' et par 10% pour tout autre état 
remonté par l'API.

## Climatisations intelligentes

A compléter

## Vannes intelligentes

L'API tado ne fournit, pour le niveau de batterie des équipement Tado sur batterie, qu'un 
état "NORMAL". Les autres état de batterie possible ne sont pour le moment pas connu par le 
développeur.
Le plugin se contente donc de traduire par 100% pour l'état 'NORMAL' et par 10% pour tout autre état 
remonté par l'API.

## Météo

 A compléter

