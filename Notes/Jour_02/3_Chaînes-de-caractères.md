---
layout: default
title: Chaînes de caractères
---


[Contenu](../Contenu.html) \| [Suivant (2.1. Objets itérables ou conteneurs)](../Jours_02/4_Objets-itérables-ou-conteneurs.html)



<a href="https://colab.research.google.com/github/ai-technipreneurs/programmation-python-pratique/blob/master/3_Cha%C3%AEnes-de-caract%C3%A8res.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

****

# <center> <b> <span style="color:orange;"> Atelier 3P </span> </b></center>

## <center> <b> <span style="color:green;">Programmation Python Pratique</span> </b></center>

<center>
    <a href="https://github.com/ai-technipreneurs" ><img src="https://avatars.githubusercontent.com/u/83169416?v=4" style="float:center; max-width: 650px; display: inline" alt="IMSP"/> </a>
    </center>

### <center> <b> <span style="color:blue;">  Chaînes de caractères </span> </b></center>

#### <left> <b> <span style="color:brown;">Instructeur : </span> </b></left>[ai-technipreneurs](https://github.com/ai-technipreneurs)

****

Cette section a pour but de presenter les`chaînes de caractères`, de passer en revues certaines les opérations les plus couramment rencontrées notamment dans les opérations
de traitement de texte.

Les chaînes de caractères ne sont pas des objets en tant que tels dans un programme python.
Ce sont plutôt des séquences de valeurs (tout comme les données de type numériques) qui
servent à définir les objets proprement dits comme les listes, les tuples -dont nous parlerons plus tard-, etc... Tout comme dans le cas des opérations mathématiques réalisables les données numériques (addition,
multiplication, division, etc..), il existe également un ensemble d’opérations servant à la manipulation des chaînes de caractères. 

##  <left> <b> <span style="color:orange;"> 0. Définition d’une variable de type chaîne de caractères</span> </b></left>

Une variable chaîne de caractère se définit de manière classique par une assignation directe en
utilisant le symbole de l’égalité (comme cela a été discutée dans la section sur la création de
variable). La seule particularité des variables caractères par rapport aux variables numériques est que leurs valeurs doivent être spécifiées entre guillemets lors de l’assignation. Les trois
exemples ci-dessous sont des illustrations.


```python
ch1 = 'Seriez-vous à la réunion de ce soir ?'
ch2 = '"Oui", répond-il.'
ch3 = "D’accord, j'apprécierai bien."
ch4 = """Cette phrase est une longue chaîne de caractères contenant
tous les types de guillemets: " ' « » mais aussi de nombreux
caractères spéciaux."""
print(ch1)
print("================================================")
print('\t')



print(ch2)
print("================================================")
print('\t')


print(ch3)
print("================================================")
print('\t')


print(ch4)
```

    Seriez-vous à la réunion de ce soir ?
    ================================================
    	
    "Oui", répond-il.
    ================================================
    	
    D’accord, j'apprécierai bien.
    ================================================
    	
    Cette phrase est une longue chaîne de caractères contenant
    tous les types de guillemets: " ' « » mais aussi de nombreux
    caractères spéciaux.


Ces quatre exemples montrent différentes utilisations des guillemets lors de la définition d’une
variable en chaines de caractères.

 - Dans le premier exemple (`ch1`), on utilise des guillemets simples car il n’y a aucun inconvénient
à cela compte tenu de la chaîne spécifiées. On pouvait aussi utiliser des guillemets doubles.
 - Dans le deuxième exemple (`ch2`), on utilise des guillemets simples car la chaînes spécifiée
contient déjà des guillemets doubles comme valeur.
 - Dans le troisième exemple (`ch3`), on utilise les guillemets doubles car le texte contient des
apostrophes qui sont en fait des guillemets simples.
 - Dans le quatrième exemple (ch4), on utilise les guillemets triples car le texte contient non
seulement des guillemets simples, apostrophes et les guillemets doubles mais s’étend sur
plusieurs lignes. Dans ces conditions, l’utilisation des guillemets triples s’impose.

##  <left> <b> <span style="color:orange;"> 1. Indiçage des chaînes et sous-chaînes (*Slicing*) </span> </b></left> 

###  <left> <b> <span style="color:brown;"> 1.0 Indiçage des chaînes et sous-chaînes (*Slicing*) </span> </b></left> 
 

Une chaîne de caractère est une séquence de valeurs ordonnées et indicées. Ce qui signifie
qu’on peut accéder à chacun des éléments de la séquence en spécifiant son indice comme dans
les liste.
Aussi des portions d’une chaîne peuvent être extraites en utilisant des *slices* (« tranches »), de notation
générique `[start=0]:[stop=len][:step=1]`. L’indexation en python commence à 0 : le 1er élément d’une liste est l’élément n°0, le
2nd est le n°1, etc. Les n éléments d’une liste sont donc indexés de *0* à *n-1*. 
Les exemples ci-dessous sont des illustrations.

```python
ch="Christelle"
ch[0] # renvoie 'C'
ch[2] # renvoie 'r'
ch[-1] # renvoie 'e', le dernier élément de ch
ch[:6] # Renvoie 'Christ'
ch[6 :] # Renvoie 'elle'
ch[0:10:2] # renvoie 'Crsel'
```

Les éléments d’une chaîne de caractères ne sont pas définie en fonction des mots
séparés par des espace mais par les caractères qui le constituent. En effet, même si la chaîne
avait été constituée par une phrase de plusieurs mots, les indiçages se feront uniquement sur la
base des caractères qui forment la longue chaînes. Exemple :
```python
    ch="Ceci est une chaîne de plusieurs mots"
    ch[1] # renvoie 'e'
    ch[4] # renvoie ' ', l’espace vide qui sépare Ceci et est.
    ch[0:4] # renvoie 'Ceci'
```

<left> <b> <span style="color:brown;">On peut agir sur une chaîne (et plus généralement sur une séquence) en utilisant des
fonctions (notion procédurale) ou des méthodes (notion objet). Nous en discutons plus bas.</span> </b></left> 

###  <left> <b> <span style="color:brown;"> 1.1  Longueur d’une chaîne de caractères </span> </b></left> 


Pour déterminer la longueur d’une chaîne, on utilise la fonction `len()`.


```python
ch="Ceci est une chaîne de plusieurs mots"
print(len(ch)) # renvoie 37; La chaîne ch est constituée de 37 caractères (espace compris).
```

    37


###  <left> <b> <span style="color:brown;"> 1.2  Addition de chaînes de caractères (**concaténation**) </span> </b></left> 

L’addition de chaînes de caractères est la juxtaposition de chaînes de caractères les unes à la
suite des autres pour une former une chaîne de caractères unique. Il s’agit de la **concaténation**.
Pour réaliser cette opération, on utilise le symbole + entre les noms des variables chaînes. Le
résultat obtenu est ensuite assignée à une nouvelle variable. Exemples :


```python
x = "Un petit pas pour l'homme,"
y = "un grand pas pour l'humanité"
z = x + y
print(z) # renvoie 'Un petit pas pour l'homme, un grand pas pour l'humanité'
```

    Un petit pas pour l'homme,un grand pas pour l'humanité


Attention toutefois dans l’utilisation de l’opérateur de concaténation lorsqu’il s’agit d’associer
une valeur numérique à une chaîne pour former une chaîne unique. Exemple:
```python
    x = 'Le prix du stylo est'
    y = 5
    z = 'euros'

```
On veut concaténer x, y et z de sorte à obtenir la phrase 'Le prix du stylo est 5 euros'.
Dans cette situation, on ne peut pas faire x+y+z car y est de type numérique. Il faut d’abord
convertir celle-ci en utilisant la fonction str(). Ainsi on a :
    


```python
x = 'Le prix du stylo est'
y = 5
z = 'euros'
ch = x+str(y)+z
print(ch) # renvoie 'Le prix du stylo est5euros'
```

    Le prix du stylo est5euros


On voit que est 5 euros est sans espace, on peut alors modifier l’opération de concaténation en
insérant des espace entre les valeurs. Ainsi, on a :



```python
ch = x + ' '+ str(y) + ' '+ z
print(ch) # renvoie Le prix du stylo est 5 euros
```

    Le prix du stylo est 5 euros


Ce résultat pouvait aussi être obtenu par une expression directe telle que :



```python
ch = 'Le prix du stylo est'+ ' '+ '5' + ' '+ 'euros'
print(ch) # renvoie 'Le prix du stylo est 5 euros'
```

    Le prix du stylo est 5 euros


###  <left> <b> <span style="color:brown;"> 1.3 Méthodes </span> </b></left> 

Les chaînes de caractères disposent de [nombreuses fonctionnalités](https://docs.python.org/2/library/stdtypes.html#string-methods) – appelées `méthodes` en POO
(Programmation Orientée Objet) – facilitant leur manipulation.
La fonction `dir()` liste toutes les méthodes des chaînes. Au nombres de celles-ci, les plus courantes sont 
`upper()`, `lower()`, `capitalize()`, `find()`, `replace()`,`count()`,`startwith()`,`endwith()`, `in`.


```python
help(titre.replace)
```

    Help on built-in function replace:
    
    replace(old, new, count=-1, /) method of builtins.str instance
        Return a copy with all occurrences of substring old replaced by new.
        
          count
            Maximum number of occurrences to replace.
            -1 (the default value) means replace all occurrences.
        
        If the optional argument count is given, only the first count occurrences are
        replaced.
    



```python
# Tout en majuscules
mot="Bonjour"
mot=mot.upper()
print(mot)
```

    BONJOUR



```python
#Tout en minuscules
mot="Bonjour"
mot=mot.lower()
print(mot)
```

    bonjour



```python
# Seule la première lettre en majuscule
mot="bonJOUR"
mot=mot.title()
print(mot)
```

    Bonjour



```python
enfant, peluche = "Calvin", 'Hobbes' # Affectation mutiple



titre = enfant + ' et ' + peluche; titre # +: Concaténation de chaînes
print(titre)
print("================================================")
print('\t')





print(titre.replace('et', '&')) # Remplacement de sous-chaînes 'Calvin & Hobbes'
print("================================================")
print('\t')



' & '.join(titre.split(' et ')) # Découpage (split) et jonction (join)
print("================================================")
print('\t')




print('Hobbes' in titre) # in: Test d'inclusion
print("================================================")
print('\t')



print(titre.find("Hobbes")) # str.find: Recherche de sous-chaîne


print(titre.center(30, '-')) # '-------Calvin et Hobbes-------'


dir(str) # Liste toutes les méthodes des chaînes
```

    Calvin et Hobbes
    ================================================
    	
    Calvin & Hobbes
    ================================================
    	
    ================================================
    	
    True
    ================================================
    	
    10
    -------Calvin et Hobbes-------





    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__getnewargs__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mod__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__rmod__',
     '__rmul__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'capitalize',
     'casefold',
     'center',
     'count',
     'encode',
     'endswith',
     'expandtabs',
     'find',
     'format',
     'format_map',
     'index',
     'isalnum',
     'isalpha',
     'isascii',
     'isdecimal',
     'isdigit',
     'isidentifier',
     'islower',
     'isnumeric',
     'isprintable',
     'isspace',
     'istitle',
     'isupper',
     'join',
     'ljust',
     'lower',
     'lstrip',
     'maketrans',
     'partition',
     'replace',
     'rfind',
     'rindex',
     'rjust',
     'rpartition',
     'rsplit',
     'rstrip',
     'split',
     'splitlines',
     'startswith',
     'strip',
     'swapcase',
     'title',
     'translate',
     'upper',
     'zfill']



###  <left> <b> <span style="color:brown;"> 1.4 Formatage </span> </b></left> 

Il arrive très souvent que l’on veuille récupérer la valeur d’une variable et l’intégrer à une chaine
de caractères pour former une nouvelle chaine de caractères utilisable à d’autres fins.
Soit
la variable prix définie comme suit
```python prix=2
```
Nous voulons afficher un message de genre 
`"Le prix du stylo est de 2 euros"`.

Le but de
l’opération de l’opération de formatage de faire afficher la valeur d’une variable à l’intérieur
d’une chaine de caractères. Pour cela, on dispose de trois principales méthodes:
  - l'utilisation de l'opérateur de concaténation "+ "
  - l'utilisation de l’opérateur de formatage "%" %
  - l'utilisation de la fonction format "{}".format().
  
Nous montrerons juste un example avec la méthode `str.format()`.
Le système de [formatage](https://docs.python.org/2/library/string.html#formatstrings) permet un contrôle précis de la conversion de variables en chaînes de caractères.
Il s’appuie essentiellement sur la méthode `str.format()`:


```python
print("{nom} a {age} ans".format(nom='Calvin', age=6)) #'Calvin a 6 ans'
print("================================================")
print('\t')


print("{} a {} ans".format('Calvin', 6)) # Raccourci  'Calvin a 6 ans'
print("================================================")
print('\t')



pi = 3.1415926535897931
print("{x:f} {x:.2f} {y:f} {y:g} ".format(x=pi, y=pi*1e9)) # '3.141593 3.14 3141592653.589793 3.14159e+09'
```

    Calvin a 6 ans
    ================================================
    	
    Calvin a 6 ans
    ================================================
    	
    3.141593 3.14 3141592653.589793 3.14159e+09 


[print](https://docs.python.org/2/library/functions.html#print) affiche à l’écran (plus spécifiquement la sortie standard) la conversion d’une variable en chaîne
de caractères :


```python
print("Calvin and Hobbes\nScientific progress goes 'boink'") # Calvin and Hobbes Scientific progress goes 'boink'
```

    Calvin and Hobbes
    Scientific progress goes 'boink'



```python
print(("{0} fois {1} font {2} ").format(3, 4, 3*4)) # Formatage et affichage
#3 fois 4 font 12
#Un petit exercice dans cette section est d'afficher une table de multiplication.
```

    3 fois 4 font 12 


Un point que nous n'aborderons pas dans le present calepin mais qu'il serait bon de lire est l'utilisation de l’opérateur **antislash** `\`.

En concluant cette section, nous faisons mention de l'etudes des expressions régulières (regex ou re) qui sera l'objet d'un expose. Nous pouvons, a titre de guide, dire que les expressions régulières
sont des extensions de la fonction str() qui permettent de réaliser des opérations plus
complexes de définition de motifs que ne permettent des fonction str().

**Remarque:** Il faut faire une remarque importante concernant la
différence entre une valeur de type caractère et une valeur de type alphabétique. En effet, une
valeur alphabétique est toujours une chaîne de caractère alors qu’une chaîne de caractère n’est
pas nécessairement une valeur alphabétique. Sous python, une valeur caractère est toujours
exprimée entre guillemets (simple, double ou triple) alors qu’une valeur numérique est
exprimée sans guillemets. On distingue deux principaux types de données : les données
numériques et les données en caractères. Il faut noter qu’une valeur numérique exprimée entre
guillemets est automatiquement traitée comme une valeur caractère même si elle n’est pas
alphabétique. Il est important de garder à l’esprit ces détails lors de la manipulation des
séquences de valeurs sous python (voir exemple ci-dessous):

```python
    x = 12 # x est une variable numérique
    y = "12" # y est une chaîne de caractère formée par une chiffres
    z = "mon texte" # z est une chaîne de caractères formée de valeurs alphabétiques
    k = "Ce stylo coûte 5 euros" # k est une chaîne de caractères formée de valeur alphanumérique
```

Pour plus de détails sur le traitement des chaines de caractères consulter [cette page.](http://www.tutorialspoint.com/python/python_strings.htm)

[Contenu](../Contenu.html) \| [Suivant (2.1. Objets itérables ou conteneurs)](../Jours_02/4_Objets-itérables-ou-conteneurs.html)


