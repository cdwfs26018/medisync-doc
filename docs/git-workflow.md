# Mise en œuvre technique

## T1

Le protocole de communication utilisé en standard par le client Git est **HTTPS** (HyperText Transfer Protocol Secure).

## T2

Le protocole utilisé en secours est **SSH** (Secure Shell), souvent utilisé comme alternative plus sécurisée et sans saisie de mot de passe après configuration.

## T3

Oui, il est possible de synchroniser un dépôt local avec plusieurs dépôts distants.

Pour cela, on peut ajouter plusieurs remotes avec la commande :

```bash
git remote add <nom> <url>
```

Ensuite, on peut pousser ou récupérer depuis chacun d'eux avec :

```bash
git push <nom>
git pull <nom>
```

## T4

La commande `git revert` crée un nouveau commit qui annule les modifications introduites par un commit précédent.

Le commit initial reste dans l'historique, mais ses effets sont inversés, ce qui permet de conserver un historique propre sans réécriture.

---

# Mise en œuvre méthodologique

## M1

La principale différence est que :

- `git merge` conserve l'historique tel quel et ajoute un commit de fusion
- `git rebase` réécrit l'historique en rejouant les commits sur une autre base, ce qui donne un historique plus linéaire

## M2

Une autre méthode est **Git Flow**.

Contrairement à GitHub Flow (simple et basé sur une branche principale), Git Flow utilise plusieurs branches (`main`, `develop`, `feature`, `release`, `hotfix`) pour structurer le développement, ce qui est plus adapté aux projets complexes avec des cycles de release.

## M3

L'objectif d'une **pull request** (ou merge request) est de :

- proposer des modifications avant leur intégration
- permettre une revue de code par les autres membres de l'équipe
- discuter des changements
- valider automatiquement (tests, CI) avant fusion