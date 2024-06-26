# Cryptanalyse de chiffrements
### Crédit
Projet IN200 2023 de l'UVSQ

Emma CLUZET

## Utilisation du programme

Le programme doit crypter des messages en ayant une clé de chiffrement donnée. Plusieurs fonctions encryptage et décryptage différentes sont utilisées. 

Il y a donc 8 fonctions chiffrement et déchiffrement qui prennent en entrée une chaîne de caractères et la clef qui renvoie le chiffré. Ainsi que des fonctions qui prennent en entrée un chemin dans l'ordinateur contenant le chemin du fichier contenant un texte à chiffrer ou à déchiffrer.

De plus à partir d'un texte chiffré, sans connaissance de la clef, le programme doit retrouver une partie ou toute la clef et/ou le message inital.
Pour cela, il va falloir manipuler des chaînes de caractères. On laisse la possibilité à l’utilisateur de supprimer les espaces ou les caractères spéciaux et de chiffrer un texte écrit dans un fichier *.txt* qui se situerait n’importe où dans l’ordinateur. Ou bien généraliser le code de César ou le chiffre de Vigenère à des alphabets plus grands.

Puis nous avons une fonction qui permet de retrouver le message crypté par les fonctions précédentes sans connaître la clé de déchiffrement. Il va donc tester toutes les possibilités (force brute) et l'utilisateur pourra déterminer quel est le résultat le plus probant.


## Le code César

Le  code de César est issu d'un décalage de 3 lettres dans l'alphabet pour créer une clé de chiffrement. Ici la fonction traite les espace puis récupère l'indice de la lettre pour la stocker dans une variable i en y ajoutant le décalage. Si ce dernier est supérieur à 25, on calcule le reste de la division que l'on stocke dans "i". On ajoute à la variable *texte_chiffre* la lettre avec son indice incrémenté.

Pour déchiffrer le message choisi, le programme traite aussi les espaces puis les lettre en soustrayant le décalage. Si ce dernier est supérieur à 25, on calcule le reste de la division que l'on stocke dans *"i"*. On ajoute la lettre avec son indice décalé à la variable *texte_chiffre* .


## Substitution monoalphabétique générale

Une substitution monoalphabétique est un cryptage issus d'une clé aléatoire unique. 

La fonction génère une clé aléatoire avec la méthode *"shuffle()"* et retourne une "liste copie" de l'alphabet. Une fois la clé obtenue on peut commencer à crypter un message.

La fonction qui encrypte parcourt l'entièreté des caractères du texte afin de vérifier si ils font parti de l'alphabet (majuscule et minuscule). On récupère son indice afin de trouver sa substitution dans la clé et on le remplace. Si le caractère n'est pas alphabétique la fonction le réecrit dans sa forme originale dans le nouveau texte. 

Pour le déchiffrement on réitère le programme en prenant l'indice du caractère de la clé pour trouver quel caractère il substitue.


## Chiffre de Vigenère

Le chiffrement de Vigenère est une méthode de cryptage par subtitution polyalphabétique. Elle utilise la table de Vigenère qui est créée en décalant à chaque ligne, chaque lettre vers la droite d'une position, jusqu'à ce que l'alphabet complet soit écrit.
Ainsi chaque ligne contient une permutation complète et différente de l'alphabet.
Pour déchiffrer un message, il faut connaitre la clé utilisée qui déchiffre à l'aide du tableau en trouvant la lettre correspondante dans la colonne correspondante à la lettre de la clé. Pour cela on cherche la lettre de la clé sur la première ligne du tableau, puis on suit la colonne verticale jusqu'à la lettre chiffrée. La lettre correspondante dans la ligne de la lettre de la clé est la lettre déchiffré.
Si la clé est trop courte, on la répète autant de fois que nécessaire.

## Limites

Nous avons deux fonctions (une pour césar et une en fréquence). Elles sont indépendantes du code et l'une de l'autre et nous n'avons pas eu le temps de les tester sur le code complet.
