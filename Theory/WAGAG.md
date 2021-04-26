# Travaux de groupe sur le même code

    Voici les outils les plus utilisé pour éviter les incohérences de code dans un projet réalisé en parrallèle par plusieurs personnes.

## Git

### Qu'est-ce que Git?

    Git est un programme de "versionning". Il permet à plusieurs personnes de travailler sur le même projet simultanément en partitionnant les versions du projet tout en gardant les versions initiales à l'abri sur un serveur distant. Cela créera un "arbre de vie" du projet avec des "branches" différentes pour pouvoir les comparer au "tronc" (qui deviendra le projet fini). Cela permet d'éviter les erreurs entre les lignes de codes des différentes versions pendant les "merge" (fusion de branches) ainsi qu'éviter la perte de données.



### Commandes principales du Git?
            
    git add                 |   Versionne le(s) fichier(s) demandé
    git pull                |   Met à jour le dépôt local par rapport au distant
    git commit              |   Valide l'envoi vers le dépot distant
    git push                |   Envoi le commit dans la branche donnée
    git clone               |   Récupére le dépôt distant
    git diff                |   Compare les versions
    git status              |   Informe sur les versions
    git log                 |   Liste les "commits" dans le dépôt ainsi que les modifications effectuées

### QCommandes d'annulation

    git reset -hard HEAD    |   Annule les changements effectués depuis le dernier "commit"
    git reset -hard HEAD^   |   Supprime le dernier "commit" (répétable)
    git revert commit       |   Restaure le dépôt tel au'il était lors du dernier "commit"
                                        (Après que toutes les modifications soient "commit")

### Commandes de gestion des "branches"

    git branch nom          |   Crée une nouvelle "branche" nommée "nom"
    git branch              |   Liste les "branche(s)" présente(s) dans le dépôt
    git checkout <nom>      |   Change de "branche" (après avoir "commit" ou annulé tout les changements)
    git merge <nom>         |   Fusionne la "branche" courante avec la "branche" nommée(debug & "commit" pour finaliser)

### Récupérer et fusionner une branche d'un collaborateur sur vle dépot local?

    git remote add nom1 git://github.com/exemple
    git fetch nom1
    git merge Nom1/master

    La première commande crée un alias qui fait pointer "nom1" vers l'adresse du dépôt. Ça permet d'éviter d'avoir à taper l'adresse complète à chaque fois. La deuxième commande récupère les changements que bob a effectués. La troisième commande fusionne les changements de "nom1" avec votre branche courante. (la deuxième et troisième commande équivalent à la seule commande

        git pull nom1

    après avoir créé l'alias)

## GitHub