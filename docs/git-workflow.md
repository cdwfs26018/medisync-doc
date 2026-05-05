
## Contrainte réseau — Port SSH 22 bloqué

### Problème
Le réseau de l'établissement bloque le port 22 (port SSH par défaut),
ce qui empêche de pousser du code vers GitHub en utilisant SSH normalement.

### Solution
Nous avons utilisé HTTPS à la place de SSH pour communiquer avec GitHub.

### Configuration utilisée
```bash
git remote set-url origin https://github.com/cdwfs26018/medisync-doc.git
```

Cette commande change l'URL du dépôt distant de SSH vers HTTPS,
contournant ainsi le blocage du port 22.



## Questions techniques

### T1
Le protocole de communication utilisé en standard par le client Git est SSH (Secure Shell).

### T2
Le protocole utilisé en secours est HTTPS (HyperText Transfer Protocol Secure), notamment lorsque SSH n’est pas disponible (par exemple si le port 22 est bloqué).

### T3
Oui, il est possible de synchroniser un dépôt local avec plusieurs dépôts distants.

Cela se fait avec la commande :
git remote add <nom> <url>

Exemple :
git remote add origin https://github.com/user/repo.git  
git remote add backup https://gitlab.com/user/repo.git

Cela permet de pousser et récupérer du code depuis plusieurs dépôts.

### T4
La commande git revert ne supprime pas le commit.

Elle crée un nouveau commit qui annule les modifications du commit précédent.  
L’historique est conservé, ce qui rend cette méthode sûre en travail collaboratif.

---

## Questions méthodologiques

### M1
La principale différence entre git merge et git rebase concerne la gestion de l’historique.

git merge conserve l’historique complet et crée un commit de fusion.  
git rebase réécrit l’historique pour obtenir une suite de commits linéaire sans commit de fusion.

### M2
Une autre méthode de gestion de branches est Git Flow.

Git Flow utilise plusieurs branches longues :
- main
- develop
- feature
- release
- hotfix

Elle est plus structurée et plus complexe que GitHub Flow, qui est plus simple et repose principalement sur une branche principale et des branches de fonctionnalités.

### M3
L’objectif d’une Pull Request (ou Merge Request) est de permettre aux membres de l’équipe de :

- relire le code
- discuter des modifications
- garantir la qualité du code
- valider les fonctionnalités avant intégration dans la branche principale

Cela améliore la collaboration et limite les erreurs.