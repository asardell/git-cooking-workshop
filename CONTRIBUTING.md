# 🤝 Guide de contribution

Bienvenue dans Git Cooking Workshop !

Ce document explique comment contribuer au livre de recettes, de la création de votre fork jusqu'à la Pull Request (PR).

L'objectif est d'apprendre à collaborer sur un projet avec Git et GitHub, comme dans un projet professionnel ou open source.

## 📋 Sommaire

- [🤝 Guide de contribution](#-guide-de-contribution)
  - [📋 Sommaire](#-sommaire)
  - [1. Choisir une recette](#1-choisir-une-recette)
    - [Règles à respecter](#règles-à-respecter)
  - [2. Créer son fork](#2-créer-son-fork)
  - [3. Créer une branche](#3-créer-une-branche)
    - [Depuis l'interface GitHub](#depuis-linterface-github)
    - [Depuis le terminal](#depuis-le-terminal)
  - [4. Modifier une recette](#4-modifier-une-recette)
  - [5. Vérifier ses modifications](#5-vérifier-ses-modifications)
  - [6. Créer un commit](#6-créer-un-commit)
    - [Bonnes pratiques](#bonnes-pratiques)
  - [7. Publier sa branche](#7-publier-sa-branche)
  - [8. Ouvrir une Pull Request](#8-ouvrir-une-pull-request)
    - [Modèle de description](#modèle-de-description)
  - [9. Participer à une review](#9-participer-à-une-review)
    - [Points à vérifier](#points-à-vérifier)
    - [Commenter une Pull Request](#commenter-une-pull-request)
  - [10. Synchroniser son dépôt](#10-synchroniser-son-dépôt)
    - [Récupérer la dernière version de main](#récupérer-la-dernière-version-de-main)
    - [Rebaser une branche de travail](#rebaser-une-branche-de-travail)
  - [11. Résumé des commandes](#11-résumé-des-commandes)
  - [🎉 Merci pour votre contribution !](#-merci-pour-votre-contribution-)


## 1. Choisir une recette

Explorez le dossier recipes/ et choisissez une recette qui contient une erreur à corriger.

Les erreurs peuvent concerner :

- L'orthographe ou la grammaire.
- Les quantités ou les unités des ingrédients.
- Les étapes de préparation.
- Les temps de préparation ou de cuisson.
- La mise en forme Markdown.

### Règles à respecter

- Corrigez un problème précis.
- Limitez vos modifications au strict nécessaire.
- Ne réécrivez pas toute une recette si une petite correction suffit.
- Ne modifiez pas plusieurs recettes dans une même PR sans raison valable.

## 2. Créer son fork

Un fork est une copie du dépôt original sur votre propre compte GitHub.

1. Ouvrez le dépôt original git-cooking-workshop sur GitHub.
2. Cliquez sur Fork.
3. Sélectionnez votre compte GitHub.
4. Cliquez sur Create fork.

Vous disposez maintenant de votre propre copie du projet.

Vous pourrez y créer des branches et publier vos modifications sans modifier directement le dépôt original.

## 3. Créer une branche

Chaque contribution doit être réalisée sur une branche dédiée.

N'effectuez pas vos modifications directement sur main.

Choisissez un nom explicite, par exemple :

- correction/crepes
- correction/carbonara
- docs/amelioration-recette

### Depuis l'interface GitHub

Dans votre fork :

1. Cliquez sur le sélecteur de branche, généralement affiché avec main.
2. Saisissez le nom de votre nouvelle branche.
3. Créez la branche à partir de main.

### Depuis le terminal

Après avoir cloné votre fork, créez une branche avec

```bash
git switch -c correction/crepes
```

Cette commande crée la branche et vous place automatiquement dessus.

## 4. Modifier une recette

Ouvrez le fichier Markdown de la recette choisie et effectuez votre correction.

Une recette doit rester claire et structurée.

Elle peut notamment contenir :

- Le nom du plat.
- Une courte présentation.
- Le nombre de portions.
- Le temps de préparation.
- Le temps de cuisson.
- La liste des ingrédients.
- Les étapes de préparation.

Conservez la structure existante autant que possible.

## 5. Vérifier ses modifications

Avant de créer un commit, vérifiez ce que vous avez changé.

Dans le terminal, utilisez :

- `git status` pour connaître l'état du dépôt.
- `git diff` pour afficher les modifications effectuées dans les fichiers suivis.

```bash
git status
git diff
```

Après avoir ajouté vos fichiers à l'index, vous pouvez également vérifier les changements qui seront inclus dans le prochain commit avec `git diff --staged`.

Assurez-vous que le diff contient uniquement les modifications attendues.

## 6. Créer un commit

Un commit enregistre un ensemble de modifications dans l'historique Git.

Ajoutez uniquement le fichier concerné, par exemple avec 

```bash
git add recipes/01-crepes/recipe.md
```

Adaptez le chemin au fichier que vous avez réellement modifié.

Créez ensuite votre commit avec 

```bash
git commit -m "Corrige les quantités de la recette des crêpes"
```


### Bonnes pratiques

Un bon message de commit doit être :

- Court et explicite.
- Centré sur une modification précise.
- Facile à comprendre lorsqu'on consulte l'historique.

Évitez les messages trop vagues comme fix, modifs ou test.

## 7. Publier sa branche

Pour publier votre branche sur votre fork GitHub, utilisez

```bash
git push -u origin correction/crepes
```

Remplacez `correction/crepes` par le nom de votre branche.

L'option `-u` associe votre branche locale à la branche distante correspondante. Lors des prochains envois, un simple `git push` suffira généralement.

## 8. Ouvrir une Pull Request

Une Pull Request permet de proposer vos modifications au dépôt original.

Après avoir publié votre branche :

1. Ouvrez votre fork sur GitHub.
2. Cliquez sur Compare & pull request, si le bouton est proposé.
3. Vérifiez que la branche de base est main dans le dépôt original.
4. Vérifiez que la branche source est votre branche de correction dans votre fork.
5. Rédigez une description claire.
6. Cliquez sur Create pull request.

### Modèle de description

Votre Pull Request doit expliquer :

- **Problème :** quelle erreur avez-vous identifiée ?
- **Correction :** qu'avez-vous modifié ?
- **Vérification :** comment avez-vous vérifié votre correction ?

Exemple :

**Problème :** la recette des crêpes indiquait une quantité de lait incohérente.

**Correction :** la quantité a été corrigée.

**Vérification :** j'ai vérifié le diff pour m'assurer que seuls les changements nécessaires étaient présents.

Ne fusionnez pas vous-même votre PR dans le cadre de cet atelier. Le formateur s'occupera du merge après la review.

## 9. Participer à une review

Chaque participant doit relire la Pull Request d'un autre étudiant.

Une review consiste à examiner les modifications proposées et à fournir un retour constructif.

### Points à vérifier

- Le problème décrit est-il réellement corrigé ?
- La correction est-elle cohérente ?
- Les changements sont-ils limités au besoin ?
- La recette reste-t-elle facile à comprendre ?
- Le Markdown est-il correctement formaté ?
- La description de la PR correspond-elle aux changements ?

### Commenter une Pull Request

Dans l'onglet Files changed de la PR :

1. Examinez le diff.
2. Ajoutez un commentaire si nécessaire.
3. Expliquez clairement le problème ou la suggestion.
4. Soumettez votre review.

Vous pouvez approuver la modification si elle est satisfaisante, ou demander des changements si une correction supplémentaire est nécessaire.

Une review doit rester constructive : son objectif est d'améliorer la contribution, pas de juger son auteur.

## 10. Synchroniser son dépôt

Le dépôt original peut évoluer pendant que vous travaillez.

Pour récupérer ses dernières modifications, configurez le dépôt original comme dépôt distant upstream.

Cette configuration se fait une seule fois avec

```bash
git remote add upstream https://github.com/FORMATEUR/git-cooking-workshop.git
```

Remplacez FORMATEUR par le compte GitHub du propriétaire du dépôt original.

Vous pouvez vérifier vos dépôts distants avec

```bash
git remote -v
```

Vous devriez voir :

- origin : votre fork.
- upstream : le dépôt original.

### Récupérer la dernière version de main

1. Récupérez les informations du dépôt original avec
```bash
git fetch upstream
```
2. Placez-vous sur votre branche locale main avec
```bash
git switch main
```
3. Synchronisez-la avec votre fork grâce à
```bash
git pull --ff-only origin main
```
4. Intégrez les modifications du dépôt original avec
```bash
git merge upstream/main
```
5. Publiez la mise à jour sur votre fork avec
```bash
git push origin main
```

Cette séquence permet de mettre à jour votre branche locale main, puis de publier cette mise à jour sur votre fork.

### Rebaser une branche de travail

Si vous avez une branche de travail encore ouverte et que vous souhaitez la mettre à jour à partir de la dernière version du dépôt original :

1. Récupérez les dernières informations avec
```bash
git fetch upstream
```
2. Placez-vous sur votre branche de travail avec
```bash
git switch correction/crepes
```
3. Rebasez-la sur la dernière version de main avec
```bash
git rebase upstream/main
```

En cas de conflit, Git vous demandera de résoudre les fichiers concernés avant de poursuivre le rebase.

**Attention :** si vous avez déjà publié cette branche, un rebase peut réécrire son historique. Il faut alors mettre à jour la branche distante avec précaution. Dans cet atelier, demandez de l'aide au formateur si vous rencontrez cette situation.

Si votre PR a déjà été mergée, vous pouvez simplement repartir de main à jour pour votre prochaine contribution.

## 11. Résumé des commandes

| Commande | Utilité |
|---|---|
| `git clone` | Copier un dépôt sur son ordinateur |
| `git switch -c` | Créer une branche et s'y placer |
| `git status` | Vérifier l'état du dépôt |
| `git diff` | Examiner les modifications |
| `git add` | Préparer les changements pour le commit |
| `git diff --staged` | Examiner les changements préparés |
| `git commit` | Enregistrer un commit |
| `git push` | Publier les commits sur un dépôt distant |
| `git fetch` | Récupérer les informations du dépôt distant |
| `git pull` | Récupérer et intégrer des modifications distantes |
| `git rebase` | Rejouer les commits sur une autre base |

## 🎉 Merci pour votre contribution !

Chaque correction améliore le livre de recettes et permet à chacun de progresser dans l'utilisation de Git et GitHub.

N'hésitez pas à poser des questions, à demander une review et à aider les autres participants.

Bon atelier et bonne cuisine !