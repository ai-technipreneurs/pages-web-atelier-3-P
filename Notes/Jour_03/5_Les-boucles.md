---
layout: default
title: Les Boucles
---



[Contenu](../Contenu.html) \| [Suivant (3.1. Fonctions et Modules)](../Jours_03/6_Fonctions-et-Modules.html)



<a href="https://colab.research.google.com/github/ai-technipreneurs/programmation-python-pratique/blob/master/5_Les-boucles.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

****

# <center> <b> <span style="color:orange;"> Atelier 3P </span> </b></center>

## <center> <b> <span style="color:green;">Programmation Python Pratique</span> </b></center>

<center>
    <a href="https://github.com/ai-technipreneurs" ><img src="https://avatars.githubusercontent.com/u/83169416?v=4" style="float:center; max-width: 650px; display: inline" alt="IMSP"/> </a>
    </center>

### <center> <b> <span style="color:blue;">Boucles  </span> </b></center>

#### <left> <b> <span style="color:brown;">Instructeur : </span> </b></left>[ai-technipreneurs](https://github.com/ai-technipreneurs)

****

 Un script Python est formé d’une suite d’instructions exécutées en séquence de
haut en bas. Chaque ligne d’instructions est formée d’une ou plusieurs lignes physiques qui
peuvent être continuées par un antislash `\` ou un caractère ouvrant `[({` pas encore
fermé. Cette exécution en séquence peut être modifiée pour choisir ou répéter des portions de code. C’est l’objet de ce calepin.


## Les instructions en boucle

Sous python, on distingue deux principales catégories d’instructions en boucles : les
instructions en boucle **« while... »** et les instructions en boucle **« for... in... »**.

### Les boucles while

Après avoir introduit les structures de choix, nous nous intéressons aux structures de répé-
tition : ces structures permettent d’exécuter à plusieurs reprises un bloc d’instructions. Ces
répétitions se classent en deux catégories :
  
  - les répétitions conditionnelles : le bloc d’instructions est à répéter autant de fois qu’une
condition est vérifiée.

  - les répétitions inconditionnelles : le bloc d’instructions est répété un nombre donné de
fois.

La syntaxe générale de la définition des instructions en boucle while se présente comme suit :

```python
   Initialisation de la variable d’incrémentation
   while condition :
        bloc_instructions
        incrémentation

```

Comme dans la
structure if, la condition est d’abord évaluée et si elle vraie, le bloc d’instructions est exécuté.
Mais ici avec la clause while après exécution du bloc d’instruction, la condition est évaluée à
nouveau. Cette exécution se répète jusqu’à ce que la condition devienne fausse. C’est pourquoi
il n’est nécessaire de définir une variable d’incrémentation dont la valeur se modifie après
chaque exécution de sorte que la condition puisse être fausse à partir d’une certaine valeur.
Cette incrémentation est nécessaire pour éviter que les instructions soient indéfiniment
évaluées créant ainsi une boucle infinie (ou boucle folle). Une telle situation nécessite alors un
arrêt forcé de l’exécution du programme.


```python
x = 1 # Initialisation de la variable x
while (x < 10):
    print('La valeur de x est ', a)
    x = x + 1 # Incrémentation de la variable x
```

    La valeur de x est  150
    La valeur de x est  150
    La valeur de x est  150
    La valeur de x est  150
    La valeur de x est  150
    La valeur de x est  150
    La valeur de x est  150
    La valeur de x est  150
    La valeur de x est  150



```python
fruits = ['pommes', 'oranges', 'fraises', 'bananes']
i = 0
while i < len(fruits):
    print (fruits[i])
    i = i + 1
```

    pommes
    oranges
    fraises
    bananes


### Les instructions en boucle « for... in... »

Lorsque l’on souhaite répéter un bloc d’instructions un nombre déterminé de fois, on peut
utiliser un *compteur actif*, c’est-à-dire une variable qui compte le nombre de répétitions et
conditionne la sortie de la boucle **while**. C’est le cas de l’exemple suivant où l’on définit une
fonction qui prend en argument un entier `n` et affiche `n` fois le même message.

Pour effectuer une telle répétition, on dispose d’une structure de répétition nous économisant
d’une part l’initialisation du compteur `( i = 0 )`, et d’autre part son incrémentation `( i += 1 )`:
c’est la structure introduite par le mot-clé `for`.

La syntaxe générale de la définition d’instructions en boucle for... in... est la suivante :

```python
   for element in sequence_de_valeurs :
        bloc instructions
```        


```python
n = 5
for i in range(n):
    print('Je me répète {} fois.' ' (i={})'.format(n, i))
```

    Je me répète 5 fois. (i=0)
    Je me répète 5 fois. (i=1)
    Je me répète 5 fois. (i=2)
    Je me répète 5 fois. (i=3)
    Je me répète 5 fois. (i=4)



```python
# Instruction dans une boucle « for.. in ... » simple
for i in range(1,11) :
    print(i)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10



```python
# Boucle « for.. in... » sur une chaine de caractères
listch = "Hello world"
for i in listch :
    print ( i )
```

    H
    e
    l
    l
    o
     
    w
    o
    r
    l
    d



```python
# Combinaison d’une boucle « for...in ... » et d’une clause « if »
listnb = [4, 5, 6]
for i in listnb:
    if i == 5:
        print("La condition est vérifiée pour l’élement", i)
    else :
        print("La condition ,n’est pas vérifiée pour l’élément", i)
```

    La condition ,n’est pas vérifiée pour l’élément 4
    La condition est vérifiée pour l’élement 5
    La condition ,n’est pas vérifiée pour l’élément 6



```python
# Combinaison d’une boucle « for...in ... » et d’une clause « if »
mych = "Hello World"
for lettre in mych :
    if lettre in "AEIOUYaeiouy":
        print ('La lettre', lettre, 'est une voyelle')
    else :
        print ('La lettre', lettre, 'est une consonne')
```

    La lettre H est une consonne
    La lettre e est une voyelle
    La lettre l est une consonne
    La lettre l est une consonne
    La lettre o est une voyelle
    La lettre   est une consonne
    La lettre W est une consonne
    La lettre o est une voyelle
    La lettre r est une consonne
    La lettre l est une consonne
    La lettre d est une consonne



```python
# Combinaison d’une boucle « for...in ... » et d’une clause « if »
# On tient compte de caractere `espace`
mych = "Hello World"
for lettre in mych :
    if lettre in "AEIOUYaeiouy":
        print ('La lettre', lettre, 'est une voyelle')
    elif lettre == " " :
        print ("Il s'agit surement d'un espace")
    else :
        print ('La lettre', lettre, 'est une consonne')
```

    La lettre H est une consonne
    La lettre e est une voyelle
    La lettre l est une consonne
    La lettre l est une consonne
    La lettre o est une voyelle
    Il s'agit surement d'un espace
    La lettre W est une consonne
    La lettre o est une voyelle
    La lettre r est une consonne
    La lettre l est une consonne
    La lettre d est une consonne



```python
fruits = ['mangue', 'orange', 'pomme', 'banane']
couts = [49, 99, 15, 32]
for fruit, prix in zip(fruits, couts):
    print("Une",fruit, "coute", prix, "frs CFA.")    
```

    Une mangue coute 49 frs CFA.
    Une orange coute 99 frs CFA.
    Une pomme coute 15 frs CFA.
    Une banane coute 32 frs CFA.



```python
couts = {'mangue': 49, 'orange': 99, 'pomme': 15, 'banane': 32}
for fruit, prix in couts.items():
    print ("Une",fruit, "coute", prix, "frs CFA.")
```

    Une mangue coute 49 frs CFA.
    Une orange coute 99 frs CFA.
    Une pomme coute 15 frs CFA.
    Une banane coute 32 frs CFA.


### Liste par compréhension
Pour créer des listes, Python fournit une facilité syntaxique particulièrement agréable, à savoir les listes (définies) par compréhension (en anglais, *list-comprehensions*). Elles permettent
de générer des listes d’une manière très concise, sans avoir à utiliser de boucles si les éléments doivent
êtres testés ou traités avant d’être intégrés dans la liste.

La syntaxe pour définir une liste par compréhension est proche de celle utilisée en mathématiques pour définir un ensemble par compréhension :

L’expression est de la forme :
    
                    [expression for expression in sequence [`if` test]] 


```python
liste = [2, 4, 6, 8, 10]


print([3*x for x in liste])
print("================================================")
print('\t')



print([[x, x**3] for x in liste])
print("================================================")
print('\t')



print([3*x for x in liste if x > 5] )# on filtre avec une condition
print("================================================")
print('\t')



print([3*x for x in liste if x**2 < 50]) # idem
print("================================================")
print('\t')


liste2 = list(range(3))
print([x*y for x in liste for y in liste2])

```

    [6, 12, 18, 24, 30]
    ================================================
    	
    [[2, 8], [4, 64], [6, 216], [8, 512], [10, 1000]]
    ================================================
    	
    [18, 24, 30]
    ================================================
    	
    [6, 12, 18]
    ================================================
    	
    [0, 2, 4, 0, 4, 8, 0, 6, 12, 0, 8, 16, 0, 10, 20]



```python
# Voici par exemple, un moyen efficace d’obtenir la liste des années bissextiles dans un intervalle donné :
bissextile = [b for b in range(2000, 2100) if (b % 4 ==0 and b % 100 != 0) or (b % 400 == 0)]
```

### Les instructions break et continue dans une clause « while... » ou « for ... in...»
Les mots réservés `break` et `continue` sont utilisés pour modifier le comportement d'une boucle
« for...in » ou d'une boucle « while... ». L’instruction `break` permet d’arrêter l’évaluation de la
boucle et l’exécution des instructions pour sortir prématurément de la boucle même la
condition principale définissant la boucle reste encore vraie. Et l’instruction `continue` permet de
suspendre l’exécution des instructions lorsque la condition principale est vérifiée. Les exemples
ci-dessous sont des illustrations.

Au départ, cette boucle for vise à afficher tous éléments de la séquence de valeurs allant de 1 à 4. Mais avec l’instruction break définie à l’intérieur de la clause if, la boucle for est stoppée
lorsque i devient supérieur à 2.


```python
# Boucle avec l’instruction break
for i in range(5):
    if i > 2:
        break
print (i)
```




```python
Au départ, cette boucle for est conçue pour afficher tous éléments de la séquence de valeurs
allant de 1 à 4. Mais avec l’instruction continue définie à l’intérieur de la clause if, l’instruction
print() n’est pas exécutée lorsque i prend la valeur 2. Mais elle est exécutée pour toutes les
autres valeurs de la séquence.
```


```python
# Boucle avec l’instruction continue
for i in range(5):
    if i == 2:
        continue
    print (i)
```

L’instruction <b> <span style="color:pink;"> break </span> </b>

L’instruction <b> <span style="color:pink;"> break </span> </b> permet de « casser » l’exécution d’une boucle (while ou for). Elle fait sortir de la boucle et passer à l’instruction suivante.




Exemple


```python
for i in range(10):
    print("debut iteration", i)
    print("bonjour")
    if i == 2:
        break
    print("fin iteration", i)
print("apres la boucle")
```

    debut iteration 0
    bonjour
    fin iteration 0
    debut iteration 1
    bonjour
    fin iteration 1
    debut iteration 2
    bonjour
    apres la boucle


<b> <span style="color:red;"> Note: </span> </b>
Dans le cas de boucles imbriquées, l’instruction break ne fait sortir que de la boucle la plus interne.



Remarque : équivalent du  <b> <span style="color:red;"> do ... while (faire ... tant que)</span> </b>

Dans de nombreux langages, il existe une instruction do…while qui permet de créer une boucle pour laquelle on ne connaît pas à l’avance le nombre de répétition, mais qui doit s’exécuter au moins une fois. Cette instruction n’existe pas en Python, mais on peut facilement reproduire son fonctionnement de la façon suivante :


```python
while True:
    n = int(input("donnez un entier > 0 : "))
    print("vous avez fourni", n)
    if n > 0:
        break
print("reponse correcte")
```

L’instruction  <b> <span style="color:pink;"> continue </span> </b>

L’instruction <b> <span style="color:pink;"> continue </span> </b> permet de passer prématurément au tour de boucle suivant. Elle fait continuer sur la prochaine itération de la boucle.

Exemple


```python
for i in range(4):
    print("debut iteration", i)
    print("bonjour")
    if i < 2:
        continue
    print("fin iteration", i)
print("apres la boucle")
```

    debut iteration 0
    bonjour
    debut iteration 1
    bonjour
    debut iteration 2
    bonjour
    fin iteration 2
    debut iteration 3
    bonjour
    fin iteration 3
    apres la boucle


[Contenu](../Contenu.html) \| [Suivant (3.1. Fonctions et Modules)](../Jours_03/6_Fonctions-et-Modules.html)



