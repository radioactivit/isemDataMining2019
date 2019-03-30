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

N'hésitez pas d'ailleurs à créer un projet. Un projet c'est un ensemble de fichiers et dossiers, toute une arborescence. Et ça inclut l'environnement de travail R (votre session). Si vous travaillez sur plusieurs projets en parallèle, c'est plus pratique de travailler ainsi.

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
- q
- load
- save.image

### Autour des vecteurs

- c (pour concaténer/créer des vecteurs)
- length (pour avoir la taille d'un vecteur)
- unique (pour avoir un nouveau vecteur sans les valeurs en double)
- paste (pour concaténer des chaînes de caractères ou collapser un vecteur)

### Les is. pour savoir si un objet est du bon type

- is.numeric (pour savoir si un vecteur est un numérique ou non)
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
- order
- sort
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

Du coup, tout ce qui est suit correspond à des fonctions (qui pour ne rien gâcher sont vectorielles) :

- `<-`
- `>=`
- `<=`
- `>`
- `<`
- `+`
- `-`
- `/`
- `^`
- `%in%`
- `&`
- `|`

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

Les listes peuvent avoir des clefs nommées (plutôt que 1, 2, 3...)

    myList <- list(prenom="jean",nom="pierre") #pour créer une telle liste
    myList$prenom #pour lire le contenu de la clef prénom
    myList$nom #pour le nom par exemple
    myList[["prenom"]] #pour lire le contenu de la clef prénom également, (autre écriture)
    myList[["nom"]] #pour le nom par exemple

    myList[["prenom"]] <- "jacques" #remplace la valeur contenue dans la clef prénom
    myList[["autreClef"]] <- "jeRajouteUneClef"

Ceci s'applique aussi aux vecteurs mais c'est rarement utile :

    monVecteur <- c(nom="jerome",prenom="julien")

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

### Shiny code de base

Installer la librairie (à faire une seule fois)

    install.packages("shiny")

Charger la librairie

    library(shiny)

Avoir de l'aide sur la fonction runExample

    ?runExample

Lister les exemples disponibles

    runExample()

Lancer le premier exemple

    runExample("01_hello")

Avoir de l'aide sur la fonction runExample

Lancer son propre exemple

```# Define UI for app that draws a histogram ----
ui <- fluidPage(

  # App title ----
  titlePanel("Hello from ISEM 2019!"),

  # Sidebar layout with input and output definitions ----
  sidebarLayout(

    # Sidebar panel for inputs ----
    sidebarPanel(

      # Input: Slider for the number of bins ----
      sliderInput(inputId = "bins",
                  label = "Number of bins:",
                  min = 1,
                  max = 50,
                  value = 30)

    ),

    # Main panel for displaying outputs ----
    mainPanel(

      # Output: Histogram ----
      plotOutput(outputId = "distPlot")

    )
  )
)

# Define server logic required to draw a histogram ----
server <- function(input, output) {

  # Histogram of the Old Faithful Geyser Data ----
  # with requested number of bins
  # This expression that generates a histogram is wrapped in a call
  # to renderPlot to indicate that:
  #
  # 1. It is "reactive" and therefore should be automatically
  #    re-executed when inputs (input$bins) change
  # 2. Its output type is a plot
  output$distPlot <- renderPlot({

    x    <- faithful$waiting
    bins <- seq(min(x), max(x), length.out = input$bins + 1)

    hist(x, breaks = bins, col = "#75AADB", border = "white",
         xlab = "Waiting time to next eruption (in mins)",
         main = "Histogram of waiting times")

  })

}

shinyApp(ui = ui, server = server)
```

### data.table, code de base

Installer et charger la librairie

    install.packages("data.table")
    library(data.table)

cars est une data.frame disponible nativement dans R. Mais ce n'est pas une data.table. On peut la convertir en data.table avec la fonction as.data.table. Cette fonction, nous ne pouvons l'utiliser que par

    carsDt <- as.data.table(cars)

Quelques manipulations

    carsWithSpeedSuperior20 <- carsDt[speed >= 20] #un filtre, on ne veut que les lignes où speed est supérieur ou égal à 20, on obtient une nouvelle data.table
    carsWithSpeedSuperior20[order(-dist,speed)] #on trie la data.table par distance décroissante et speed croissante
    carsWithSpeedSuperior20[,speedMoinsUn := speed - 1] #on rajoute une nouvelle colonne speedMoinsUn valant speed - 1. On rappelle que le - est une opération vectorielle et que le 1 est recyclé autant de fois qu'il y a de lignes dans la data.table

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

## Etude de cas

https://www.kaggle.com/rtatman/lego-database#sets.csv

### Context

LEGO is a popular brand of toy building bricks. They are often sold in sets with in order to build a specific object. Each set contains a number of parts in different shapes, sizes and colors. This database contains information on which parts are included in different LEGO sets. It was originally compiled to help people who owned some LEGO sets already figure out what other sets they could build with the pieces they had.

### Content

This dataset contains the LEGO Parts/Sets/Colors and Inventories of every official LEGO set in the Rebrickable database. These files are current as of July 2017. If you need it to be more recent data, you can use Rebrickable’s API which provides up to date data, and additional features.

### Acknowledgements

This dataset was compiled by Rebrickable, which is a website to help identify what LEGO sets can be built given bricks and pieces from other LEGO sets. You can use these files for any purpose.

### Inspiration

This is a very rich dataset that offers lots of rooms for exploration, especially since the “sets” file includes the year in which a set was first released.

### Précisions

La boîte de jeu Lego

- Un thème = Star Wars, Police, Bateau...
- Un set = une boîte de jeu. Une boîte de jeu a un et un unique thème. Il y a 614 thèmes.

Les briques élémentaires

- Une part = une brique élémentaire (déclinable en plusieurs couleurs, mais la table ne décrit pas ces déclinaisons. Les briques identiques à la couleur près forment une même `part`)
- Une part_categories = une catégorie de brique (Windows and doors, tiles, pneumatics...). Chaque brique élémentaire a une catégorie. Il y a seulement 57 catégories.

Autour des inventaires

- Un inventaire = un ensemble de pièces.
- Une pièce d'un inventaire (Inventory_part) = une brique élémentaire (part), pour un inventaire donné, dans une couleur donnée, avec une quantité donnée.
- Couleur = une couleur. Il y en a 135. Chaque inventory_part a une couleur.

On va ignorer le fichier inventory_sets. Il n'est pas utile à la compréhension.
On va se cantonner à seulement certains sets :

On va ignorer les sets qui ont plusieurs inventories (plusieurs versions) ou bien qui n'ont pas d'inventories du tout. Ca concerne très très peu d'entrées.
On va ignorer les sets dont la propriété num_parts ne vaut pas la somme des inventory_parts relatives à leur inventory (penser à multiplier par la quantité de chaque inventory parts).

Exemples

```
library(data.table)
inventories <- fread("lego/inventories.csv")
inventory_parts <- fread("lego/inventory_parts.csv")
inventory_sets <- fread("lego/inventory_sets.csv")
sets <- fread("lego/sets.csv")

setsWithoutInventory <- sets[!(set_num %chin% inventories$set_num)] # %in% est un opérateur vectoriel qui pour chaque élément du vecteur de gauche vérifie que l'élément est bien présent dans le vecteur de droite. Le ! est un opérateur qui sur un vecteur de booléens prend sa négation (donc chaque FALSE devient un TRUE et vice versa. Les NA restent des NA).

#Ici on merge inventory_pars avec inventories inventories[T] permet de dupliquer la data.table inventories (car on va rajouter des colonnes à cette data.table dupliquée mais on ne veut pas altérer la data.table initiale). Pour merger deux data.table, ils doivent avoir le même nom de clef, ici on a choisi inventory_id
mergeInventoryPartsAndInventories <- merge(inventory_parts,inventories[T][,inventory_id := id][,id := NULL],by="inventory_id")

#Ici, sur notre mergeInventoryPartsAndInventories, on groupe par set_num (venu de inventories qu'on a mergé) et on somme les quantités. On merge avec les sets pour comparer les quantités qui sont dans sets et les quantités obtenus par sommation des quantités de chaque pièce. V1 représente la somme des quantités. On devrait trouver V1 == num_parts en théorie, mais la théorie rejoint rarement la pratique !
#Histoire que l'histoire soit cohérente, on ne va garder que les sets cohérent.
setsThatWeMustExclude <- merge(mergeInventoryPartsAndInventories[,sum(quantity),by="set_num"],sets[,c("num_parts","set_num")],by="set_num")[V1 != num_parts]
```

Si on résume notre modèle simplifié :

Une boîte de jeu a un inventaire.
Une boîte de jeu a un thème.
Un inventaire a plusieurs inventory_parts.
Chaque inventory_parts est la répétition d'une pièce, dans une couleur et dans une certaines quantités (pensez au petit livrer qui accompagne une boîte de jeu et qui décrit son contenu).
Chaque pièce a une catégorie.

### Questions

How have the size of sets changed over time?

What colors are associated with witch themes? Could you predict which theme a set is from just by the bricks it contains?

What sets have the most-used pieces in them? What sets have the rarest pieces in them?

Have the colors of LEGOs included in sets changed over time?
