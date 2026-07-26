# Omni — binaires de release

Ce dépôt **ne contient aucun code source**. Il ne sert qu'à héberger les artefacts publiés par
la CI du dépôt principal (privé) : l'installeur `Omni-<version>-setup.exe`, son `.blockmap`, et
`latest.yml`, le manifeste que lit `electron-updater`.

## Pourquoi un dépôt séparé

L'application installée doit pouvoir lire ses propres releases. Sur un dépôt privé, cela exige un
jeton stocké sur la machine de l'utilisateur — or GitHub n'offre **aucune** permission « Releases »
isolée : les releases relèvent de `Contents`, la même permission qui donne la lecture du code source.

Un jeton pointant sur le dépôt principal aurait donc permis, s'il était dérobé, d'exfiltrer le code.
En déplaçant les binaires ici, le jeton stocké dans l'application ne donne plus accès qu'à des
installeurs — que son porteur exécute déjà. Le chemin de fuite disparaît.

## Ce qui écrit ici

Uniquement `.github/workflows/release.yml` du dépôt principal, via un secret d'Actions
(`RELEASES_TOKEN`) qui ne quitte jamais GitHub.

## Le jour où Omni deviendra public

Rendre ce dépôt public suffit : l'application n'a alors plus besoin d'aucun jeton.
