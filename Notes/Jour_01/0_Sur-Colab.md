---
layout: default
title: Sur Colab
---




# Notebooks iPython - Google Colab

Google Colab est un environnement permettant d'exécuter directement un **Notebook iPython**. Un Notebook est une série de **cellules de texte** (comme celle que vous êtes en train de lire), **ou de code Python** (comme la cellule suivante). Les cellules de code sont **interactives**: lorsque vous les lancez, elles réalisent le script ligne par ligne, et renvoient directement les résultats en-dessous de la cellule. 

Lorsqu'une cellule de code est lancée, le code de la cellule est en fait envoyé à un **interpréteur Python**, c'est-à-dire un système qui va traduire le code en traitements sur des données informatiques.

**Chaque cellule de code peut être exécutée individuellement, mais elles partagent toutes le même interpréteur.** L'interpréteur ne peut exécuter qu'une cellule de code à la fois. **Ainsi, si vous en lancez plusieurs en même temps, elles seront réalisées dans l'ordre dans lequel vous les avec lancées.**

**Remarque importante: comme chaque cellule partage le même interpréteur, une variable créée dans une cellule sera accessible, et modifiable dans une autre cellule**. C'est ce qui rend intéressant l'utilisation du Notebook: l'exécution séquentielle des cellules permet de vérifier étape par étape, l'évolution des états d'un programme.

Pour exécuter une cellule de code, sélectionner la cellule et :
* appuyer sur le bouton ![Texte alternatif…](https://raw.githubusercontent.com/titsitits/UNamur_Python_Analytics/master/Images/button1.jpg) apparaissant à gauche
* ou utiliser le raccourcis Shift+Enter (ou Ctrl+Enter pour rester sur la cellule après exécution)




```python
salut = 'Bonjour le monde!'
print(salut)
```

    Bonjour le monde!



```python
print(salut, 'Il y a la forme')
```

    Bonjour le monde! Il y a la forme


Pour ajouter une cellule, utiliser les boutons de contrôle du menu principal:

![Texte alternatif…](https://raw.githubusercontent.com/titsitits/UNamur_Python_Analytics/master/Images/notebook0_image1.png) 

ou le menu apparaissant sous une cellule existante:

![Texte alternatif…](https://raw.githubusercontent.com/titsitits/UNamur_Python_Analytics/master/Images/notebook0_image2.png)

Pour plus de détails sur Colab, voir [ici](https://colab.research.google.com/notebooks/basic_features_overview.ipynb).

Maintenant que vous connaissez les bases de Colab, vous pouvez passer sur [ Python en bref](1_Python-en-bref.html).


[Contenu](../Contenu.html) \| [Next (1.1. Python en bref)](1_Python-en-bref.html)
