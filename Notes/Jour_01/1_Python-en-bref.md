---
layout: default
title: Python en bref
---



****

# 0. Pourquoi Python ?

Le langage de programmation Python est une très bonne option tant pour ceux qui débutent en programmation que pour ceux qui s'y connaissent déjà beaucoup plus. C'est un langage de très haut niveau dont la syntaxe encourage à écrire du code clair et de qualité. De plus l'apprentissage de Python est facilité par l’existence d’une interface interactive et en particlier par l'utilisation des `calepin Jupyter`. Cela dit, son intérêt ne se limite pas à l'apprentissage de la programmation ou de l’algorithmique; sa popularité et son utilisation vont bien au-delà du cadre académique, en témoigne sa popularité croissante. Il a été choisi par des acteurs majeurs comme `Google`, `YouTube`,
la `NASA`.



1. C'est un langage **interprété**: lorsqu'on écrit une instruction, on peut directement l'exécuter. A l'opposé, un langage **compilé** nécessite l'écriture (et la compilation) d'un programme entier avant de pouvoir le tester. Un langage interprété permet de programmer plus facilement, **de manière interactive**, de tester facilement un morceau de code. C'est donc un langage idéal pour rapidement développer et tester des prototypes, ou plus particulièrement, des algorithmes d'analyse de données.

2. C'est un langage **haut-niveau**: une seule ligne de code permet dans certains cas de réaliser des processus complexe, en cachant les détails liés notamment à la gestion ou la représentation des données dans la mémoire de l'ordinateur, ou les opérations arithmétiques ou binaires de bas-niveau. Un langage de haut-niveau rend plus facile le développement d'un programme, et augmente donc la **productivité** (généralement au détriment de la vitesse d'exécution).

3. Python est **open source**: et donc **gratuit** pour tout le monde, y compris les entreprises.

4. C'est un langage **populaire**: la communauté de développeurs est très active, et on trouve facilement sur internet de la documentation et de très **nombreux exemples d'utilisation** dans tout type d'application. De plus, la communauté développe et maintient de très **nombreuses librairies** développées et/ou compatibles avec Python, permettant d'augmenter la productivité lors de l'écriture d'un programme, particulièrement dans les domaines des mathématiques et des sciences des données.

![Texte alternatif…](https://github.com/titsitits/Python_Data_Science/blob/master/Images/python_stack_overflow_withsource.png?raw=true)

(source: https://stackoverflow.blog/2017/09/06/incredible-growth-python/)


Python est donc le langage idéal pour développer et tester facilement et rapidement un algorithme. Le désavantage principal est sa lenteur: l'exécution d'un langage haut-niveau et interprété est généralement plus lente que celle d'un langage compilé. 

Dans un contexte où la vitesse d'exécution est cruciale (e.g. pour des systèmes embarqués, ou traitement de données en temps réel, des programmes réactifs), Python n'est pas le langage idéal. A l'inverse, dans un contexte où la vitesse de développement est cruciale (développement de prototypes, d'applications business concurrentes), la productivité offerte par le langage Python en fait un bon choix.




Les principales caractéristiques du langage Python:

 - **Syntaxe simple** et __lisible__ : langage pédagogique et facile à apprendre et à utiliser;
 - __Langage interprété__ : utilisation interactive ou script exécuté ligne à ligne, pas de processus de
compilation;
 - __Haut niveau__ : typage dynamique, gestion active de la mémoire, pour une plus grande facilité
d’emploi;
 - __Multi-paradigme__ : langage impératif et/ou orienté objet, selon les besoins et les capacités de
chacun;
 - __Logiciel libre__ et __ouvert__, largement répandu (multi-plateforme) et utilisé (forte communauté);
 - __Riche bibliothèque standard__ : Batteries included;
 - __Riche bibliothèque externe__ : de nombreuses bibliothèques de qualité, dans divers domaines (y
compris scientifiques), sont déjà disponibles.

Les différentes versions de Python (pour *Windows*, *Unix*, etc.), son  **tutoriel** original, son __manuel de référence__ , la  **documentation** des bibliothèques de fonctions, etc. sont disponibles en téléchargement
gratuit depuis Internet, à partir du [site web officiel](http://www.python.org).





L’objectif de cette formation est bien d'apprendre un *seul* langage de haut niveau, permettant tout aussi bien des analyses rapides dans la vie de tous les jours – quelques lignes de code en intéractif – que des programes plus complexes (projets plus volumineux, p.ex. de plus de 100000 lignes).


# 1. Types de données de base

## 1.0 Scalaires et chaînes de caractères (ou strings)

On identifie généralement quatre types de données de base en Python.

Trois sont des **données numériques**:
* Booléen (**`bool`**): `True, False`
* Nombre entier (**`int`**): `-42, 0, 1, 42, 250000`
* Nombre décimal à virgule flottante (**`float`**): `42.0, 3.14, -0.01`

La dernière permet de représenter du **texte**:

* Chaîne de caractères (**`string`**): `"Hello World!"` ou `'Hello World!' `

On définit un **`string`** en entourant le texte des symboles **"double quote"** ou **'simple quote'**. Ainsi, 4 représente un **`int`**, mais "4" représente un **`string`**.


```python
mon_entier1 = 2
mon_entier2 = -4
mon_flottant = 4.2
mon_booleen = True
ma_chaine_de_caractere1 = "Rue de Cotonou"
ma_chaine_de_caracter2 = ' 64'
ma_chaine_de_caractere3  = " Akpakpa "

```

### 1.0.0 Opérations sur les scalaires 
  

Les opérations de base peuvent se faire entre différents types de données numériques, en réalisant des conversions implicites de types si nécessaire:

* Les **int**, **float** et **bool** peuvent être additionnés (**+**), multiplés (**\***), divisés (**/**), ou soustraits (**-**) entre eux.  
* L'opérateur **\*\*** et un opérateur de puissance (exposant): 2\*\*10 => 1024
* L'opérateur **%** et un modulo (reste de la division entière): 11%3 => 2



```python
#Operations sur un seul type de donnée
print(  mon_entier1+mon_entier2,   111-69,   6*7,   (mon_entier1 + mon_entier12) * 10 + 2)
```


```python
#Opération compatibles entre types différents (entier, float, booléen)
print(mon_entier1 + mon_flottant,\
      mon_flottant + mon_booleen,\
      (mon_entier1 + mon_entier2 - 3.5) * 5 / 2)
```


```python
#Exposant
print(2 ** 42)

#Modulo
print(11%3)
```


```python
#La division entière renvoie un float (contrairement au langage C)
8/3
```


```python
# Attention:
a/2  # le résultat 1.5 en Python 3.4 
     # mais 1 en 2.7
```

### 1.0.1 Opérations sur des chaînes de caractères

Les strings peuvent être additionnés entre eux (**+**), ou multiplés par un entier (**\***):

  * Deux **string** peuvent être additionnés, ce qui résulte en une concaténation: "hell" + "o" => "hello"
  * Un **string** peut être multiplié par un entier, ce qui résulte en une concaténation multiple du string: "hi"*3 => "hihihi"


```python
#Les opérations sur les strings sont des concaténation
address = ma_chaine_de_caractere1 + ma_chaine_de_caractere2 + ma_chaine_de_caractere3
print(address)
print("Bonjour" * 3)
```

* Les opérations invalides (telle qu'additionner un string avec une variable numérique), renvoient une erreur:


```python
mon_entier1 + ma_chaine_de_caractere1
```


```python
string = '4'
string + str(mon_entier1)
```


```python
mon_entier1 + int(string)
```

## 1.1 Structures de base

### 1.1.0 Listes
Les listes permettent des combinaisons de types.  


```python
ma_liste1= [0,53,562,'rdv',[17,"l",298,43]] 
```

### 1.1.1 Tuple
Un tuple est similaire à une liste mais ne peut être modifié, il est défini par des parenthèses.


```python
mon_tuple_1= (2020,34,42,'h')

```

### 1.1.2 Dictionnaire
Un dictionnaire est similaire à une liste mais chaque entrée est assignée par une clé / un nom, il est défini avec des accolades.


```python
mois = {'Jan':31 , 'Fev': 29, 'Mar':31, 'Avr':30}
```


```python

```

# 2. Syntaxe de Python


## 2.0 Structures de contrôle 
Certaines instructions permettent de contrôler le flux du code:

* Les **conditions** permettent de réaliser un bloc d'instructions, ou de l'éviter, ou encore de choisir un bloc d'instructions parmi plusieurs.
* Les **boucles** permettent de repasser plusieurs fois, de manière itérative, par le même bloc d'instructions
* Pour différencier les différents blocs d'instructions, on utilise l'**indentation** (en utilisant des Tab, ou des Whitespace)

En Python, l'indentation de chaque ligne de commande est donc très importante, puisque c'est elle qui définit le flux des instructions.

### 2.0.0 Structure conditionnelle
Les mot-clés **`if`**, **`elif`**, et **`else`** permettent de définir un flux conditionnel d'instructions:
* "**`if condition:`**" : si la condition est vraie (**`True`**), le bloc d'instruction indenté sous cette condition est réalisé
* "**`elif condition2:`**": si la condition précédente était fausse (dans le **`if`** précédent), et que cette condition2 est vraie, le bloc d'instruction indenté sous cette condition est réalisé
* "**`else:`**": si toutes les conditions précédentes étaient fausses, le bloc indenté suivant est réalisé
* Attention à l'**indentation** et au symbole **":"** ! C'est le bloc indenté après le symbole ":" qui dépend de la condition



```python
# si alors sinon
a = -23
if a > 0:
    b = 0
    print(b)
else:
    b = -1
print(b)
```

### 2.0.1 Structure itérative
Les boucles permettent de définir un flux itératif d'instructions:
* **`while condition:`**: on éxécute le même bloc d'instructions itérativement tant qu'on respecte une condition
* **`for variable in variable_set:`**: on exécute le bloc d'instructions itérativement sur un ensemble d'éléments


```python
for i in range(1,8,2):
    print(i)
```

## 2.1 Fonctions

Une fonction est un regroupement d’instructions impératives – assignations, branchements, boucles –
s’appliquant sur des arguments d’entrée. C’est le concept central de la _programmation impérative_.


```python
# Définition d'une fonction
def pythagorus(x,y):
    """ Calcule l'hypotenuse d'un triangle """
    r = pow(x**2+y**2,0.5)
    return x,y,r
pythagorus(5,6)
```


```python
# exemple d'appel
pythagorus(x=5,y=7)
```


```python
# aide intégrée
help(pythagorus)
```


```python
pythagorus.__doc__
```

# Un résumé élargi
- Les types et structures de base
  - 250000 #entier
  - 0.12 #float
  - '42' ou "42" #string
  - True False #booléens
  - [3, 4, 'ville'] #Liste
  - ('formation',20, 'Cotonou') # Tuple
  - {'Jan':31 , 'Fev': 29, 'Mar':31, 'Avr':30} #Dictionaire
- Les blocs sont définis par **l’indentation** (en général par pas de 4 espaces);
- Une instruction par ligne en *général* (ou instructions séparées par `;`);
- Les **commentaires** commencent par `#`, et vont jusqu’à la fin de la ligne;
- **Expression booléenne** : une condition est une expression s’évaluant à `True` ou `False`:
  - `False` : test logique faux (p.ex. 3 == 4), valeur nulle, chaîne vide (''), liste vide ([]), etc,
  - `True` : test logique vrai (p.ex. 2 + 2 == 4), toute valeur ou objet non-nul (et donc s’évaluant
par défaut à True *sauf exception*);
  - **Tests logiques** : `==`, `!=`, `>`, `>=`, etc;
  - **Opérateurs logiques** : `and`, `or`, `not`;
  - **Opérateur ternaire** : `valeur **if** condition **else** valeurealt`;
- **Expression conditionnelle** : `**if** condition1 : ... [**elif** condition2 : ...] [**else**: ...]`;  
- **Boucle for** : `**for** élément **in** itérable`, s’éxecute sur chacun des éléments d’un objet itérable :
  - `continue` : interrompt l’itération courante, et reprend la boucle à l’itération suivante,
  - `break` : interrompt complètement la boucle;
- **Boucle while** : `while condition` : se répéte tant que la condition est vraie, ou après une sortie
explicite avec break.

Ces structures seront discutées en details dans les calepins à venir.

# Références principales

 1. **Yaé U. Gaba, J. Sanders; J. Masakuna** (2016); [Introduction to Programming using Python (IPuP)](https://github.com/gabayae/scientific-computing/edit/master/README.md).


 2. **Mac Kinney W.** (2013); *Python for Data Analysis*, O’Reilly; [pdf](http://it-ebooks.info/book/104).
 

 3. **Sheppard K.** (2014); *Introduction to Python for Econometrics, Statistics and Data Analysis*,[pdf](https://www.kevinsheppard.com/images/0/09/Python_introduction.pdf).
 

 4. **Moussa Keita** (2017); *Data Science with Python: Algorithm, Statistics, DataViz, DataMining and Machine-Learning*. [pdf](https://mpra.ub.uni-muenchen.de/76653/).




# Plus de littérature (Références secondaires)

Il existe également de très bons ouvrages imprimés concernant Python. La plupart concernent encore
Python 2.x, mais vous ne devrez guère éprouver de difficultés à adapter leurs exemples à Python 3. En
langue française, vous pourrez très profitablement consulter les manuels ci-après:

- __Programmation   Python__,   par   Tarek   Ziadé,   éditions   Eyrolles,   Paris,   2009,   586   p.,   ISBN
978-2-212-12483-5. C’est l’un des premiers ouvrages édités directement en langue française sur le
langage Python. Excellent. Une mine de renseignements essentielle si vous voulez acquérir les
meilleures pratiques et vous démarquer des débutants.


- __Au cœur de Python__, volumes 1 et 2, par Wesley J. Chun, traduction de 
Python core programming, 2d
edition
 (Prentice Hall) par Marie-Cécile Baland, Anne Bohy et Luc Carité, éditions CampusPress,
Paris, 2007, respectivement 645 et 385 p., ISBN 978-2-7440-2148-0 et 978-2-7440-2195-4. C’est un
ouvrage de référence indispensable, très bien écrit. 


- __Apprendre à programmer avec Python__, de Gérard Swinnen (troisième et cinquième éditions), un excellent ouvrage que l'on peut obtenir [ici](https://inforef.be/swi/python.htm).


- [Le tutoriel Python](https://docs.python.org/fr/3/tutorial/).


- Vous pouvez aussi trouver en ligne et en français, l’excellent cours sur Python 3 de Robert Cordeau,
professeur à l’IUT d’Orsay. Il est disponible sur le site de l'[AFPY](http://www.afpy.org/Members/bcordeau/Python3v1-1.pdf/download).


Maintenant que vous connaissez les bases du Python, vous pouvez passer aux [2. Variables, Types et Opérations.ipynb](https://colab.research.google.com/github/ai-technipreneurs/programmation-python-pratique/blob/master/2_Variables_Types_Op%C3%A9rations.ipynb)


[Contenu](../Contents.md) \| [Précédent (1.0. Sur Colab)](0_Sur-Colab.md) \| [Suivant (1.2. Variables, Types et Opérations)](2_Variables-Types-Opérations.html)

