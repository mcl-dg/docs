# Chapitre 11 : Graphe orienté non étiqueté

## Graphe orienté

!!! info "Définition"
	Un graphe orienté est un ensemble de sommets dont certains couples sont reliés entre eux par des « arcs » (flèches)

	Formellement :

	Un graphe est un couple $(S, A)$ où $S$ est un ensemble fini et $A$ un sous ensemble de $S \times S$

___

## Exemple de graphe

### illustration

![](https://pads.up8.edu/uploads/005aaade-81c3-4e3a-8779-5ef1111c74dc.png)



### Exemple 

Le graphe illustré ci contre peut être formellement décrit par : 

$S = \{1,2,3,4,5,6,7,8\}$

$A = \{(1,2),(2,3),(4,2),(3,4),(8,3),(3,8),(8,7),(7,6)\}$
___
## En informatique : 
-	Liste des sommets et des arcs

```dot
1
2
3
4
…
1->2
2->3
4->2
…
```
___
-	Matrice d’adjacence 

Illustration :



||1|2|3|4|5|6|7|8|
|-|-|-|-|-|-|-|-|-|
|**1**|0|1|0|0|0|0|0|0|
|**2**|0|0|1|0|0|0|0|0|
|**3**|0|0|0|1|0|0|0|1|
|**4**|0|1|0|1|0|0|0|0|
|**5**|0|0|0|0|0|0|0|0|
|**6**|0|0|0|0|0|0|0|0|
|**7**|0|0|0|0|0|1|0|0|
|**8**|0|0|1|0|0|0|1|0|

$0$ : pas d’arc

$1$ : un arc
___


-	Liste d’adjacence

```c
1 : {2}
2 : {3}
3 : {8 ; 4}
4 : {4 ; 2}
5 : {}
6 : {}
7 : {6}
8 : {3 ; 7}
```
___
## Remarques :

-	**Liste des arcs :** peu de place en mémoire souple mais lent pour trouver un arc
-	**Liste d’adjacence :** intéressant lorsqu’il y a peu d’arcs $O(n)$ où n est le nombre de sommets
-	**Matrice d’adjacence :** intéressant alors qu’il y a beaucoup d’arcs : $O(n^2)$ test de présence d’un arc $O(1)$

___

## Vocabulaire

### Illustration :

![](https://pads.up8.edu/uploads/d151e4fc-b37a-4778-86f7-566ebaccd44a.png)

___

## Chemin, chemin élémentaire

- Un chemin part d’un sommet étiqueté est une liste d’arc où chaque destination d’un arc est l’origine de l’arc suivant.

- Un chemin est dit élémentaire si il passe au plus une seule fois par sommet
___

### Exemple : 

-	3 8 3 4 4
-	2 3 4 (élémentaire)
-	2 3 4 2 (circuit)
-	3 (c’est un chemin qui n’emprunte pas d’arc)



___

## Successeur, successeur direct, predescesseur, predescesseur direct

- On dit qu’un sommet ``V`` est un successeur d’un sommet ``U`` si il existe un chemin allant de ``U`` jusqu’à ``V``
- Si ce chemin emprunte un seul arc on dit que ``V`` est un successeur direct.


- On parle aussi de prédescesseur et de prédescesseur direct dans « l’autre sens »



### Exemple :
- 8 est un prédescesseur direct de 7
- 8 est un prédescesseur de 6
- 7 est un successeur direct de 8
- 6 est un successeur de 8

___
## Circuit

- On dit qu’un chemin est un circuit si son sommet de départ est aussi son sommet d’arrivée.

- Quand un graphe n’admet aucun circuit qui emprunte au moins un arc on dit qu’il est sans circuit





### Exemple de graphe sans circuit

![](https://pads.up8.edu/uploads/375c8326-18cc-4d50-aba3-1c3e2ca018c5.png)

___
## Parcours en profondeur d’un graphe

### Algorithme (pseudo-code)

```c
Parcours(s : sommet) :
	Si s déjà visité :
		Revisite de s
	Sinon
		Previsite de s
		Pour tout i successeur direct de s
			Parcours(i)
		Post visite de s
```

___
### Illustration

Pour ``Parcours(3)`` : 

![](https://pads.up8.edu/uploads/7899d5e5-2000-42de-b000-cd595586f766.png)

|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-
|$3$|$8$|$3$|$7$|$6$|$\bar{6}$|$\bar{7}$|$\bar{8}$|$4$|$4$|$2$|$3$|$\bar{2}$|$\bar{4}$|$\bar{3}$