Créer une nouvelle branche
```
$ git branch testing
```
voir les logs
```
$ git log --oneline --decorate
```
Pour basculer sur une branche testing
```
$ git checkout testing
```

ajouter un fichier puis commiter (ici en ligne de commande sinon via un IDE comme IntelliJ)

$ vim ajout du fichier readme-pull-request.md
$ git commit -a -m 'ajout du fichier readme-pull-request.md'

Pour intégrer la branche au repository distant, 
il faut utiliser la commande git push. L'option -u indique à git de créer toutes les informations nécessaires pour rendre la branche traçable. Il faut ensuite spécifier le nom du repository 
distant (par défaut, il se nomme origin) et le nom de la branche.
```
$ git push -u origin testing
```

Sur le site  GitHub, on va créer un Pull Request :

![img.png](img.png)

une ligne supplémentaire ajouter ici via l'interface web de GitHub
