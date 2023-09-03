# Comment réaliser un Pull Request avec GitHub ?

## Créer une nouvelle branche

Créez une nouvelle branche nommée "testing" avec la commande suivante :

```bash
$ git branch testing
```

### Voir les logs

Affichez les logs des commits en utilisant cette commande pour avoir un aperçu de l'historique :

```bash
$ git log --oneline --decorate
```

### Basculer sur une branche "testing"

Passez à la branche "testing" avec la commande `git checkout` :

```bash
$ git checkout testing
```

### Ajouter un fichier puis commiter

Ajoutez un fichier, par exemple "readme-pull-request.md", puis effectuez un commit en ligne de commande (vous pouvez également utiliser un IDE tel qu'IntelliJ) :

```bash
$ vim readme-pull-request.md  # Utilisez l'éditeur de texte de votre choix
$ git commit -a -m 'Ajout du fichier readme-pull-request.md'
```

### Intégrer la branche au dépôt distant

Pour intégrer la branche "testing" dans le dépôt distant, utilisez la commande `git push`. 
L'option `-u` indique à Git de créer toutes les informations nécessaires pour rendre la branche traçable. 
Vous devez spécifier le nom du dépôt distant (par défaut, il se nomme "origin") et le nom de la branche :

```bash
$ git push -u origin testing
```

### Créer un Pull Request sur GitHub

Rendez-vous sur le site GitHub et suivez ces étapes pour créer un Pull Request :

1. Cliquez sur le bouton "New Pull Request".

   ![img.png](img.png)

2. Effectuez vos modifications dans le fichier "readme-pull-request.md" via l'interface web de GitHub.

### Mettre à jour la branche locale

En local, mettez à jour votre branche avec les changements effectués sur GitHub en exécutant les commandes suivantes :

```bash
$ git fetch
$ git merge
```

### Modifier le contenu du fichier

Modifiez la ligne du le fichier "readme-pull-request.md" :

```
une ligne supplémentaire ajoutée ici via l'interface web de GitHub
```

par :

```
une ligne supplémentaire ajoutée dans le fichier readme-pull-request.md via l'interface web de GitHub
```

### Effectuer un nouveau commit et push

Effectuez un nouveau commit avec les modifications :

```bash
$ git commit -a -m '3ème mise à jour du fichier readme-pull-request.md'
```

Puis, poussez les modifications vers le dépôt distant :

```bash
$ git push
```

### Valider les changements sur GitHub

Du côté de GitHub, après avoir validez les changements, vous obtiendrez un écran équivant à ceci :

![img_1.png](img_1.png)

Et voilà, vous avez créé un Pull Request avec succès en utilisant GitHub !
