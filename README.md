# (Up in the) R

## Qu'est-ce que R ?

`R` est un langage de programmation.

Il est orienté statistiques : il inclut un ensemble d'outils, fonctions, façons de penser qui aident dans ce domaine.

Il est nativement vectoriel : il permet de réaliser une même opération sur un `tableau` (vecteur) de valeurs en même temps.

## Que doit-on installer pour s'en servir ?

On va utiliser `RStudio`.

`RStudio` est un IDE (Integrated Development Environment), c'est-à-dire un outil qui nous aide au développement (plus qu'un éditeur de texte tout simple comme le bloc note par exemple).

Pour fonctionner, RStudio a besoin que R soit installé sur l'ordinateur.

Url de téléchargement de R : https://cran.rstudio.com/
Url de téléchargement de RStudio : https://www.rstudio.com/products/rstudio/download/#download

## Lancement de R en ligne de commande

Lancer l'application `Terminal` sous Mac ou `Powershell`/`CMD` sur Windows.

Bienvenue sur la ligne de commande.

Taper simplement `R` puis tapez `Entrée`.

Vous y voilà, vous êtes dans une console R. Vous pourriez développer tous vos projets ici.

Par exemple déclarer une variable a, une variable b et demander à R de les sommer.

    a <- 5
    b <- 12
    a + b

Essayez, vous serez bluffé par les capacités de R !

Même si on pourrait poursuivre directement dans la console, on va s'en passer et directement lancer l'application RStudio qu'on vient d'installer, ce sera plus confortable.

## Lancement de RStudio

Au lancement de RStudio, notre environnement de développement intégré, on distingue plusieurs zones :

- La console (ça doit vous faire penser à ce qu'on a lancé dans la section précédente)
- Une zone `Environment` en haut à droite où le contenu de votre envionnement est listé. Ceci correspond à toutes les variables que vous avez déclarées et à leurs valeurs respectives.
- Une zone en bas à droite avec un explorateur, les packages disponibles, les courbes que vous auriez générées (...)

On va faire apparaître une quatrième zone, généralement en haut à gauche (la console va descendre en bas à gauche). Pour ce faire, on va créer un nouveau fichier R. File => New => New R Script.

Dans un fichier R Script, on peut tout simplement écrire du code R. Une fois qu'on en est satisfait, on peut l'évaluer dans la console. Pas besoin de copier coller, il suffit de cliquer sur `Source` (Source the content of the active document).

C'est comme si on avait écrit tout le code dans la console.
On peut aussi envoyer dans la console seulement une zone du code en la surlignant et en cliquant sur `Run`.

TODO:

1. Déclarer dans la console les variables a et b comme dans l'exemple précédent. Les voir apparaître dans la zone Environment
2. Déclarer dans le fichier R script une variable c valant 19. Constater qu'on voit aussi la liste des variables dans notre zone Environment
3. N'hésitez pas à enregistrer votre R Script quelque part sur votre ordinateur et à le sauvegarder régulièrement.

## Notion de variable

On dit qu'on `affecte` une valeur à une variable.

`a <- 5` revient à affecter la valeur `5` à la variable `a`

On peut affecter une seule valeur à la fois à une variable.

Mais on peut réaffecter autant de fois qu'on veut une variable.

    a <- 5
    a <- 14
    a <- 22

Il est souvent préférable d'affecter une valeur à une variable une seule fois. On minimise les effets de bord possible.

## Les types primitifs

R inclut les types primitifs qui suivent :

- les entiers (integer)
- les "nombres flottants" (double)
- les chaînes de caractères (character (souvent string dans d'autres langages de programmation))
- les booléens (logical (souvent boolean dans d'autres langages de programmation)
- les complexes (complex)

Même quand on a l'impression d'affecter un type primitif à une variable, on affecte en fait à la variable un vecteur de taille 1 avec pour seule valeur la valeur en question qu'on a choisie.

## Notion de vecteur

Un vecteur a :

- le même type pour tous ses éléments
- une taille

Un vecteur fait penser à un tableau dans d'autres langages (array ou list en Python par exemple) sauf que les éléments sont tous du même type.

L'affectation se fait avec `<-` même si = marche aussi. <- est souvent préféré. `c` est ici une fonction permettant de concaténer. Ici, elle permet de concaténer trois vecteurs (le vecteur de taille 1 contenant la valeur 5, le vecteur de taille 1 contenant la valeur 10 et enfin le vecteur de taille 1 contenant la valeur 14) afin d'en former un quatrième (a).

    a <- c(5,10,14)

On peut accéder aux éléments d'un vecteur comme ceci :

    a[1] #accéder au premier élément
    a[2] #accéder au deuxième élément

Dans la plupart des langages, les tableaux commencent à l'index 0. En R, ils commencent à l'index 1.

Pour afficher un vecteur ou bien n'importe quoi d'autre, on peut utiliser la fonction `print` ou `cat` avec en paramètre ce qu'on veut afficher

    print(a)

ou

    cat(a)

TODO:

1. Que constate-t-on comme différence entre les appels des deux fonctions cat et print ?

2. On peut avoir la taille d'un vecteur a en faisant :

```
length(a)
```

Tester la fonction length sur vos exemples.

3.  Que dit R quand on affecte à b cette valeur ?

```
b <- c(5,10,14,"hello")
```

R a-t-il accepté cela ? b est-il bien un vecteur ? Un vecteur de quels types ?

4. `TRUE` et `T` ainsi que `FALSE` et `F` correspondent aux booléens. Déclarez un vecteur de booléen.

5. Faites

```
vv <- 52
```

vv est-il un vecteur ? De quelle taille ?

6. Faites

```
a + vv
```

Que se passe-t-il ? + est un opérateur vectoriel.

7. Testez avec -, /, \*, ^. Essayez de taper des expressions complexes du type :

8. Pour une range de nombres entre 1 et 100 INCLUS qu'on peut générer comme suit :

```
myRange <- 1:100
```

Comment écririez-vous : je veux un vecteur avec les nombres de 1 à 100 PLUS les nombres de 101 à 200 PLUS 14 MULTIPLIE PAR 3 DIVISE PAR 5 A LA PUISSANCE 6.

9. Etudiez la fonction paste en tapant `?paste` dans la console. Que fait-elle ? Et si on ne veut pas de séparateur. Testez la propriété collapse.

## Comment avoir de l'aide dans RStudio

Il suffit de préfixer par `?` le nom de notre fonction ! Très pratique.

```
?paste
?collapse
?c
```

Bien évidemment, pour avoir de l'aide, on saisira aussi ses problèmes sur Google, en anglais, histoire de tomber sur quelqu'un qui a le même problème que nous !

## Fonctions fréquemment utilisées

### Pour avoir des informations sur l'environnement

- ls (pour lister les éléments contenus dans la session)
- print (et cat, pour afficher l'élément donné en paramètre)
- getwd (pour avoir le répertoire de travail courant, utile pour récupérer un fichier ou sauvegarder un fichier ou une session par exemple)
- rm (pour supprimer une variable)

### Autour des vecteurs

- c (pour concaténer/créer des vecteurs)
- length (pour avoir la taille d'un vecteur)
- distinct (pour avoir un nouveau vecteur sans les valeurs en double)

### Les is. pour savoir si un objet est du bon type

- is.numeric (pour savoir si un vecteur est un numérique ou non)
- paste (pour concaténer des chaînes de caractères ou collapser un vecteur)
- is.integer
- is.character
- is.vector
- is.list
- is.data.frame
- ...

### Les as. pour convertir un objet vers un autre

- as.character (pour convertir un vecteur, par exemple de nombres, en un vecteur de chaînes de caractères)
- as.numeric
- as.vector
- as.list
- ...

### Quelques fonctions statistiques

- sum
- max
- min
- mean (moyenne)
- sd (écart-type)
- median (médiane)
- quantile (quartiles, déciles...)
- ...

### Autour des packages externes

- install.packages
- library
- ...

### Autre

- return (qui est une fonction, ce qui est très rare et n'est pas le cas dans la plupart des langages de programmation)
- date

### Tout est fonction !

En R, tout ou presque est une fonction.

Même `<-` qui est une fonction prenant deux paramètres ! Essayez par vous-mêmes de l'utiliser :

    `<-`(b,1022)

## Notion de session

Faites

    save.image()

Ceci va sauvegarder votre session. Vous aviez plusieurs vecteurs, vous vous souvenez ?

Faites

    q()

Puis quittez sans sauvegarder la session sans sauvegarder (on vient de sauvegarder !). Votre RStudio va se fermer. Vous auriez pu de la même façon fermer tout simplement RStudio. Sauvegardez bien vos scripts !

Relancer RStudio

Faites

    ls()

Pour lister tous les objets de votre session. Vos variables sont-elles présentes ?

Quand vous avez fait `save.image()` vous avez demandé à créer un fichier `.RData` (juste une extension, pas de nom) avec votre session.

Si vous faites `save.image("monSuperFichier.RData")` vous créerez un fichier `monSuperFichier.RData` (testez pour voir) et ce fichier contiendra votre session. Vous pouvez par exemple partager ce fichier à un collègue, il pourra récupérer tous les objets que vous aviez dans votre session.

Si vous devez chargez une session portant le nom "monSuperFichier.RData", vous pouvez faire

    load("monSuperFichier.RData")

Par défaut, lorsqu'on lance RStudio, la session R va charger le contenu du fichier .RData qui est à l'endroit (working directory qu'on peut avoir en faisant getwd()) où est lancée la session.

## Autres types

- matrices (matrix) (tous les éléments ont le même type, mais on peut avoir des lignes et des colonnes, pas seulement une dimension comme avec un vecteur)

```
matrix(0,10,12)
```

Ici on déclare une matrice avec 10 lignes et 12 colonnes remplie de 0

- listes (list) (on peut mettre des éléments de différentes natures. On peut avoir une liste avec pour premier élément un vecteur de nombres, pour deuxième élément une liste, pour troisième élément une matrice)

```
myList <- list(c(12,14),list(c("test")),matrix(0,10,12))
```

- array (matrice mais pouvant avoir plus de deux dimensions)

- data.frame (matrice mais avec pour chaque colonne un type pouvant être différent, une data.frame est une liste de vecteurs)

Les `fonctions` sont des types à part entière.

## Packages externes

R est un langage très riche. Une foultitude de package tiers existent. La communauté est très dynamique et généreuse.

On installe un package en faisant

    install.packages("nomDuPackageEntreGuillemets)

On load un package installé dans notre environnement en faisant

    library(nomDuPackageSansGuillemetsMaisAvecLesGuillemetsCaMarcheAussi)

TODO:

1. Installer le package Shiny et faire fonctionner l'exemple proposé
2. Installer le package data.table et faire fonctionner l'exemple
3. Constater qu'une data.table est une data.frame. On parle d'héritage (en programmation orientée objet)

## Créer votre propre fonction

On a utilisé beaucoup de fonctions mais on peut bien sûr en créer.

Ici, on définit une fonction :

    direBonjour <- function() {
        print("Bonjour")
    }

Et là, on l'appelle, elle ne prend aucun paramètre

    direBonjour()

On déclare une fonction prenant un paramètre

    direBonjourA <- function(prenom) {
        print(paste("Bonjour",prenom))
    }

On l'appelle

    direBonjourA("julien")

TODO:

1. En lisant comment marche la fonction quantile, on veut une fonction appelée `allDeciles` qui prend en paramètre un vecteur de numériques et renvoie un autre vecteur de numériques. Le vecteur retour doit avoir 9 valeurs : le premier décile, le deuxième décile, le troisième décile, le neuvième décile (...)
