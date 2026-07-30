# Omni

**[English](#english) · [Français](#français)**

---

## English

Omni is an **augmented project manager for Windows**.

You talk to a single chat — the *manager*. It does the rest: it recruits a team of AI agents
(Claude Code sessions), hands each one a task, lets them talk to one another, follows their
progress, and reports back to you. You stay in the conversation; the team works underneath.

### Download

Take the latest **`Omni-<version>-setup.exe`** from the [Releases](../../releases/latest) page and run it.

- Windows 10 or 11, 64-bit.
- The installer sets Omni up for your user account only, so it never asks for administrator rights.
- Omni checks for new versions by itself and installs them when you close it — you should not need to come back here.

### Before you start

Omni runs on your own Claude account, connected once in **Paramètres → Comptes Claude**:

- a **Pro or Max subscription** — run `claude setup-token` in a terminal (Claude Code installed, signed in to the right account), then paste the token into Omni;
- or an **Anthropic API key** (`sk-ant-api…`).

Nothing starts until an account is connected. The interface is in French.

### About this repository

This repository holds **no source code** — only what Omni's CI publishes: the installer, its
`.blockmap`, and `latest.yml`, the manifest `electron-updater` reads.

It is public on purpose. The installed app has to read its own releases to update itself, and GitHub
offers **no** Releases-only permission: releases live under `Contents`, the same permission that
grants read access to the source code. Reading them from a private repository would therefore have
meant shipping an access token — one that would have exposed the source if stolen — to every user's
machine. Keeping the binaries here removes the token entirely: the app reads this repository
anonymously, and there is nothing secret left to store or distribute.

Omni's source code stays in a private repository. Only its release workflow writes here, through a
GitHub Actions secret that never leaves GitHub.

---

## Français

Omni est un **chef de projet augmenté pour Windows**.

Vous parlez à un seul chat — le *manager*. Il se charge du reste : il recrute une équipe d'agents IA
(des sessions Claude Code), confie une tâche à chacun, les laisse communiquer entre eux, suit leur
avancement et vous en rend compte. Vous restez dans la conversation ; l'équipe travaille en dessous.

### Téléchargement

Prenez le dernier **`Omni-<version>-setup.exe`** sur la page [Releases](../../releases/latest) et lancez-le.

- Windows 10 ou 11, 64 bits.
- L'installeur installe Omni pour votre seul compte utilisateur : il ne demande aucun droit administrateur.
- Omni cherche les nouvelles versions tout seul et les installe à la fermeture — vous ne devriez pas avoir à revenir ici.

### Avant de commencer

Omni fonctionne avec votre propre compte Claude, connecté une fois dans **Paramètres → Comptes Claude** :

- un **abonnement Pro ou Max** — lancez `claude setup-token` dans un terminal (Claude Code installé, connecté au bon compte), puis collez le token dans Omni ;
- ou une **clé API Anthropic** (`sk-ant-api…`).

Rien ne démarre tant qu'aucun compte n'est connecté.

### À propos de ce dépôt

Ce dépôt ne contient **aucun code source** — seulement ce que la CI d'Omni publie : l'installeur, son
`.blockmap` et `latest.yml`, le manifeste que lit `electron-updater`.

Il est public à dessein. L'application installée doit lire ses propres releases pour se mettre à jour,
et GitHub n'offre **aucune** permission limitée aux releases : celles-ci relèvent de `Contents`, la
permission qui donne aussi accès au code source. Les lire depuis un dépôt privé aurait donc imposé de
livrer un jeton d'accès — qui aurait exposé le code s'il avait été volé — sur la machine de chaque
utilisateur. Garder les binaires ici supprime le jeton purement et simplement : l'application lit ce
dépôt anonymement, et il ne reste aucun secret à stocker ni à distribuer.

Le code source d'Omni reste dans un dépôt privé. Seul son workflow de release écrit ici, via un secret
GitHub Actions qui ne quitte jamais GitHub.
