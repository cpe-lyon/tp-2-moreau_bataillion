# TP 2 - Bash

## Exercice 1. Variables d’environnement

**1.Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur?**
Les commandes tapées par un utilisateur se trouvent dans un des dossiers suivants: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin. Bash explore successivement ces dossiers jusqu'à trouver la commande.

**2.Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans votre répertoire personnel?**
Grâce à la commande *$env* on a accès à la liste des variables d'environnement. On remarque la variable HOME contient le chemin du répertoire personnel.

**3.Explicitez le rôle des variables LANG, PWD, OLDPWD, SHELL et_.**
LANG : indique la langue qui est utilisée par les logiciels et les utilisateurs
PWD : indique l'emplacement du dossier courant
OLDPWD : indique l'emplacement du dossier courant précédent
SHELL : renvoie l'interpréteur shell utilisé : pour nous il s'agit de bash (avec *echo $SHELL* on obtient :*/bin/bash*)
_ : renvoie le dernier argument passé

**4.Créez une variable locale MY_VAR(le contenu n’a pas d’importance). Vérifiez que la variable existe.**
*MY_VAR="bla"*
Pour afficher le contenu de la variable locale : *echo $MY_VAR*
Note : *printenv MY_VAR* ne peut pas fonctionner car MY_VAR est une variable locale, et pas une variable d'environnement.

**5.Tapez ensuite la commande bash. Que fait-elle? La variable MY_VAR existe-t-elle? Expliquez. A la fin de cette question, tapez la commande exit pour revenir dans votre session initiale.**
La commande *bash* crée un nouveau shell. Dans ce shell, MY_VAR n'existe plus : elle n'a pas été créée à ce niveau et c'est une variable locale. *exit* nous permet de rejoindre le shell initial dans lequel MY_VAR est toujours présente. On peut connaître le niveau de son shell actuel grâce à  *echo $SHLVL*.

**6.Transformez MY_VAR en une variable d’environnement et recommencez la question précédente. Expliquez.**
On transforme MY_VAR en variable d'environnement grâce à *export MY_VAR*. Lorsqu'on crée un nouveau SHELL, cette variable est conservée car elle est de configuration globale : elle est présente dans tous les SHELL jusqu'à sa suppression.

**7.Créer la variable d’environnement NOMS ayant pour contenu vos noms de binômes séparés par un espace. Afficher la valeur de NOMS pour vérifier que l’affectation est correcte.**
*export NOMS=Bataillion Moreau* crée une variable d'environnement NOMS qui contient uniquement Bataillion. Il a été considéré que les 2 noms étaient des arguments différents. Il faut mettre des cotes ou des guillemets pour indiquer qu'il s'agit d'un seul argument.

**8.Ecrivez une commande qui affiche ”Bonjour à vous deux, binôme1 binôme2!” (où binôme1 et binôme2 sont vos deux noms) en utilisant la variable NOMS.**
*echo Bonjour à vous deux, $NOMS*

**9.Quelle différence y a-t-il entre donner une valeur vide à une variable et l’utilisation de la commande unset?**
Une variable vide existe mais ne contient rien. La commande unset détruit la variable et son contenu.

**10.Utilisez la commande echo pour écrire exactement la phrase :$HOME =chemin(où chemin est votre dossier personnel d’après bash)**
*echo '$HOME = '$HOME* Les cotes permettent à bash de ne pas interpréter ce qui s'y trouve.


### Programmation Bash
Ajoutez le chemin vers script à votre PATH de manière permanente : 
PATH=$PATH:~/script


## Exercice 2. Contrôle de mot de passe

**Écrivez un script testpwd.sh qui demande de saisir un mot de passe et vérifie s’il correspond ou non au contenu d’une variable PASSWORD dont le contenu est codé en dur dans le script. Le mot de passe saisi par l’utilisateur ne doit pas s’afficher.**
On crée un fichier testpwd.sh que l'on remplie avec le code utile:
#!/bin/bash
PASSWORD="tp"
read -s -p 'Saisissez votre mot de passe : ' mdp
if [ "$mdp" = "$PASSWORD" ]; then
	echo "Le mot de passe correspond"
else
	echo "Le mot de passe ne correspond pas"
fi

On compile avec *chmod u+x testpwd.sh*
On lance le script en appelant *testpwd.sh*


## Exercice 3. Expressions rationnelles

**Ecrivez un script qui prend un paramètre et utilise la fonction suivante pour vérifier que ce paramètreest un nombre réel :**







Notes: Copier VM->session
scp -P 2222 marialice@localhost:script/nom_fichier.sh ~/Documents









