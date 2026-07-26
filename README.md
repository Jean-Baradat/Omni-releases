# Omni — binaires de release

Ce dépôt **ne contient aucun code source**. Il n'héberge que les artefacts publiés par la CI
d'Omni : l'installeur `Omni-<version>-setup.exe`, son `.blockmap`, et `latest.yml`, le manifeste
que lit `electron-updater`.

## Pourquoi il est séparé, et public

L'application installée doit pouvoir lire ses propres releases pour se mettre à jour. Si elle
lisait celles d'un dépôt privé, il faudrait un jeton d'accès sur la machine de chaque utilisateur —
et GitHub n'offre **aucune** permission « Releases » isolée : les releases relèvent de `Contents`,
la permission qui donne aussi la lecture du code source. Un tel jeton, volé, aurait donc exposé le
code ; et il aurait fallu le distribuer à chaque utilisateur.

Séparer les binaires du code résout les deux problèmes d'un coup : ce dépôt peut être public sans
rien révéler du code, l'application le lit sans authentification, et il n'y a plus aucun secret à
stocker ni à transmettre.

Le code source d'Omni reste dans un dépôt privé.

## Ce qui écrit ici

Uniquement le workflow de release du dépôt principal, via un secret d'Actions (`RELEASES_TOKEN`)
qui ne quitte jamais GitHub.
