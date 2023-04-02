Mini-projets
------------

La partie contrôle continue est évaluée sur un mini-projet. Celui-ci correspond à un TP++, avec la différence que le sujet est moins guidé que pour une séance de travaux pratiques normale. On ne s'attend pas à avoir quelque chose de très performant, un démonstrateur ou une preuve de concept suffit.

## Travail attendu

Un *notebook* Jupyter contenant une démonstration de votre méthode. Vous pouvez mixer à loisir images, diagrammes, code et explications textuelles. L'évaluation se fait sur la qualité de la justification de vos choix d'implémentations (quel algorithme ? pourquoi ?). Le code n'a pas besoin d'être particulièrement efficace mais essayez de faire en sorte d'être lisibles et de commenter.

La quantité de travail attendue est de l'ordre d'une journée maximum (5h à 7h de travail en groupe). Si vous bloquez sur un point, posez des questions.

## Sujets

Il y a pour l'instant huit sujets de projet proposés. Chaque projet est à réaliser en binôme ou en trinôme, de préférence en trinôme. Un projet ne peut être choisi que par un seul groupe.

Vous pouvez aussi proposer un sujet de votre choix mais il doit être validé par l'enseignant *avant* que vous commenciez à travailler dessus.

### Sujet 1 : scanner intelligent

L'objectif de ce mini-projet est d'utiliser une webcam ou un smartphone comme scanner. À partir d'une photo d'une page de texte, on veut automatiquement scanner la page pour en obtenir une version propre, sur fond blanc.

Étapes :
1. détecter les coins de la page,
2. aligner la page,
3. améliorer le contraste ou binariser le texte sur fond blanc,
4. *bonus, si vous avez le temps* : utiliser [TesseractOCR](https://pypi.org/project/pytesseract/) pour automatiquement extraire le texte de la page.

### Sujet 2 : moteur de recherche d'images d'animaux

L'objectif de ce mini-projet est d'implémenter un moteur de recherche d'images par similarité sur une banque d'images d'animaux. On utilisera la base de données [Animal Image Dataset](https://www.kaggle.com/ashishsaxena2209/animal-image-datasetdog-cat-and-panda).

Étapes :
1. calculer des caractéristiques d'images sur les images
2. implémenter une recherche d'image par la méthode des plus proches voisins
3. comparer les performances de différentes caractéristiques
4. *bonus, si vous avez le temps* : calculer les scores de [précision et de rappel](https://fr.wikipedia.org/wiki/Pr%C3%A9cision_et_rappel)

### Sujet 3 : numérisation de sudoku

L'objectif de ce mini-projet est de scanner une grille de sudoku manuscrite pour pouvoir la résoudre automatiquement. À partir d'une photo de la grille, on veut automatiquement détecter toutes les cases et identifier les chiffres qu'elles contiennent.

Étapes :
1. détecter les cases de la grille,
2. séparer les cases remplies et les cases vides,
3. Utiliser [TesseractOCR](https://pypi.org/project/pytesseract/) pour automatiquement reconnaître les chiffres.
4. *bonus, si vous avez le temps* : résoudre automatiquement le sudoku.

### Sujet 4 : floutage de visages en temps-réel

L'objectif de ce mini-projet est de suivre automatiquement un ou plusieurs visages qui se déplacent devant une webcam. Le suivi doit se faire en temps réel (c'est-à-dire au moins 5 fois/seconde pour être fluide). On veut flouter les visages pour « anonymiser » le flux vidéo.

Étapes :
1. améliorer la qualité de l'image
2. appliquer la méthode de Viola et Jones pour détecter le visage
3. flouter automatiquement le(s) visage(s)
4. *bonus, si vous avez le temps*: utiliser une heuristique pour stabiliser le tracking quand on passe d'une image à l'autre

### Sujet 5 : mesure d'objets

L'objectif de ce mini-projet est de pouvoir mesurer les objets présents dans une photo à partir d'un objet de référence (par exemple, une pièce de monnaie dont les dimensions sont connues). On utilisera une approche de segmentation pour séparer les différents objets, l'objet de référence permettra de réaliser une conversion cm <-> pixel. Pour simplifier les choses, on supposera que tous les objets sont dans le même plan (par exemple, posés sur une table).

Étapes :
1. segmenter les objets photographiés
2. retrouver l'objet de référence
3. convertir les tailles des objets en pixel vers des centimètres
4. *bonus, si vous avez le temps*: améliorer la robustesse en utilisant plusieurs objets de référence.

### Sujet 6 : détection des photos floues

L'objectif de ce mini-projet est de quantifier la présence de flou dans une image. On pourra comparer deux méthodes : une méthode basée FFT et une méthode basée gradient.

Étapes :
1. implémenter l'algorithme 1 : variance du Laplacien. On convolue l'image avec le noyau Laplacien et on calcule la variance de l'image filtrée obtenue. Si elle est supérieure à un certain seuil (à déterminer), l'image n'est pas floue.
2. implémenter l'algorithme 2 : on calcule la FFT de l'image. On retire les basses fréquences, on calcule l'amplitude de ce qui reste. Si c'est au-dessus d'un seuil (à déterminer), l'image n'est pas floue. 
3. générer des images floutées et calculer pour chaque méthode la corrélation entre le coefficient obtenu et la quantité de flou réelle.
4. *bonus, si vous avez le temps*: appliquer le détecteur de flou sur un flux vidéo.

### Sujet 7 : version cartoon d'une image

L'objectif de ce mini-projet est de transformer une photo pour lui donner un effet *cartoon* dessiné (voir un exemple [ici](https://dezyre.gumlet.io/images/blog/computer-vision-projects/CartooniseImage.gif?w=1242&dpr=1.0)). Pour ce faire, on combinera un mélange de différentes techniques : détection et renforcement des contours, lissage des couleurs, etc.

Étapes :
1. implémenter une détection de contours sur l'image
2. renforcer les contours en leur appliquant un trait noir semi-transparent
3. lisser les couleurs de l'image en utilisant un floutage ou une stylisation par segmentation
4. *bonus, si vous avez le temps*: appliquer la « cartoonification » en temps réel sur un flux vidéo.


### Sujet 8 : création de panoramas

L'objectif de ce mini-projet est crééer automatiquement des panoramas, par exemple à 360°, en combinant plusieurs photos prises depuis le même point de vue. On pourra utiliser une détection de points d'intérêt (manuelle ou automatique) puis estimer la matrice d'homographie pour passer d'une image à la suivante.

Étapes:
1. implémenter une sélection manuelle d'au moins quatre points d'intérêts
2. implémenter l'estimation de l'homographie pour coller ensemble deux images
3. étendre le programme pour coller ensemble plusieurs images
4. *bonus, si vous avez le temps*: utiliser un algorithme d'extraction automatique des points d'intérêt

Le rendu est à faire sous forme d'un *notebook* Jupyter qui contient :
- le code permettant de tester le démonstrateur,
- des explications textuelles sous forme de mini-rapport.
