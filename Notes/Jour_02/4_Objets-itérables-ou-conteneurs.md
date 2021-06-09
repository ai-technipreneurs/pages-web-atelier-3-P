---
layout: default
title: Objets itérables ou conteneurs
---


[Contenu](../Contenu.html) \| [Précédent (2.1 Chaînes de caractères)](../Jours_02/3_Chaînes-de-caractères.html)


<a href="https://colab.research.google.com/github/ai-technipreneurs/programmation-python-pratique/blob/master/4_Objets-it%C3%A9rables-ou-conteneurs.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

****

# <center> <b> <span style="color:orange;"> Atelier 3P </span> </b></center>

## <center> <b> <span style="color:green;">Programmation Python Pratique</span> </b></center>

<center>
    <a href="https://github.com/ai-technipreneurs" ><img src="https://avatars.githubusercontent.com/u/83169416?v=4" style="float:center; max-width: 650px; display: inline" alt="IMSP"/> </a>
    </center>

### <center> <b> <span style="color:blue;"> Objets itérables ou conteneurs</span> </b></center>

#### <left> <b> <span style="color:brown;">Instructeur : </span> </b></left>[ai-technipreneurs](https://github.com/ai-technipreneurs)

****

Python offre *les conteneurs*.
De façon générale, un conteneur, comme son nom l'indique, est un objet composite destiné à contenir d’autres objets. Ce calepin détaille les listes et les dictionnaires, et donne également un bref apercu sur les ensembles et les tuples.


Comme signalé dans les sections précédentes, un programme python fonctionne toujours sur
la base des manipulations des objets. Les instructions (qu’elles soient définies dans un code
libre, dans une clause if ou dans une boucle while ou for) sont toujours exécutées sur des
objets. Les variables telles que discutées précédemment représentent un type particulier
d’objet python. Sinon d’une manière générale, les instructions dans un programme python
sont définies à partir d’une collection d’objets qui se présentent sous différentes formes de
séquences de valeurs. Cette séquence de valeurs peut être par exemple constituée par un
ensemble de variables à valeur unique. Ce qui signifie finalement qu’une variable définie à
partir d’une seule valeur n’est généralement pas suffisant pour former l’architecture d’un
programme. Dans le langage python, nous avons:
    
   - Un objet **liste** est une séquence de valeurs (numériques et /ou caractères) **indicées** et
spécifiées à l’intérieur des **crochets**, séparées par des virgules. Exemple :
      ```python
         x = [ 1 , 5 , 8, 10 ,4 , 50, 8 ] # Liste formée uniquement de chiffres
         y = ["Olivier","ENGEL","Strasbourg"] # liste formée uniquement de caractères
         z = [1, "Olivier",5 , 8, "ENGEL",10, 4, 50, "Strasbourg"] # liste formée de chiffres et de caractères.
       
      ``` 
     Un objet liste peut être généré manuellement en indiquant les valeurs entre crochets ou
     automatiquement en utilisant la fonction `list()`.
      ```python
        x = list(range(1,10))
        print(x) # renvoie [1, 2, 3, 4, 5, 6, 7, 8, 9]
     ```
   - Un objet **tuple** est une séquence de valeurs (numériques et /ou caractères) **indicées** et
spécifiées à l’intérieur des **parenthèses**, séparées par des virgules. Exemple :
      ```python
         x = ( 1 , 5 , 8, 10 ,4 , 50, 8 ) # tuple formé uniquement de chiffres
         y = ("Olivier","ENGEL","Strasbourg") # tuple formé uniquement de caractères
         z = (1, "Olivier",5 , 8, "ENGEL",10, 4, 50, "Strasbourg") # tuple formé de chiffres et de caractères.
       
      ``` 
     Un objet tuple peut être généré manuellement en indiquant les valeurs entre crochets ou
     automatiquement en utilisant la fonction `tuple()`.
      ```python
        x = tuple(range(1,10))
        print(x) # renvoie (1, 2, 3, 4, 5, 6, 7, 8, 9)
     ```
     
   - Un objet **set** est une séquence de valeurs (numériques et /ou caractères) **non
dupliquées** et **non indicées**, et spécifiées à l’intérieur des **accolades**, séparées par des
virgules. Exemple :
      ```python
         x = { 1 , 5 , 8, 10 ,4 , 50, 8 } # set formé uniquement de chiffres
         y = {"Olivier","ENGEL","Strasbourg"} # set formé uniquement de caractères
         z = {1, "Olivier",5 , 8, "ENGEL",10, 4, 50, "Strasbourg"} # set formé de chiffres et de caractères.
       
      ``` 
     Un objet tuple peut être généré manuellement en indiquant les valeurs entre crochets ou
     automatiquement en utilisant la fonction `set()`.
      ```python
         v = [2 , 4 , "orange", "viande", 4, "orange"]
         V = set(v)
         print(V) # renvoie {2, 'orange', 4, 'viande'}
      
      ```
   - Un objet **dictionnaire** est une séquence de valeurs (numériques et /ou caractères)
**indicées** par des clés et spécifiées à l’intérieur des **accolades** et séparées par des
virgules. A chaque `clé` correspond une ou plusieurs `valeurs`. Un dictionnaire est
constitué d’un ensemble `clé-valeurs`. Exemple :   
      ```python
         x = {'nom':'Jean', 'poids':70, 'taille':1.75} # Clés à valeurs uniques.
         y = {'Jean':[25,70,1.75],'Paul':[30,65,1.80],'Pierre':[35,75,1.65]} # Clé à plusieurs valeurs formée par une liste
      
      ```
   Pour le dictionnaire `x`, les clés sont nom, poids et taille. Les valeurs correspondant à
chacun de ces clés sont respectivement jean, 70 et 1.75.
Pour le dictionnaire `y`, les clés sont Jean, Paul et Pierre alors que les valeurs sont des
listes constituées de trois valeurs (âge, poids et taille).
Un objet dictionnaire peut être généré manuellement en indiquant les valeurs entre
accolades ou automatiquement en utilisant la fonction `dict()` pour créer un dictionnaire
vide. Nous reviendrons plus en détails sur la définition des dictionnaires.   

Les quatres objets que nous venons de citer sont aussi ceux que nous appelons les `conteneurs` pour la simple raison qu'ils `peuvent contenir` quelque chose. Ainsi, les chaînes de caractères, listes, tuples et dictionnaires sont les objets itérables de base en Python. Les
listes et dictionnaires sont mutables – leurs éléments constitutifs peuvent être changés à la volée – tandis
que chaînes de caractères et les tuples sont immuables.

Les trois derniers objets que nos citons ne sont pas itérables mais nous les mentionnons et en ferons une etude plus detaillee et assez mintieuse dans la suite.

   - Un objet **fonction** est un programme conçu pour réaliser une opération bien précise.
Par exemple la fonction `print()` permet d’afficher à l’écran les résultats de l’instruction
qu’on lui fournit;
   - Un objet **classe** est une collection de fonctions c'est-à-dire une association de fonctions
apparentées;
   - Un objet **module** est une collection de classe c'est-à-dire une collection de classes
apparentées.

## Listes
Un objet liste peut être déclaré et défini manuellement ou en utilisant la fonction `list()`. On
distingue deux catégories de listes. Les listes à une dimension (ou listes simples) et les listes à
plusieurs dimensions.


```python
voltage = [-2.0, -1.0, 0.0, 1.0, 2.0]

courant = [-1.0, -0.5, 0.0, 0.5, 1.0]

type(courant) # Renvoie le type de la variable courant
```




    list




```python
help(voltage.sort())
```

    Help on NoneType object:
    
    class NoneType(object)
     |  Methods defined here:
     |  
     |  __bool__(self, /)
     |      self != 0
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
    


Par ailleurs, dans certaines situations, il arrive qu’on crée d’bord une liste vide et qui sera par la
suite remplie par des valeurs en utilisant la fonction `append()`. Pour créer une liste vide, on fait :
`x = list()` Ou bien `x = []`.

Contrairement à une liste simple, une liste à plusieurs dimensions est une liste dont les
éléments individuels sont constitués de plusieurs valeurs. D’une manière générale, une liste à
plusieurs dimensions se présente comme une liste de listes.


```python
x = [[1,2,3],[2,3,4],[3,4,5]] # liste à deux dimensions (liste de listes)

y = [[[1,2],[2,3]],[[4,5],[5,6]]] # liste à trois dimensions (liste de listes de listes)

x,y
```




    ([[1, 2, 3], [2, 3, 4], [3, 4, 5]], [[[1, 2], [2, 3]], [[4, 5], [5, 6]]])




```python
La liste étant une séquence de valeurs indicées, on peut accéder à chacun des valeurs ou des groupes de valeurs en
indiquant leur indice:
```


      File "<ipython-input-4-297b630a6d1f>", line 1
        La liste étant une séquence de valeurs indicées, on peut accéder à chacun des valeurs ou des groupes de valeurs en
               ^
    SyntaxError: invalid syntax




```python
x = list ([' lundi ',' mardi ',' mercredi ',1800,20.357,' jeudi ',' vendredi ']) # Définition d’une liste
print(x) # affiche tous les éléments de la liste x
```


```python
print(x[0]) # renvoie le premier élément de x :lundi (Nb :l’indiçage commence toujours à 0)
print("================================================")
print('\t')



print(x[3]) # renvoie l’élément d’indice 3( quatrième élément de x) :1800
print("================================================")
print('\t')


print(x[1:3]) # Renvoie tous éléments compris entre l’indice 1 et l’indice 3 (Nb : l’élément d’indice 3 est exclu)
print("================================================")
print('\t')



print(x[1:6 :2]) # Renvoie tous éléments compris entre l’indice 1 et l’indice 6 avec un saut de 2 éléments à chaque fois ['mardi', 1800, 'jeudi'](l’élément d’indice 6 est exclu).
print("================================================")
print('\t')


print(x[2 :]) # renvoie tous éléments à partir de l’élément d’indice 2 (inclu).
print("================================================")
print('\t')



print(x[:3]) # renvoie tous éléments situés avant l’élément d’indice 3 (exclu)
print("================================================")
print('\t')



print(x[-1]) # Indiçage négatif, renvoie le dernier élément de la liste (équivaut ici à x[6])
print("================================================")
print('\t')



print(x[-2]) # Indiçage négatif, liste(équivaut ici à x[5]) renvoie l’avant-dernier élément de la
print("================================================")
print('\t')



print(x[: :2]) # Parcourt tous éléments compris entre l’indice 0 et le dernier indice en renvoyant tous les éléments avec un saut de 2 éléments à chaque fois ['lundi', 'mercredi', 20.357, 'vendredi'].
print("================================================")
print('\t')


print(x[: :-1]) # renvoie une liste contenant tous éléments de x en les réorganisant du dernier élement au premier élément. Il s’agit de faire reverse sur x. renvoie ['vendredi', 'jeudi', 20.357, 1800, 'mercredi','mardi', 'lundi']. 
#On obient le même résultats en faisant x.reverse()
x_rev = x.reverse()
x_rev
```


```python
Avec une liste à plusieurs dimensions, l’indiçage se fait à plusieurs niveaux. Par example:
```


```python
x=[[1,2,3],[2,3,4],[3,4,5]]
print(x)
print("================================================")
print('\t')


print(x[0]) # renvoie le premier élément-liste [1,2,3]
print("================================================")
print('\t')



print(x[0][0]) # renvoie le premier élément du premier élément-liste c'est-à-dire 1
print("================================================")
print('\t')



print(x[2]) # renvoie [ 3,4,5]
print("================================================")
print('\t')


print(x[2][1]) # renvoie 2
print("================================================")
print('\t')





print(x[1:]) # renvoie [[2, 3, 4], [3, 4, 5]]
print("================================================")
print('\t')


print(x[1:][0]) # renvoie [2, 3, 4]
print("================================================")
print('\t')


print(x[-1]) # renvoie 3, 4, 5]
print("================================================")
print('\t')



print(x[1][:2]) # renvoie [2, 3]
print("================================================")
print('\t')


x[1][1:] # renvoie [3, 4]
```

### La fonction range()

Les séquences de valeurs sont des variables très fréquemment rencontrées dans les
programmes python. Elles correspondent à un ensemble de valeurs successives et ordonnées dont les valeurs peuvent être extraites comme une liste. Les séquences de valeurs sont
générées en utilisant la fonction `range()`. Exemple :


```python
x = range(10) # Crée une séquence de valeurs entières allant de 0 à 9
print(x)
print("================================================")
print('\t')



x = range(2, 10) # Crée une séquence de valeurs entières allant de 2 à 9
print(x)
print("================================================")
print('\t')


x = range(1, 10, 2) # Crée une séquence de valeurs entières allant de 2 à 9 avec un pas de 2. Il renvoie alors 1, 3, 5, 7 et 9
x
```


```python
Pour afficher les valeurs générées, on peut utiliser la fonction list() ou la fonction tuple() telles
que :

```


```python
x = range(10)

print(list(x)) # renvoie une liste :valeurs entre crochets [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

print(tuple(x)) # renvoie un tuple : valeurs entre parenthèses (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
```

### Les opérations sur les listes 
Une liste étant définie, on peut réaliser plusieurs opérations visant à modifier la structure de la
liste ou les éléments qui le constituent.

 - Pour connaitre le nombre d’éléments d’une liste, on utilise la fonction `len()`. Exemple : soit la
liste x définie comme suit :
```python 
   x = ['lundi', 'mardi', 'mercredi', 1800, 20.357, 'jeudi', 'vendredi']
```
Pour connaitre la longueur de x (nombre d’éléments de x), on fait :
 ```python
    print(len(x)) # cela renvoie 7
 ```   
 
 - On peut additionner deux listes pour en former une seule en utilisant l’opérateur `+` qui permet
de concaténer les listes en questions:
```python 
   x = ['girafe','tigre']
   y = ['singe','souris']
   z = x + y
   print(z) # renvoie ['girafe', 'tigre', 'singe', 'souris']
```
 - On peut démultiplier les éléments d’une liste en utilisant l’opérateur de multiplication `*`
 ```python
    x = ['girafe', 24, 18 , 'tigre', 2400, 150 ]
    y = x*3
    print(y) # renvoie ['girafe', 24, 18, 'tigre', 2400, 150, 'girafe', 24, 18, 'tigre', 2400, 150, 'girafe', 24, 18, 'tigre', 2400, 150]
 ```   
 
 - Il est possible de modifier un élément particulier d’une liste en se servant de son indice.
 ```python
    x = ['lundi', 'mardi', 'mercredi', 1800, 20.357, 'jeudi', 'vendredi']
    x[3] = x[3]+100
    print(x) # renvoie ['lundi', 'mardi', 'mercredi', 1900, 20.357,'jeudi', 'vendredi']
    
    x[6] = x[6]+ ' saint' # attention à l’espace dans ' saint' sinon on aura vendredisaint.
    print(x) # renvoie ['lundi', 'mardi', 'mercredi', 1900, 20.357, 'jeudi', 'vendredi saint']

 ```
 
 - Il est possible d’ajouter des nouveaux éléments en plus des éléments initiaux. Pour cela, on
utilise la fonction `append().`
 ```python
    x = ['lundi', 'mardi', 'mercredi’, ‘jeudi', 'vendredi']
    x.append( ' samedi ')
    x.append( ' dimanche ')
    print(x)

 ```
 Comme on peut le constater la fonction append() ne peut ajouter qu’un seul
élément à une liste à la fois. C’est pourquoi, on peut avoir recours à la fonction extend()
lorsque l’on veut ajouter plusieurs éléments en même temps. Exemple :
 ```python
    x = ['lundi', 'mardi', 'mercredi’, ‘jeudi', 'vendredi']
    x.extend(['samedi','dimanche'])
    print(x)

 ```

****
A titre d'approfondissement, etudier les methodes suivantes et comment elles operent sur les listes:
`insert()`, `remove()`,`delete()`,`index()`,`count()`,`join()`,`zip()`.
***

<left> <b> <span style="color:brown;">Compte tenu du fait que leur utilisation est assez peu commune, nous ne traiterons pas, dans ce cours, des objets `tuple` et `set`. La breve presentation donnee plus haut est relativement suffisante et le lecteur qui en a expressement besoin pourra consulter la documentation abondante sur la toile. </span> </b></left>

Nous pouvons neanmois, dire que qu'un `set` est une collection itérable non ordonnée d’éléments hachables distincts et que les operations mathematiques classiques sur les ensembles peuvent etre faites sous Python, par example:

<center>
    <img src="images/set.png" width="20%></center>
                              
                   

```python
   X, Y = set(’abcd’), set(’sbds’)
   print("X =", X) # X = {’a’, ’c’, ’b’, ’d’}
   print("Y =", Y) # Y = {’s’, ’b’, ’d’} : un seul élément ’s’      
    
   print('c' in X)  # True
   print('a'in Y)   # False
   print(X - Y)     # {’a’, ’c’}
   print(Y - X)     #{’s’}
   print(X | Y)     # {’a’, ’c’, ’b’, ’d’, ’s’}
   print(X & Y)     #{’b’, ’d’}     
                              
```          

## Dictionnaires

Dans une conception pythonienne, un dictionnaire (encore appelé bibilothèque) est une
collection d’objets définie selon le principe `clé-valeur`. Contrairement aux listes, dans lesquels chaque élément est
identifié à partir de son indice, dans un dictionnaire, les éléments sont identifiés à travers des
clés (qui se présente généralement sous forme de chaîne de caractère). 


```python
x = {'nom':'Jean', 'age':25, 'poids':70, 'taille':1.75}
y = {'Jean':[25,70,1.75],'Paul':[30,65,1.80],'Pierre':[35,75,1.65] }
z = {'Jean':(25,70,1.75),'Paul':(30,65,1.80),'Pierre':(35,75,1.65) }
k = {'nom':'Jean','biométrie':[25,70,1.75],'score':(12,17,15),'rang':25}
```

Les quatre variables ci-dessus représentent **quatre** manières typiques de définir un
dictionnaire. La variable x est un dictionnaire dont les clés sont **nom, age, poids et taille**. Les valeurs
respectives correspondantes sont **Jean, 25, 70** et **1.75**. Dans la définition
de x, il à est noter qu' à chaque clé correspond une valeur unique.
Toutefois, il arrive très fréquemment d’associer plusieurs valeurs à une seule clé. C’est le cas du dictionnaire y.

###  Les opérations sur les dictionnaires

 - Pour accéder aux éléments d’un dictionnaire on se sert des clés. La méthode `keys()` renvoie la liste des clés 
   du dictionnaire et a methodes `values()` les valeurs.
  ```python 
     X= {'nom':'Jean', 'age':25, 'poids':70, 'taille':1.75}
     print(X.keys())  # renvoie ['nom', 'age', 'poids', 'taille']
     print(X.values()) # renvoie ['Jean',25,70,1.75]   
     print(X['nom'])  # renvoie 'Jean"   
     x = {' Jean ':[25,70,1.75],' Paul ':[30,65,1.80],' Pierre ':[35,75,1.65] }
     print(x['Jean']) #renvoie [25, 70, 1.75]
     print(x['Jean'][0]) #renvoie 25
     print(x['Jean'][0 :2]) #renvoie [25, 70]   

  ```
  
 - Ajout ou modification de clés ou de valeurs: on peut modifier un dictionnaire soit en modifiant les clés et les valeurs déjà existantes ou en ajouter des nouvelles. On peut également supprimer des valeurs mais aussi des clés.
  
```python
  x= {} #  Crée un dictionnaire vide. On pouvait aussi utiliser x=dict()
  x['nom'] = 'Jean' # ajoute la clé-valeur nom et Jean au dictionnaire x initial
  x['biométrie']= [25,70,1.75] # ajoute la clé-valeur biométrie et [25,70,1.75] au dictionnaire x
  x['biométrie']= [30,70,1.80] # modifie les valeurs de la clé biométrie en effectuant une nouvelle définition
  x['biométrie'][0]= 2 # modifie l’élément d’indice 0 de la liste de valeur qui correspond à la clé biométrie    (préalabelemnt définie)

   Y = {' Jean ':[25,70,1.75],' Paul ':[30,65,1.80],' Pierre ':[35,75,1.65] }
   del Y['Jean'] # Supprime la clé Jean toutes les valeurs correspondantes
   del Y['Jean'][0] # Supprime l’élément d’indice 0 dans la séquence de valeur correspondant à la clé Jean. Pour une clé à une seule valeur, on utilise del x['nomCle'] où nomCle est le nom de la clé qui a la valeur unique. 

```
   
 - Pour renommer une clé dans un dictionnaire, on utilise la fonction pop() telle que définie dans
l’exemple suivant :

```python
x = {' Jean ':[25,70,1.75],' Paul ':[30,65,1.80],' Pierre ':[35,75,1.65] }
x['John'] = x.pop('Jean') # On renomme la clé Jean comme John
print(x)

```

[Contenu](../Contenu.html) \| [Précédent (2.2 Objets itérables ou conteneurs)](../Jours_02/3_Chaînes-de-caractères.html)

