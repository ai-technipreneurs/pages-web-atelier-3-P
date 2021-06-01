---
layout: default
title: Vue d'ensemble
description: Vue d'ensemble
---



# Vue d'ensemble

## Variables et assignement

Python est un langage dynamiquement typé, les variables n'ont pas
besoin d'être déclarées, et leur type peut changer au cours de
l'exécution.

``` python
python: a = 3
python: type(a)
<type 'int'>
python: a = '3'
python: type(a)
<type 'str'>
python: a
'3'
python: int(a)
3
``` 

## Syntaxe

L'indentation en Python a une valeur syntaxique : elle sert à délimter
les blocs. Toutes les lignes d'un même bloc doivent être précédées du
même nombre d'espaces blancs ; en général on conseille d'utiliser 4
espaces blancs.

Voici un exemple de bloc conditionnel mettant en évidence cette
syntaxe.

``` python
if a == 0:
    print 'a vaut 0'
elif a > 0:
    print('a est positif')
    print('il vaut : ', a)
else:
    print('a est négatif')
print 'encore des questions sur a?'
```

## Structures de contrôle

Source : <https://docs.python.org/3.5/tutorial/controlflow.html>

### `if... else`

La seule construction conditionnelle existante en Python est
`if... elif... else...`. Toutes les branches sont optionnelles, à
l'exception du `if`, il peut y avoir un nombre quelconque de `elif`,
mais un seul `else` à la fin.

``` python
if a == b == c:
    print('égaux')
elif a <= b <= c  or  c <= b <= a:
    print 'b au milieu'
elif b <= a <= c  or  c <= a <= b:
    print('a au milieu')
else:
    print('c au milieu')
``` 

### Boucle `for... in`

Fondamentalement, il existe deux types de boucles en Python. La plus courante
est la `for... in` qui permet de parcourir les éléments d'un itérable.

``` python
for i in range(10):
    print(i)
``` 

#### La fonction `range`

La boucle `for` est souvent utilisée en conjonction avec la fonction
`range`, dont la syntaxe générale est :

``` python
range(start, end, step)
``` 

Ainsi appelée, la fonction génère la liste des entiers entre `start`
(inclus) et `end` (non inclus) avec pas de `step` :

``` python
python: range(0, 10, 2)
[0, 2, 4, 6, 8]
``` 

Les deux autres syntaxes admissibles sont `range(start, end)` (pas
égal à 1) et `range(end)` (début égal à 0).

**Note :** À partir de Python 3.x, `range` ne renvoie plus une liste,
 mais un *générateur*. La différence réside exclusivement dans
 l'utilisation de la mémoire, beaucoup plus efficace avec la 3.x. Le
 même comportement est réalisé par la fonction `xrange` en Python 2.x.

### Boucle `while`

La deuxième boucle est la `while`.

``` python
a = 0
while a < 10:
    a += 1
    print(a)
``` 

Pas étonnant qu'il soit alors beaucoup plus facile d'écrire une boucle
infinie :

``` python
while True:
    print('boucle toujours')
``` 

### Interrompre les boucles: `break`, `continue` et `return`

L'instruction `break` sort de la boucle sans vérifier la
condition :

``` python
for i in range(10):
    print(i)
    if i > 2:
        break
``` 

L'instruction `continue` passe à l'itération suivante en sautant le
reste du corps :

``` python
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
``` 

Et le `return` sort immédiatement de toute boucle et de la fonction
qui le contient.



## Listes

Source : <https://docs.python.org/3/tutorial/datastructures.html>

L'un des objets les plus utilisés en Python, ce sont les listes. On
déclare une liste avec les crochets `[]`, et on accède à ses éléments
comme on accède aux éléments d'un tableau en C :

``` python
python: l = ['nom','prenom',35, 'a', True]
python: l
['nom','prenom',35, 'a', True]
python: l[0]
'nom'
python: l[4]
True
python: l[5]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
``` 

Les indices négatifs accèdent aux éléments à partir du
dernier :

``` python
python: l[-1]
True
python: l[-4]
'prenom'
python: l[-6]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
``` 

Il est aussi possible d'obtenir les sous-listes d'une liste. On parle de
`slicing`. L'expression `l[start:end:step]` donne la sous-liste de `l`
qui démarre à l'élément `start` (inclus), se termine à l'élément `end`
(exclus) et saute tous les `step` éléments.

``` python
python: l = range(10)
python: l
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
python: l[0:4]
[0, 1, 2, 3]
python: l[0:4:2]
[0, 2]
python: l[2:]
[2, 3, 4, 5, 6, 7, 8, 9]
python: l[:-3]
[0, 1, 2, 3, 4, 5, 6]
python: l[0::3]
[0, 3, 6, 9]
python: l[4:-2]
[4, 5, 6, 7]
python: l[::]
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
python: l[:]
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

``` 

La syntaxe `[:]` est un raccourci courant pour *copier* une liste :

``` python
python: l[:] == l
True
python: l[:] is l
False
``` 

### Compréhensions

Python offre une syntaxe pour la création des listes qui devrait être
familière aux mathématiciens. C'est l'écriture en `compréhension` bien connue
dans la théorie des ensembles. Elle permet entre autre, de réduire l'écriture
de loupes. C'est un héritage du langage Lisp appelé
*compréhensions de listes* :

``` python
python: [a + 0.5 for a in range(10)]
[0.5, 1.5, 2.5, 3.5, 4.5, 5.5, 6.5, 7.5, 8.5, 9.5]
``` 

ce qui est sémantiquement équivalent à

``` python
l = []
for a in range(10):
    l.append(a + 0.5)
``` 

On peut ajouter un nombre arbitraire de `for` et de `if` (sans `else`)/ opérations
logiques dans une compréhension, ils seront déroulés dans l'ordre :

``` python
[x*y for x in range(10) for y in range(x) if (x + y) % 2 == 0]
``` 

(les retours à la ligne sont optionnels) est équivalent à

``` python
l = []
for x in range(10):
    for y in range(x):
        if (x + y) % 2 == 0:
            l.append(x*y)
``` 



## Fonctions

Source : <https://docs.python.org/3/tutorial/controlflow.html>

Les fonctions Python sont définies par le mot clef `def`. Elles
peuvent prendre un nombre arbitraire de paramètres, et renvoyent une
valeur à l'aide du mot clef `return`. Toute fonction renvoye une
valeur, les fonctions qui n'ont pas de `return` renvoient la valeur
spéciale `None`.

``` python
def max(x, y):
    if x > y:
        return x
    else:
        return y
``` 

Certains paramètres peuvent prendre des valeurs par défaut. Si un
paramètre prend une valeur par défaut, tous ceux qui le suivent
doivent aussi en prendre.

``` python
python: def test(a, b, c=0, d=False):
.......    return a, b, c, d

python: test(1, 2)
(1, 2, 0, False)
python: test(1, 2, 3)
(1, 2, 3, False)
python: test(1, 2, 3, 4)
(1, 2, 3, 4)
python: test(1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: test() takes at least 2 arguments (1 given)
``` 

Les paramètres d'une fonction peuvent être assignés hors ordre avec la
notation `paramètre=valeur` :

``` python
python: test(b=1, a=2)
(2, 1, 0, False)
python: test(1, 2, d=4)
(1, 2, 0, 4)
``` 

Python fournit deux opérateurs unaires pour transformer des objets en
paramètres d'une fonction. L'opérateur `*` transforme une liste ou un
tuple, tandis que l'opérateur `**` transforme un dictionnaire :

``` python
python: l = range(4)
python: test(*a)
(0, 1, 2, 3)
python: d = { 'a' : 3, 'b' : 5, 'd' : 1 }
python: test(**d)
(3, 5, 0, 1)
``` 



## [Python: un survol rapide](http://www.larsen-b.com/static/intro_python/)









[Retour](./)
