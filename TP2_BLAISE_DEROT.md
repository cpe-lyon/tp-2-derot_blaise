# TP 2 - Bash

## Exercice 1. Variables d’environnement


1. Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur?
>Les commandes tapées par l'utilisateur sont sont stockées dans les fichiers liées au PATH, bash va aler dans chacun de ces fichiers successivement jusqu'a trouver la commande : on utilise la commande "printenv PATH" pour les trouver. On obtient alors : /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

2. Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans votre répertoire personnel?
>Si on tape cd sans argument, la valeur de la variable shell HOME est utilisée pour nous ramener a notre dossier personnel.

3. Explicitez le rôle des variables LANG, PWD, OLDPWD, SHELL et _.
>LANG : stocke la langue utilisée sur le système
 PWD : stocke le chemin d'accès au repertoire
 OLDPWD : stocke le chemin d'accès au repertoire visité précédemment
 SHELL : stocke le type de shell utilisé
 _ : stocke le dernier argument envoyé en entrée

4. Créez une variable locale MY_VAR(le contenu n’a pas d’importance). Vérifiez que la variable existe.
>On créé MY_VAR avec "MY_VAR="variable", puis on execute "echo $MY_VAR" pour verifier son existance : on obtient en sortie "variable".

5. Tapez ensuite la commande bash. Que fait-elle? La variable MY_VAR existe-t-elle? Expliquez. A la fin de cette question, tapez la commande exit pour revenir dans votre session initiale.
>La commande bash sert a créer un nouveau shell. Dans ce nouveau shell la variable MY_VAR n'existe plus car c'est une variable locale.

6. Transformez MY_VAR en une variable d’environnement et recommencez la question précédente. Expliquez.
>Pour transformer MY_VAR en une variable d'environnement (= globale), on execute "export MY_VAR="testvar" && printev MY_VAR". Si on recréé un nouveau shell, on peut cette fois ci afficher le contenu le MY_VAR grace a la commande echo car c'est désormais une variable d'environnement.

7. Créer la variable d’environnement NOMS ayant pour contenu vos noms de binômes séparés par un espace. Aﬀicher la valeur de NOMS pour vérifier que l’affectation est correcte. 
>Même principe que la question précédente : on execute "export NOMS='BLAISE DEROT' && printenv NOMS" puis on affiche sa valeur grace a "echo $NOMS" : on obtient en sortie "BLAISE DEROT".

8. Ecrivez une commande qui aﬀiche ”Bonjour à vous deux, binôme1 binôme2!” (où binôme1 et binôme2 sont vos deux noms) en utilisant la variable NOMS. 
>On execute "echo "Bonjour à vous deux, $NOMS !" et on obtient en sortie "Bonjour à vous deux, BLAISE DEROT".

9. Quelle différence y a-t-il entre donner une valeur vide à une variable et l’utilisation de la commande unset?
>

10. Utilisez la commande echo pour écrire exactement la phrase :$HOME =chemin(où chemin est votre dossier personnel d’après bash)
>On utilise un antislash pour afficher $HOME en brut sans afficher le chemin d'accès au repertoire personnel, on execute donc "echo "\$HOME = $HOME".

## Programmation Bash


