# Pour commencer ..
## Installer Github
#### Sur Mac
```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew doctor
```


Accepter d'installer les *Command Line Developper Tools* de Apple si brew vous le propose. Puis installer `git`

```bash
brew install git
```


#### Sur Linux
```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install git
```


#### Sur Windows
Aller sur https://gitforwindows.org/ et l'installer

## Github Desktop
Github desktop peut se montrer pratique pour editer, explorer ou bien gerer les conflits.

# Workflow
Voici une vue rapide des differentes commandes mises en jeux.

```sh
git clone  https://github.com/bxb-space/bxb-space.github.io
cd bxb-space.github.io/
# ! Use git pull if already cloned !

# Edit what you need
git add --all
git commit -m "" # commit message can't be empty btw
git push
```

## Details
### Cloner le repo
On utilise `clone` avec toute simplicitée :
```sh
$ git clone https://github.com/bxb-space/bxb-space.github.io
$ cd bxb-space.github.io/
```

S'il est deja present sur la machine on le met à jour grâce à `pull` :
```sh
git pull origin
```

### Actualiser ses changements
##### Add
Si l'on a ajouté de nouveaux fichiers il faut d'abord utiliser la commande `add` qui prend en argument le chemin du dît fichier.

```sh
$ git add ./nom_du_fichier
```
Pour plus de rapiditée preferez utiliser une des deux commandes :
```sh
$ git add .
# ou :
$ git add --all
```

##### Commit
Un commit sert à enregistrer ses changements : on ne change pas le repo master, mais on renseigne les changements effectués sur notre branche.

Dès lors il sera possible d'effectuer un `push` où la branche master sera mise à jour. C'est à ce moment qu'il sera possible de rencontrer des conflits.

```sh
$ git commit -m "message"
```
On peut visualiser l'historique des commits avec la commande `git log`.



##### Push
Voici le moment où les données sont uploadées sur le repo.

```sh
$ git push
```
###### En cas de conflit :
Imaginons nous qu'une autre personne ait push son commit avant vous. Dans ce cas la git refusera le push :
```
Your branch and 'origin/master' have diverged,
and have 1 and 1 different commit(s) each, respectively.
```
Il faut actualiser son repertoire avec la branche master actuelle grâce à `pull`, qui n'est que la fusion de `fetch` et `merge`.
```sh
$ git pull
```
