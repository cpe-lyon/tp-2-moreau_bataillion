# TP 2 - Bash

## Exercice 1. Variables d’environnement

**1.Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur?**
Les commandes tapées par un utilisateur se trouvent dans un des dossiers suivants: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin. Bash explore successivement ces dossiers jusqu'à trouver la commande.

**2.Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans votre répertoire personnel?**
Grâce à la commande *$env* on a accès à la liste des variables d'environnement. On remarque la variable HOME contient le chemin du répertoire personnel.

**3.Explicitez le rôle des variables LANG,PWD,OLDPWD, SHELLet_.**




