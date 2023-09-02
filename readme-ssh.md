# Comment se connecter à GitHub en SSH sous Windows ?

Si vous utilisez Windows comme système d'exploitation, voici comment vous pouvez vous connecter à GitHub en utilisant SSH :

## Étape 1 : Ouvrir Git Bash

1. Ouvrez Git Bash ou un terminal si vous avez déjà installé "Git for Windows". Si vous ne l'avez pas encore installé, vous pouvez le télécharger et l'installer à partir de [Git for Windows](https://gitforwindows.org/).

## Étape 2 : Configuration de votre compte GitHub

2. Collez la commande suivante dans votre terminal, en remplaçant `<votre-adresse-email>` par votre adresse e-mail GitHub :
   ```shell
   git config --global user.email "<votre-adresse-email>"
   ```

## Étape 3 : Initialiser le dépôt local

1. Assurez-vous que votre projet local est un projet Git. Si ce n'est pas le cas, vous pouvez l'initialiser avec la commande suivante (assurez-vous d'être dans le répertoire de votre projet) :

   ```shell
   git init
   ```

   Remarque : Il existe plusieurs façons d'initialiser un projet local avec Git, mais dans cet exemple, nous utilisons la commande ```git init``` pour créer un nouveau dépôt Git local.


2. Ajoutez vos fichiers pour les préparer à la validation :
   ```shell
   git add --all
   ```

   Remarque : Cela ajoutera tous les fichiers modifiés, non suivis et supprimés au "staging area". Le "staging area" permet de sélectionner et de préparer les modifications que vous souhaitez inclure dans votre prochain commit. Assurez-vous d'exécuter cette commande depuis la racine de votre projet si vous souhaitez ajouter tous les fichiers et sous-répertoires.

4. Validez vos modifications avec un message descriptif :
   ```shell
   git commit -m "Ajout des fichiers initiaux"
   ```

## Étape 4 : Ajouter le dépôt distant

3. Utilisez la commande suivante pour ajouter le dépôt distant de GitHub à votre projet local (assurez-vous d'être dans le répertoire de votre projet) :
   ```shell
   git remote add origin git@github.com:votre-nom-utilisateur/votre-projet.git
   ```
   Remplacez `<votre-nom-utilisateur>` par votre nom d'utilisateur GitHub et `<votre-projet>` par le nom de votre projet sur GitHub.

## Étape 5 : Générer vos clés SSH

4. Générez vos clés SSH privée et publique en utilisant la commande suivante (remplacez `<votre-adresse-email>` par votre adresse e-mail GitHub) :
   ```shell
   ssh-keygen -t ed25519 -C "<votre-adresse-email>"
   ```

   Cette commande vous demandera éventuellement de spécifier un nom de fichier pour stocker les clés. Par défaut, il utilisera "id_ed25519" et les sauvegardera dans le répertoire "C:\Users\<votre-nom-utilisateur>\.ssh\".

## Étape 6 : Ajouter votre clé SSH publique à GitHub

5. Copiez le contenu de votre clé SSH publique. Vous pouvez utiliser la commande suivante pour afficher le contenu de la clé dans Git Bash :
   ```shell
   cat ~/.ssh/id_ed25519.pub
   ```

6. Allez sur [GitHub Settings SSH](https://github.com/settings/ssh/new) et collez la clé SSH publique que vous avez copiée précédemment.

## Étape 7 : Vérifier la connexion

7. Pour vérifier que votre connexion SSH fonctionne correctement, utilisez la commande suivante pour tester votre connexion à GitHub :
   ```shell
   ssh -T git@github.com
   ```

   Vous devriez voir un message de confirmation indiquant que vous êtes authentifié avec succès.

## Étape 8 : C'est terminé !

Vous êtes maintenant prêt à travailler avec votre dépôt GitHub en utilisant SSH. Vous pouvez pousser vos modifications vers GitHub en utilisant la commande suivante :

```shell
git push -u origin master
```

Félicitations ! Vous pouvez désormais collaborer sur vos projets GitHub en toute sécurité avec SSH.
