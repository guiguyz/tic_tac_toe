# Une partie de Tic-Tac-Toe :

Le point positif de ce projet pourrait être qu'il sera construit sans aucune autre bibliothèque que numpy. numpy étant irremplaçable pour les méthodes de manipulation matricielle soignées dont il peut vous équiper avec la vitesse du c++.

Vous pouvez cloner le repo, le bifurquer ou faire ce que vous voulez, mais jetez un oeil à la documentation ajoutée au code.

J'ai écrit les attentes au début du cahier. Si cela vous convient, essayez de l'essayer ou au moins de l'exécuter, si rien ne marche pour vous, vous pouvez demander ce que vous n'avez pas compris dans les commentaires sur github.

J'ai adopté une approche orientée objet car je pensais qu'il pouvait y avoir une synergie entre la programmation orientée objet et les entités que nous devons modéliser. Si vous trouvez les commentaires de code ennuyeux, veuillez utiliser un IDE qui peut vous aider à les faire taire facilement, je sais par exemple que PyCharm a une sorte de support. La plupart des bribes semblent énormes, mais là encore, c'est parce qu'elles sont fortement commentées. Toutes les méthodes de classe, en moyenne, sont de 12 à 14 lignes de code.

# Installation

```
git clone git@github.com:AmreshVenugopal/tic_tac_toe.git
pip install numpy
```

C'est la seule dépendance dont vous auriez besoin !

# Utilisation

```
python train.py


> 'Enter the number of epochs for training
> 10000
```
Vous pouvez consulter les informations de débogage si vous le définissez dans votre shell :
```
export ENVIRONMENT=DEBUG.
```


### Étape 1

Ce que nous essayons de modéliser, c'est un tableau de tic-tac-toe. Le moins que nous ayons à faire est donc de le construire :

-  Il devrait avoir une structure de données qui représente un tableau tic-tac-toe.

-  Elle doit permettre l'ajout du symbole "X" ou "O" dans le tableau.

-  Il devrait pouvoir déclarer un gagnant, au cas où il y en aurait un.

- Cela signifie qu'il doit pouvoir calculer si une ligne, une colonne ou une diagonale a les mêmes valeurs partout.

- Le constructeur s'occupe des points (1), (2) et crée de la place pour rendre possible le point (3), alors commençons par cela :

- Créez la propriété du tableau, et mettez-le en place avec une matrice 3x3 pleine de zéros, nous allons avancer avec une matrice comme structure de données pour représenter le tableau tic-tac-toe.

-  Établir des relations entre les symboles à utiliser sur les tableaux avec des nombres pour faciliter le calcul du gagnant.

- Attribuer les symboles à un joueur et à un bot.

- Initialisez un gagnant à None car personne n'a encore gagné !

### Étape 2

-  Après avoir mis en place notre tableau, nous avons besoin de moyens pour jouer. Ne vous inquiétez pas trop de la quantité de code, sur les trois méthodes que vous voyez, deux sont juste des enveloppes autour de la première, donc, c'est seulement la première fonction qui a besoin d'attention.

- Si un joueur (robot ou humain) entre son symbole pour le placer quelque part sur le plateau. Insérez plutôt l'entier correspondant. Pour "X", insérez un 2 et pour "O", un 1, sinon, laissez une cellule vide.

-  Dessinez le tableau, afin que nous puissions suivre les performances des joueurs. J'ajouterai le code pour cela dans les sections suivantes. Vérifiez si le symbole qui vient d'être inséré a conduit à une victoire. (code à venir) Étape 3

- Dans la section précédente, le point 3 est assez important. Comment savoir si quelqu'un a gagné la partie ? Revenez sur le point 3 - Attentes. Nous devons trouver un moyen de vérifier si une ligne, une colonne ou une diagonale a la même valeur que le dernier symbole inséré, dans l'ensemble du jeu.

### Étape 3.1

Couvrons d'abord la diagonale, car elle a moins de code et certains des concepts seraient déjà couverts, donc moins à dire dans les autres parties. Avant que vous ne vous énerviez avec le code, laissez-moi vous dire que cette section ne fait pas grand-chose non plus. Les deux dernières fonctions sont presque identiques, à l'exception de l'étape d'augmentation de la variable d'itération.

Dans la méthode element_diagonal_has_same_value(self, item, item_x, item_y), nous vérifions si le dernier symbole du tableau se trouve également sur la diagonale gauche ou droite.

### Étape 3.2

Accrochez-vous, encore plus de code ! Bien que j'aie fait de mon mieux pour être clair dans les recommandations du code, je peux comprendre que jusqu'à présent, cela aurait été vraiment accablant. Je sais exactement ce que l'on ressent, parce que, lorsque j'ai essayé pour la première fois, c'est ce que j'ai ressenti aussi. Le mieux que je puisse suggérer est de faire une pause et d'essayer par vous-même. Cela vous aidera à vous connecter ou, mieux encore, à trouver des moyens plus efficaces de faire la même chose.

Cette étape est une branche de l'étape 3 où nous devions déterminer si le jeu avait un gagnant. Cette étape permet de déterminer si certaines des lignes ou des colonnes ont les mêmes valeurs tout au long du jeu.

### Étape 4

Pour revenir à l'étape 2, où j'avais laissé de côté les méthodes draw_board et is_winning_move, elles sont maintenant introduites. C'est le dernier extrait de cette session.

La méthode draw_board représente la matrice dans un format de tableau tic-tac-toe convivial en insérant des valeurs dans une chaîne et la méthode is_winning_move identifie un gagnant si la méthode is_game_over retourne True qui a été couvert à l'étape 3.



