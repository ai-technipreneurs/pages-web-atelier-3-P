---
layout: default
title: Variables, Types et Opérations
---




****

Dès que l’on possède des *types de données*, on a besoin des *variables* pour stocker les
    données.
    En réalité, Python n’offre pas la notion de variable, mais plutôt celle de *référence d’objet*. Tant
    que l’objet n’est pas modifiable (comme les entiers, les flottants, etc.), il n’y a pas de différence
    notable. Dans le présent calepin, nous discutons les grandes lignes atour de l'utilisation des variables sous Python.

#  <left> <b> <span style="color:orange;"> 0. Définir une variable</span> </b></left>

Sous Python, une variable est un objet de programmation permettant de stocker une
information en mémoire de la machine en attribuant un nom symbolique. Une variable est
définie en utilisant l’opérateur mathématique `=` soit par assignation directe de sa valeur, ou par
une assignation à partir de la valeur d’une autre variable. Exemples :

## <left> <b> <span style="color:brown;"> 0.0 Assignation directe</span> </b></left>


```python
x = 86 # définit la variable nommée x et lui assigne la valeur 86
```


```python
y = 4.8134 # définit la variable nommée y et lui assigne la valeur 4.8134

```


```python
salutation = "Comment allez-vous ?" # Définit la variable nommée salutation et lui assigne la valeur " Comment allez-vous ?"
```

## <left> <b> <span style="color:brown;"> 0.1 Affichage</span> </b></left>

Pour afficher les valeurs des trois variables définies, on utilise la fonction `print()`-sur laquelle nous reviendrons quand nous parlerons des *objets fonctions sous Python*.


```python
print(x)
```

    86



```python
print(y)
```

    4.8134



```python
print(salutation)
```

    Comment allez-vous ?


Pour afficher les trois valeurs sur la même ligne on utilise une seule fonction print() en séparant
les variables par des virgules :


```python
print(x,y,salutation)
```

    86 4.8134 Comment allez-vous ?


## <left> <b> <span style="color:brown;"> 0.2 Assignation multiple</span> </b></left>

Les examples présentes entrent dans le cadre de ce qe nous appelons `assignation directe`. Une `assignation multiple` est un cas d'`assignation directe` qui consiste à attribuer une même valeur à plusieurs variables dans la
même ligne de code. Exemple :


```python
x = y = 7 # x et y prennent la même valeur simultanément 7.
```

## <left> <b> <span style="color:brown;"> 0.3 Assignation parallèle</span> </b></left>
Une `assignation parallèle` consiste à définir plusieurs variables en utilisant un seul symbole
d’égalité. Exemple :


```python
x, y = 4, 8.33 # On définit deux variables x et y dont les valeurs sont respectivement 4 et 8.33.
```


```python
## 0.2 Erreur d'assignation

128 = a
```


      File "<ipython-input-110-74505f970abb>", line 3
        128 = a
               ^
    SyntaxError: can't assign to literal




```python
Ceci nous appelle a parler brièvement des noms de variables admissibles sous Python. 
```


      File "<ipython-input-111-857d56225df4>", line 1
        Ceci nous appelle a parler brièvement des noms de variables admissibles sous Python.
                ^
    SyntaxError: invalid syntax



##  <left> <b> <span style="color:brown;">0.4 Conventions de nommage </span> </b></left>

Les conventions de nommage des différents éléments de code sont importantes car elles donnent des informations supplémentaires aux développeurs quant à la nature de certains attributs ou certaines variables. Il faut garder à l'esprit certaines règles concernant les noms de variables.
La convention pour les noms de variable est la suivante:
 
   - Ils ne doivent être constitués que de caractères alphanumériques (a-z, A-Z, 0-9) et du caractère de soulignement` _`.
   - Les noms de variables peuvent debuter avec `_` , `$` , ou une lettre;
   - Les noms de variables peuvent etre en miniscule ou en majuscule;
   - Les noms de variables ne peuvent debuter avec un chiffre;
   - Les espaces blancs ne sont pas autorisés dans les noms de variables;
   - Les mots réservés tels que `if`, `else` , etc., ne peuvent être utilisés comme noms de variables;


<left> <b> <span style="color:brown;"> Le bon programmeur s’efforce bien entendu de choisir les noms de variables les plus pertinents possible. </span> </b></left>

Sous Python, il existe **33** mots réservés dont la liste est fournie ci-dessous:

|             |                  |                  |                  |                  | 
|-------------|------------------|------------------|------------------|------------------|
|``and``      | ``elif``         | ``if``           | ``or``           | ``yield``        |
|``as``       | ``else``         | ``import``       | ``pass``         |                  | 
|``assert``   | ``except``       | ``in``           | ``raise``        |                  |  
|``break``    | ``False``        | ``is``           | ``return``       |                  |
|``class``    | ``finally``      | ``lambda``       | ``True``         |                  |
|``continue`` | ``for``          | ``None``         | ``try``          |                  |
|``def``      | ``from``         | ``nonlocal``     | ``while``        |                  |
|``del``      | ``global``       | ``not``          | ``with``         |                  |

### <left> <b> <span style="color:red;"> Note</span> </b></left>

Vous pouvez toujours obtenir la liste des mots-clés dans votre version actuelle de Python en tapant 
`import keyword ; print(keyword.kwlist)` dans un environnement Python. 


```python
import keyword ; print(keyword.kwlist)
```

    ['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']


**Remarque**: Python est sensible à la casse, ainsi, les noms de variables `Age` et `age` sont distincts. Suivant le langage, il y a une [convention de nommage](https://en.wikipedia.org/wiki/Naming_convention_(programming)#Python_and_Ruby) pour les variables qui est recommandée. 

- `UpperCamelCase` pour les noms de classe;

- `CAPITALIZED_WITH_UNDERSCORES` pour les constantes;

- `lowercase_separated_by_underscores` ou `snake_case` pour les autres variables.

****
**Un exercice fondamental : l’échange des contenus de deux variables**

> On suppose que les variables `x` et `y` ont pour valeurs respectives des entiers $\alpha$ et $\beta$. On souhaite
échanger le contenu de ces deux variables.

>   - a. Première méthode : Proposer une méthode qui utilise une variable auxiliaire `tmp`.
       ```python
          tmp = x
          x = y
          y = tmp
       ```
>   - b. Deuxième méthode : On exécute la séquence d’instructions suivante :
       ```python 
          x = x + y; y = x - y; x = x - y  
       ```
       
>   - c. Troisième méthode (la plus « pythonique ») : Utiliser une affectation parallèle.
      ```python
         x, y = y, x
      ```   
**** 

### <left> <b> <span style="color:red;"> Première méthode </span> </b></left>


```python
x = 5
y = 4  
print(x,y)
print("================================================")
print('\t')

tmp = x
x = y
y = tmp
print(x,y)
```

    5 4
    ================================================
    	
    4 5


### <left> <b> <span style="color:red;"> Deuxième méthode </span> </b></left> 


```python
x = 7
y = 9 
print(x,y)
print("================================================")
print('\t')


x = x + y; y = x - y; x = x - y 
print(x,y)
```

    7 9
    ================================================
    	
    9 7


### <left> <b> <span style="color:red;"> Troisième méthode </span> </b></left> 


```python
x = 90
y = 15
print(x,y)
print("================================================")
print('\t')


x, y = y, x
print(x,y)
```

    90 15
    ================================================
    	
    15 90



```python
x
```




    15



Signalons rapidement que pour supprimer une variable, on dispose de la fonction `del`. Supprimons la variable `x` avec `del x`


```python
del x
```

Vérifions que la variable `x` n'existe plus.


```python
print(x)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-118-fc17d851ef81> in <module>()
    ----> 1 print(x)
    

    NameError: name 'x' is not defined


#  <left> <b> <span style="color:orange;"> 1. Type d’une variable </span> </b></left>


Le type d’une variable correspond à la nature de celle-ci. Il existe de nombreux autres types de
variables (nombre entier, nombre réel, chaînes de caractères, etc). Les types de variables les
plus couramment rencontrés sont les entier (int) , les nombres réels (float), les chaînes de
caractères (str).

Les types de base sont:

   - Types numériques :
      - Entiers `int`
      - Réels `float`
      - Booléens `bool`, (vrai/faux) : `True`, `False`,

   
   - Chaînes de caractères : `str`
      - Entre (simples, doubles ou triples) apostrophes `'` ou guillemets `"` : `'Calvin'`, `"Calvin'n'Hobbes"`,
       `'''Deux\nlignes'''`, `"""'Pourquoi?' demanda-t-il."""`
       
Des types plus complexes comme   
   - None (rien)
   - Complexes`complex`:`1+2j`, `5.1j`, `complex(-3.14)`, `complex('j')`
exstent aussi mais ne seront abordés que plus tard dans cette formation.   

Python est un langage au typage dynamique, c’est-à-dire qu’il reconnaît directement le type
des variables lorsque sa valeur est indiquée. Ainsi, contrairement à d'autres langages comme le
langage C, il n'y a pas de déclaration de type obligatoire lors de la création d'une variable.
Exemples :


```python
x = 2 # type entier (int)
x = 2. # type réel (float avec décimaux)
x = '2' # type caractère (string)
```

Pour connaitre le type d’une variable, on utilise la fonction `type()`.


```python
i = 123
type(i) # renvoie <type 'int'>
```




    int




```python
type(i) is int # renvoie True
```




    True




```python
k = 123.456
type(k) # renvoie <type 'float'>
```




    float




```python
type(k) is float # renvoie True
```




    True




```python
m = 'ABCD'
type(m) # renvoie <type 'str'>
```




    str




```python
type(m) is str # renvoie True
```




    True



#  <left> <b> <span style="color:orange;"> 2. Conversion de types (casting) </span> </b></left>

Il faut remarquer que les variables en chaînes de caractères sont toujours définies avec des
guillemets. Avec des guillemets
simples, on a des chaines de types char alors qu’avec des guillemets doubles, on obtient des
chaînes de type string. Noter aussi que même si une variable est définie avec des nombres,
lorsque ces nombres sont indiqués avec des guillemets, python traite cette variable comme
une chaine de caractères. Néanmoins, il existe des fonctions pour convertir une variable d’un
type à un autre lorsque cette conversion est autorisée. Voir les exemples suivants.

* Lorsque c'est possible, un type de données peut être converti vers un autre type de données.
  * convertir un **`int`** en **`str`**:    **`str(4)`** => "4"
  * convertir un **`str`** en **`int`**:    **`int("4")`** => 4
  * convertir un **`float`** en **`int`**:    **`int(4.8)`** => 4
  * conversion en **`bool`**: **`bool(""), bool(0.0), bool(0)`** => **`False`**. Tout le reste renvoie **`True`**


```python
#Conversion d’une variable de type caractère en variable de type entier ou réel.

x='2'
print(x)
print("================================================")
print('\t')


x = int(x)
print(x)
print("================================================")
print('\t')



x = float(x)
print(x)
```

    2
    ================================================
    	
    2
    ================================================
    	
    2.0



```python
#Conversion d’une variable de type numérique (entier ou réel) en variable de type caractère.

y = 2.4756

y = str(y)

print(y)
```

    2.4756



```python
print(bool(""), bool(0.0), bool(0))
print(bool("0"), bool(-1.2), bool(-10), bool("hi"))
str(True), str(False), int(True), int(False), float(True), float(False)
```

    False False False
    True True True True





    ('True', 'False', 1, 0, 1.0, 0.0)




```python
int(4.9), float("3.5"), str(3.5), bool(4.2), bool(-2), bool(0)
```




    (4, 3.5, '3.5', True, True, False)



En conclusion, on peut noter que toutes les variables numériques sont convertible en type
caractère mais une variable n’est convertible en type numérique que lorsque la valeur de celle-
ci est constituée uniquement de chiffres.


```python
A = "On essaie"
A = int(A)
A
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-130-5f6b01452aec> in <module>()
          1 A = "On essaie"
    ----> 2 A = int(A)
          3 A


    ValueError: invalid literal for int() with base 10: 'On essaie'


#  <left> <b> <span style="color:orange;"> 3. Méthodes associées aux variables </span> </b></left>

A chaque variable créée dans python, est associé un ensemble d’attributs (ex : type) mais aussi
un ensemble de méthodes, c'est à dire un ensemble d’opérations de traitement et
d’exploitation réalisable avec cette variable. Pour afficher l'ensemble des méthodes d'une
variable, on utilise la commande `dir()`. Exemple :


```python
x = 2.5 # Définit une variable numérique x

y = 'mon texte' # Définit une variable en chaîne de caractères y.
```

Pour afficher l’ensemble des méthodes associées à chacune de ces variables, on fait :



```python
print(dir(x))
```

    ['__abs__', '__add__', '__bool__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floordiv__', '__format__', '__ge__', '__getattribute__', '__getformat__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__int__', '__le__', '__lt__', '__mod__', '__mul__', '__ne__', '__neg__', '__new__', '__pos__', '__pow__', '__radd__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__', '__rfloordiv__', '__rmod__', '__rmul__', '__round__', '__rpow__', '__rsub__', '__rtruediv__', '__set_format__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__truediv__', '__trunc__', 'as_integer_ratio', 'conjugate', 'fromhex', 'hex', 'imag', 'is_integer', 'real']



```python
print(dir(y))
```

    ['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']


On peut aussi faire `nom_de_la_variable.` suivi de `TAB`.

Ainsi, pour obtenir de l’aide sur une méthode spécifique, on utilise la fonction `help()` comme
suit : `help(x.nomMethode)` où nomMethode est le nom de la méthode considérée. Par exemple, pour une variable numérique de type `float`, il existe une méthode nommé `conjugate`.
Pour obtenir de l’aide sur cette fonction, on fait :
`print(help(x.conjugate))`


```python
print(help(x.conjugate))
```

    Help on built-in function conjugate:
    
    conjugate() method of builtins.float instance
        Return self, the complex conjugate of any float.
    
    None


Pour afficher l’aide sur toutes les fonctions associées à la variable x, on fait simplement :



```python
print(help(x))
```

    Help on float object:
    
    class float(object)
     |  float(x=0, /)
     |  
     |  Convert a string or number to a floating point number, if possible.
     |  
     |  Methods defined here:
     |  
     |  __abs__(self, /)
     |      abs(self)
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __bool__(self, /)
     |      self != 0
     |  
     |  __divmod__(self, value, /)
     |      Return divmod(self, value).
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __float__(self, /)
     |      float(self)
     |  
     |  __floordiv__(self, value, /)
     |      Return self//value.
     |  
     |  __format__(self, format_spec, /)
     |      Formats the float according to format_spec.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __int__(self, /)
     |      int(self)
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mod__(self, value, /)
     |      Return self%value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __neg__(self, /)
     |      -self
     |  
     |  __pos__(self, /)
     |      +self
     |  
     |  __pow__(self, value, mod=None, /)
     |      Return pow(self, value, mod).
     |  
     |  __radd__(self, value, /)
     |      Return value+self.
     |  
     |  __rdivmod__(self, value, /)
     |      Return divmod(value, self).
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __rfloordiv__(self, value, /)
     |      Return value//self.
     |  
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __round__(self, ndigits=None, /)
     |      Return the Integral closest to x, rounding half toward even.
     |      
     |      When an argument is passed, work like built-in round(x, ndigits).
     |  
     |  __rpow__(self, value, mod=None, /)
     |      Return pow(value, self, mod).
     |  
     |  __rsub__(self, value, /)
     |      Return value-self.
     |  
     |  __rtruediv__(self, value, /)
     |      Return value/self.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  __sub__(self, value, /)
     |      Return self-value.
     |  
     |  __truediv__(self, value, /)
     |      Return self/value.
     |  
     |  __trunc__(self, /)
     |      Return the Integral closest to x between 0 and x.
     |  
     |  as_integer_ratio(self, /)
     |      Return integer ratio.
     |      
     |      Return a pair of integers, whose ratio is exactly equal to the original float
     |      and with a positive denominator.
     |      
     |      Raise OverflowError on infinities and a ValueError on NaNs.
     |      
     |      >>> (10.0).as_integer_ratio()
     |      (10, 1)
     |      >>> (0.0).as_integer_ratio()
     |      (0, 1)
     |      >>> (-.25).as_integer_ratio()
     |      (-1, 4)
     |  
     |  conjugate(self, /)
     |      Return self, the complex conjugate of any float.
     |  
     |  hex(self, /)
     |      Return a hexadecimal representation of a floating-point number.
     |      
     |      >>> (-0.1).hex()
     |      '-0x1.999999999999ap-4'
     |      >>> 3.14159.hex()
     |      '0x1.921f9f01b866ep+1'
     |  
     |  is_integer(self, /)
     |      Return True if the float is an integer.
     |  
     |  ----------------------------------------------------------------------
     |  Class methods defined here:
     |  
     |  __getformat__(typestr, /) from builtins.type
     |      You probably don't want to use this function.
     |      
     |        typestr
     |          Must be 'double' or 'float'.
     |      
     |      It exists mainly to be used in Python's test suite.
     |      
     |      This function returns whichever of 'unknown', 'IEEE, big-endian' or 'IEEE,
     |      little-endian' best describes the format of floating point numbers used by the
     |      C type named by typestr.
     |  
     |  __set_format__(typestr, fmt, /) from builtins.type
     |      You probably don't want to use this function.
     |      
     |        typestr
     |          Must be 'double' or 'float'.
     |        fmt
     |          Must be one of 'unknown', 'IEEE, big-endian' or 'IEEE, little-endian',
     |          and in addition can only be one of the latter two if it appears to
     |          match the underlying C reality.
     |      
     |      It exists mainly to be used in Python's test suite.
     |      
     |      Override the automatic determination of C-level floating point type.
     |      This affects how floats are converted to and from binary strings.
     |  
     |  fromhex(string, /) from builtins.type
     |      Create a floating-point number from a hexadecimal string.
     |      
     |      >>> float.fromhex('0x1.ffffp10')
     |      2047.984375
     |      >>> float.fromhex('-0x1p-1074')
     |      -5e-324
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  imag
     |      the imaginary part of a complex number
     |  
     |  real
     |      the real part of a complex number
    
    None


#  <left> <b> <span style="color:orange;"> 3. Opérations sur les types numériques </span> </b></left>

Deux grandes catégories [d’opérateurs](https://fr.wikibooks.org/wiki/Programmation_Python/Op%C3%A9rateurs) sont utilisées en Python pour définir les variables et les
instructions. Il s’agit des opérateurs arithmétiques et les opérateurs logiques.
Les premiers permettent de réaliser les opérations mathématiques courantes tandis que les
seconds permettent de réaliser des comparaisons de valeurs. Une valeur booléenne est une
évaluation logique représentant l’une des deux possibilités suivantes : vrai ou faux. Les valeurs
booléennes sont le résultat de l’évaluation d’expressions logiques et elles servent à faire des
choix dans un programme (effectuer telle action quand telle condition est réalisée).

## <left> <b> <span style="color:brown;"> 3.0 Les opérateurs arithmétiques </span> </b></left>


   
|  Opérations    $\quad \qquad$        | Opérateur en Python 	  $\qquad$          | Exemples          |
|-------------:|:------------------:|------------------:|
| Addition $ \qquad \qquad$     |       $+ \quad \qquad$            |  $x = 2 + 3$          | 
| Soustraction $\qquad \quad$     |    $- \quad \qquad$      |   $z = x -y$      |                 
| Multiplication $\qquad \quad$  |  $* \quad \qquad$      |   $y=3*x$         | 
| Division (quotient réel)  $\qquad \quad$        | $/\quad \qquad$  | $5/2=2.5 $ |
| Division (quotient entier)  $\qquad \quad$         |$//\quad \qquad$  | $5//2=2$|
| Puissance $\qquad \quad$          | $**\quad \qquad$ | $x^{**}2=x*x$ |
| Reste de la division modulo $\qquad \quad$          | $\% \quad \qquad$  |$17\%3 =2$  |
| Addition incrémentée    $\qquad \quad$       | $+$$=\quad \qquad$ | ($x$$+$$=$$4$ ) $\iff$ $x=x+4$|
| Soustraction incrémentée    $\qquad \quad$       | $-$$=\quad \qquad$ | ($x$$-$$=$$4$ ) $\iff$ $x=x-4$|

### <left> <b> <span style="color:red;"> Quelques exemples </span> </b></left>



```python
print(10 + 10)  
print('------------------------')


print(10 - 3)
print('------------------------')

print(10 / 2) 
print('------------------------')


print(10 % 2)  
print('------------------------')

print(10 ** 2)
print('------------------------')

x = 10  
y = x + 4
x += 9  
x -= 9  
print(y)
print(x)
```

    20
    ------------------------
    7
    ------------------------
    5.0
    ------------------------
    0
    ------------------------
    100
    ------------------------
    14
    10


## <left> <b> <span style="color:brown;"> 3.1 Les opérateurs logiques </span> </b></left>


|  Opérations    $\quad \qquad$        | Opérateur en Python 	  $\qquad$          | Description          |
|-------------:|:------------------:|------------------:|
| Égalité $ \qquad \qquad$     |       $== \quad \qquad$            |    Égal à        | 
| Inégalité $\qquad \quad$     |    $!=$ (ou $<>$) $\quad \qquad$      |   Différent de      |                 
| Infériorité stricte $\qquad \quad$  |  $< \quad \qquad$      |   Inférieur à         | 
| Supériorité stricte  $\qquad \quad$        | $>\quad \qquad$  | Supérieur à |
| Infériorité large  $\qquad \quad$         |$<=\quad \qquad$  | Inférieur ou égal à|
| Supériorité large $\qquad \quad$          | $>=\quad \qquad$ | Supérieur ou égal à |
| Inclusion(appartenance) $\qquad \quad$          | `in`  $ \quad \qquad $  |Appartient à (`dans`) |
| Exclusion (non appartenance)  $\qquad \quad$       | `not in`$\quad \qquad$ |N'appartient pas à (`exclu`) |
| `Et` logique   $\qquad \quad$       | `and` $\quad \qquad$ | Comparaisons `ET` logiques|
| `Ou` logique   $\qquad \quad$       | `or` $\quad \qquad$ | Comparaisons `OU` logique|
| `Non` logique   $\qquad \quad$       | `not`$\quad \qquad$ | Évalue la valeur opposée|

<left> <b> <span style="color:red;">Affecter n’est pas comparer !</span> </b></left>
Il faut bien prendre garde au fait que l’instruction d’affectation `« = »` n’a pas la même signification que le symbole d’égalité `« = »` en mathématiques. Par exemple, le premier n’est pas
symétrique, alors que le second l’est : vouloir échanger l’ordre des éléments dans une instruction d’affectation produira immanquablement une erreur dans l’interpréteur.

Nous verrons l'utilité de ces opératuers au fil des sessions. Ils retournent toujours des booléens et permettent en l'occurence de faire des tests. Ils apparaissent dans l'écriture des boucles et dans l'écritutre des sturctures itératives et des structures conditionnelles.

Pour accéder à la liste complète des opérateurs standards de python et leurs équivalents fonctions, voir [cette page](https://docs.python.org/2/library/operator.html). L'on pourra aussi consulter [cette page](http://www.tutorialspoint.com/python/python_basic_operators.htm) pour quelques exemples
d’utilisations des opérateurs standards.


[Contenu](../Contenu.md) \| [Précédent (1.1. Python en bref)](1_Python-en-bref.md) 


