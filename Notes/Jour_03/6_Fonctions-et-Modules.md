
---
layout: default
title: Fonctions et Modules
---


****





 Dans cette section, nous allons voir
comment élaborer et appliquer une fonction sous python. Nous menons une discussion générale sur comment utiliser un
module python.



## Fonctions
Simplement définie, une fonction est un bout de programme, un ensemble d’instructions
agencées dans le but de réaliser une ou plusieurs tâches bien définies. On distingue deux
catégories de fonctions sous python, les fonctions prédéfinies et les fonctions écrites par les
utilisateurs.

- Les fonctions prédéfinies sont des fonctions directement intégrées dans la bibliothèque standard du système python.
- Les fonctions-utilisateurs sont écrites soit par l’utilisateur actuel ou par d’autres utilisateurs.

### Quelques fonctions prédéfinies sous python

 - La fonction `print()`: Comme on le sait déjà, la fonction **print()** a pour rôle d'afficher à l’écran les valeurs des objets spécifiés comme arguments:
 ```python
print("Bonjour", "à", "tous")
x=12
print(x)
y=[1, "lundi","12", 5, 3, "valeur test"]
print(y)
```
On peut remplacer le séparateur par défaut (l’espace) par un autre caractère quelconque (ou
même par aucun caractère), grâce à l’argument `sep`:
```python
    print("Bonjour", "à", "tous", sep= "****")
    print("Bonjour", "à", "tous", sep= "")
```    


 - La fonction `input()` : La fonction **input()** permet de donner la main à l'utilisateur afin qu'il saisisse la valeur d'un argument donné:
 ```python
    prenom = input("Entrez votre prénom : ")
    print("Bonjour,", prenom)
 ```
 
 ```python
    print("Veuillez entrer un nombre positif quelconque : ", end=" "  )
    ch = input()
    num = int(ch) # conversion de la chaîne en un nombre entier
    print("Le carré de", num, "vaut", num**2)
 ```   

**NB** : Soulignons que la fonction `input()` renvoie toujours une chaîne de caractères. Si vous
souhaitez que l’utilisateur entre une valeur numérique, vous devrez donc convertir la valeur
entrée (qui sera donc de toute façon de type string) en une valeur numérique du type qui vous
convient, par l’intermédiaire des fonctions intégrées `int()` (si vous attendez un entier) ou `float()`
(si vous attendez un réel).

### Les fonctions définies par l’utilisateur

Pour définir une fonction sous Python, on utilise le mot clé `def ` pour déclarer le nom de la
fonction. La syntaxe générale de définition d’une fonction est la suivante :


        def nomDeLaFonction([paramètre1,paramètre2,...,paramètreN]):
        
            """Documentation de la fonction."""
            
            <bloc_instructions>
            
 Dans la définition d’une fonction, la première chaîne de charactères (appelé docstring) servira de docu-
mentation pour la fonction, accessible de l’interpréteur via p.ex. `help(temp_f2c)`, ou `temp_f2c?` sous
*jupyter*. Elle se doit d’être tout à la fois pertinente, concise et complète. Elle peut également inclure
des exemples d’utilisation.           

#### Définition d'une fonction simple sans argument
L’exemple ci-dessous illustre la définition d’une fonction simple sans argument. Le but de la
fonction est d’afficher les 20 premières valeurs de la table de multiplication par 8.


```python
def tableMultiplication8():
    """
    Le but de la fonction est d’afficher les 20 premières 
    valeurs de la table de multiplication par 8.
    Entree : Aucune
    Sortie : La table de multiplication par 8
    """
    n = 1
    while n <=20 :
        v = n*8
        print(n, 'x', 8, '=', v, sep =' ')
        n = n +1
```

Pour exécuter la fonction `tableMultiplication8()` que nous venons de définir, il suffit de le référencer en indiquant son nom comme suit (n’importe où dans le programme principal).        


```python
tableMultiplication8() # appelle la fonction tableMultiplication8()
```

**** 
<left> <b> <span style="color:brown;">Exercice: </span> </b></left>

Proposer une version de la fonction `tableMultiplication8()` à partir d’une
boucle « for ».
****

#### Définition d'une fonction dont les arguments sont des paramètres
Un paramètre est une variable qui prend une valeur constante. Dans l'exemple précédent, nous
avons élaboré une table de multiplication par 8. Nous pouvons généraliser cette fonction de
sorte que qu’elle puisse renvoyée la table de multiplication de n’importe quel nombre spécifié
comme argument. Ces nombres étant des paramètres, il s’agit alors de définir une fonction
dont les arguments sont les paramètres. Voir l’exemple ci-dessous


```python
def tableMultiplication(base):
    n = 1
    while n <=20 :
        v=n*base
        print(n, 'x', base, '=', v, sep =' ')
        n = n +1
```


```python
tableMultiplication(2) # renvoie la table de multiplication par 2
tableMultiplication(8) # renvoie la table de multiplication par 8
tableMultiplication(11) # renvoie la table de multiplication par 11
```

#### Un ou plusieurs paramètres, pas de retour
Exemple sans l’instruction `return`, ce qu’on appelle souvent une **procédure**. Dans
ce cas la fonction renvoie implicitement la valeur `None` :
    
```python    
def table(base, debut, fin):
"""Affiche la table des <base> de <debut> à <fin>."""
    n = debut
    while n <= fin:
        print(n, ’x’, base, ’=’, n * base, end=” ”)
        n += 1
```

```python
# exemple d’appel :
table(7, 2, 11)
# 2 x 7 = 14 3 x 7 = 21 4 x 7 = 28 5 x 7 = 35 6 x 7 = 42
# 7 x 7 = 49 8 x 7 = 56 9 x 7 = 63 10 x 7 = 70 11 x 7 = 77
```

#### Un ou plusieurs paramètres, utilisation du retour

**Exemple avec utilisation d’un `return` unique :**


```python

def carre(x):
    return x**2

def aireCarre(r):
    return carre(x)

# Saisie du cote et affichage de l'aire
cote = float(input('Cote : ''))
print(”Aire du carre =”, aireCarre(cote))
```


**Exemple avec utilisation d’un return multiple :**
```python
PI = 3.14
def surfaceVolumeSphere(r):
        surf = 4.0 *PI* r**2
        vol = surf * r/3
    return surf, vol
```
```python
# programme principal
rayon = float(input(’Rayon : ’))
s, v = surfaceVolumeSphere(rayon)
print(”Sphère de surface {:g} et de volume {:g}”.format(s, v))
```

### Passage d’une fonction en paramètre

```python
def tabuler(fonction, borneInf, borneSup, nbPas):
    """Affichage des valeurs de <fonction>. On doit avoir (borneInf < borneSup) et (nbPas > 0)"""
    h, x = (borneSup - borneInf) / float(nbPas), borneInf
    while x <= borneSup:
        y = fonction(x)
        print(”f({:.2f}) = {:.2f}”.format(x, y))
        x += h
```

```python
def maFonction(x):
    return 2*x**3 + x - 5
```
```python
tabuler(maFonction, -5, 5, 10)
# f(-5.00) = -260.00
# f(-4.00) = -137.00
# ...
# f(5.00) = 250.00
```

### Définition des valeurs par défaut pour les arguments d’une fonction
Lors de la définition d’une fonction, il est souvent conseillé de définir des valeurs par défaut
pour certain arguments (notamment les arguments optionnels). En définissant les valeurs par défaut pour les arguments d’une fonction, il est possible
d’appeler le programme avec une partie seulement des arguments attendus. Exemples :

```python
   def salutation(nom, titre ='Monsieur'):
        print("Bonjour", titre, nom)
```

La fonction salutation ainsi définie a deux arguments : nom et titre. Une valeur par défaut a été
définie pour l’argument. Ainsi lorsque la fonction salutation est appelée avec seulement
l’argument nom (omettant l’argument), la fonction renvoie la valeur par défaut Monsieur.
Exemple :

```python
   salutation('Dupont') # renvoie Bonjour Monsieur Dupont
```    

Mais lorsque la fonction est appelée avec les deux arguments, la valeur par défaut est ignorée.
Exemple :
En définissant les valeurs par défaut pour les arguments d’une fonction, il est possible
d’appeler le programme avec une partie seulement des arguments attendus. Exemple:
```python
   salutation('Dupont', 'Mademoiselle')
```

<left> <b> <span style="color:brown;"> NB : Les arguments sans valeur par défaut doivent être spécifiés avant les arguments avec les
valeurs par défaut. Par exemple, la définition ci-dessous est incorrecte et renvoie une erreur
lors de l’exécution.</span> </b></left>
```python
   def salutation(titre='Monsieur', nom):
```    


```python
def salutation(titre='Monsieur', nom):
```

### Les fonctions lambda
Une fonction lambda est une fonction anonyme c'est-à-dire une fonction constituée d’un bloc
d’instructions appelable et réutilisable comme une fonction, mais sans nom. Une fonction
lambda est généralement utilisée pour des fonctions très courtes avec peu d’instructions
(nécessitant pas alors d’écrire une fonction classique avec le mot clé def et un appel).

La syntaxe générale de définition d'une fonction lamda est la suivante:

```python
   lambda arg1, arg2,..., argN : bloc instructions(ou formules)
```

L’exemple ci-dessus illustre la défintion d’une fonction lambda.
```python
   lambda x, y : x * y
```    

Notons toutefois que même si la fonction lambda n’est pas définie avec un nom, pour
récupérer la valeur renvoyée, lors de l’appel de la fonction, il faut l’assigner à une nouvelle
variable. L’exemple ci-dessous illustre l’appel de la fonction lambda précédente en prenant x=2
et y=3.
```python
   x = lambda x, y : x * y
   x(2,3)
```


```python
x = lambda x, y : x * y
x(2,3)
```

<left> <b> <span style="color:red;">
Note : Lorsque nous définissons des variables à l’intérieur d’une fonction, ces variables ne sont
accessibles que pour cette fonction elle-même. On dit que ces variables sont des variables
`« locales » ` à la fonction. Mais lorsque les variables sont définies à l’extérieur de la fonction dans
le corps du programme principal. Ces variables sont appelées variables `« globales »`. Le contenu d’une variable globale est visible et accessible à partir de l’intérieur d’une fonction,
mais cette fonction ne peut pas modifier la valeur de la variable.</span> </b></left>


```python
def myFunction():
    p = 20
    print(p, q)
p=15
q=38

print(p, q) # renvoie 15 38
myFunction() # appelle la fonction, renvoie 20 38
print(p, q) # renvoie 15 38
```


```python
Cependant, on peut modifier ce comportement par défaut en permettant à la fonction de
modifier la valeur de la variable globale. Dans ce cas, il faut explicitement définir la variable
comme global à l’intérieur de la fonction. Exemple:
```


```python
def myFunction():
    global p
    p = 20
    print(p, q)
p=15
q=38
print(p, q) # renvoie 15 38
myFunction() # appelle la fonction, renvoie 20 38
print(p, q) # renvoie 20 38
```

### Nombre d’arguments arbitraire : passage d’un tuple


```python
def somme(*args):
    """" Renvoie la somme de <tuple>."""
    resultat = 0
    for nombre in args:
        resultat += nombre
    return resultat

# Exemples d’appel :
print(somme(23)) # 23
print(somme(23, 42, 13)) # 78
```

Si la fonction possède plusieurs arguments, le *tuple* est en dernière position. Il est aussi possible de passer un tuple (en fait une séquence) à l’appel qui sera décompressé
en une liste de paramètres d’une fonction « classique » :

```python
   def somme(a, b, c):
        return a+b+c
    
   # Exemple d’appel :
   elements = (2, 4, 6)
   print(somme(*elements)) # 12

```

### Nombre d’arguments arbitraire : passage d’un dictionnaire


```python
def unDict(**kargs):
    return kargs

# Exemples d’appels
## par des paramètres nommés :
print(unDict(a=23, b=42)) # {’a’: 23, ’b’: 42}

## en fournissant un dictionnaire :
mots = {'d': 85, 'e': 14, 'f':9}
print(unDict(**mots)) # {’e’: 14, ’d’: 85, ’f’: 9}
```

### Documenter une fonction
Après avoir élaboré une fonction (surtout une fonction relativement long et complexe), il et
fortement de la documenter afin de permettre à d’autres utilisateurs de se l’approprier
rapidement. La documentation d’une fonction est généralement une chaîne de caractères qui
fournit une générale de la fonction ainsi que les aides utiles. Cette description est
généralement spécifiée après la déclaration du nom de la fonction avant la définition des
autres blocs d’instructions. L’exemple ci-dessous illustre comment documenter une fonction et
comment accéder à cette document en cas de besoin.


```python
def volumeSphere():
    """ Ce programme calcule le volume d'un cube.\n La fonction est définie avec un seul argument obligatoire r
    qui représente le rayon du cercle.
    Celui-ci peut prendre n'importe quelle valeur positive"""
    r=float(input("Saisir le rayon de la sphère"))
    PI = 3.14
    return (4 * PI * r**3)/3
```

Dans la définition de la fonction volumeSphere, la chaine de caractères ne joue aucun rôle
fonctionnel dans le script : elle est traitée par Python comme un simple commentaire, mais qui
est mémorisé comme une documentation interne sur la fonction. Cette document est stockée
dans un attribut appelé `__doc__`. Pour afficher cette attribut, on fait:


```python
print(volumeSphere.__doc__)
```

## Modules


Un programme Python est généralement composé de plusieurs fichiers sources,
appelés *modules*. Leur nom est suffixé `.py`. S’ils sont correctement codés les modules doivent être indépendants les uns des
autres pour être réutilisés à la demande dans d’autres programmes.

`Les modules sont des fichiers qui regroupent des ensembles de fonctions`.
Un **module** est un fichier indépendant permettant de scinder un programme en plusieurs scripts.
Ce mécanisme permet d’élaborer efficacement des bibliothèques de fonctions ou de classes.
Avantages des modules :
- réutilisation du code ;
- la documentation et les tests peuvent être intégrés au module ;
- réalisation de services ou de données partagés ;
- partition de l’espace de noms du système.

Tout comme les dictionnaires sont des collections d’objets (listes, tuples, set, etc..), les
modules sont des collections de fonctions qui permettent de réalisées des tâches apparentées.
Par exemple, le module math, contient un certain nombre de fonctions mathématiques telles
que sinus, cosinus, tangente, racine carrée, etc. De nombreux modules sont déjà pré-installés dans la bibliothèque standard de python.
Toutefois, pour réaliser certaines tâches spécifiques, on est souvent amené à installer des
modules supplémentaires (ex : numpy, scipy, matplotlib, pandas, etc..)

### Import d’un module

Deux syntaxes possibles :
    
- la commande `import nom_module` importe la totalité des objets du module :  
  ```python
     import tkinter
  ```
- la commande `from <nom_module> import obj1, obj2`... n’importe
que les objets `obj1, obj2...` du module : 
  ```python
     from math import pi, sin, log
  ```
  
Il est conseillé d’importer dans l’ordre :
- les modules de la bibliothèque standard ;
- les modules des bibliothèques tierces ;
- les modules personnels.  

### La bibliothèque standard
On dit souvent que Python est livré « piles comprises » (batteries included) tant sa biblio-
thèque standard, riche de plus de 200 packages et modules, répond aux problèmes courants
les plus variés.


```python
import math
dir(math)  # Pour voir l’ensemble des fonction qui forment le module.
```


```python
help(math.gamma) # renvoie l’aide sur la fonction gamma du module math
```


```python
from math import sin # Importe la fonction sinus
from math import cos, sin, tan, pi # Importe respectivement les fonction cosinus, sinus, tangente et la valeur pi (3.14).
```


```python
from math import * # Importe toutes les fonction associées à math (équivalent à import math)
```

<left> <b> <span style="color:brown;">Quelques utilisations de la fonction math : </span> </b></left>
```python
   from math import *
    v=16 # définit une variable v
    x = math.sqrt (v) # Renvoie la racine carrée de v
    y = math.e(v) # Renvoie l’exponentiel de v
    z = math.log(v) # Renvoie le logarithme népérien de v

```

<left> <b> <span style="color:brown;">Quelques exemples d’utilisation du module random: </span> </b></left>

```python
   from random import random, randint, seed, uniform, randrange,sample, shuffle # Importe quelques fonctions utiles de random
 
```


```python
import random
x=random.random() # Renvoie un nombre aléatoire.
print(x)
```


```python
import random
x=random.randint(5,17) # Renvoie un nombre aléatoire entier entre 5 et 17.
print(x)
```


```python
import random
x=random.uniform(5,17) # Renvoie un nombre aléatoire uniforme réel entre 5 et 17.
print(x)
```

## Amusez a regarder les modules `turtle`, `time`, `decimal`, `fractions`, `cmath`.

### Bibliothèques tierces
Outre les modules intégrés à la distribution standard de Python, on trouve des biblio-
thèques dans tous les domaines :
- scientifique ;
- bases de données ;
- tests fonctionnels et contrôle de qualité ;
- 3D ;
- ...

Le site [PYPI](pypi.python.org/pypi) (The Python Package Index) recense des milliers de modules
et de packages !

<!--NAVIGATION-->
<  [5. Fonctions et Modules](https://colab.research.google.com/github/ai-technipreneurs/programmation-python-pratique/blob/master/6_Fonctions-et-Modules.ipynb) | [Sommaire](https://colab.research.google.com/github/ai-technipreneurs/programmation-python-pratique/blob/master/Index.ipynb) >
