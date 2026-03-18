# Chapitre 9 : Techniques de structurations de la mémoire

Pour structurer un ensemble de valeurs en mémoire, on utilise deux techniques :

-	Relations arithmétiques entre les adresses de valeurs.
    - Tableau ;
    - Struct (implicite) : permet de mettre des valeurs cote a cote dans la mémoire.
-	Mémoriser les adresses (pointeurs)

Souvent en même temps.
___
## Exemple

### Sudoku (avec des pointeurs)

![](https://pads.up8.edu/uploads/07c12032-5e6c-44bc-b73e-b0f68188d042.png)
___
### Soduko (avec des relations arithméthiques)


|Case|(0,0)|(0,1)||||(0,8)|(1,10)||( ?, ?)||(8,8)|
|-|-|-|-|-|-|-|-|-|-|-|-|
|**Indice**|0|1|2|3||8|9||77||80|

$9 \times 9 = 81$
___

||C|0|1|2|3|4|5|6|7|8|
|-|-|-|-|-|-|-|-|-|-|-|
|**L**|||||||||||
|0||0|1|2|3|4|5|6|7|8|
|1||9|10|11|12|13|14|15|16|17|
|2|||||||||||
|3|||||||||||
|4|||||||||||
|5|||||||||||
|6|||||||||||
|7|||||||||||
|8||||||||||80|

$C : colonne : \{0,…,8\}$

$L : ligne : \{0,…,8\}$

$i : indice$

$(l,c)$

$i= c +9*l$

$i= 8+9*8 = 10*8 = 80$

$c = i\%9$

$l = i/9$ 		-> en C la partie entière inferieur au quotient

___
### Arbres (avec des tableaux)

![](https://pads.up8.edu/uploads/f315d441-01e9-4acd-9546-329b3e5574e9.png)



Valeur|3|9|1|7|8||||
-|-|-|-|-|-|-|-|-|
**Gauche**|2|-1|-1|0|-1||||
**Droit**|-1|-1|4|1|-1||||
|**Indice**|0|1|2|3|4|5|6|7

___
### Autre manière de représenter un arbre

![](https://pads.up8.edu/uploads/41fbf3ea-c864-4082-8274-d4c5b8134231.png)


|Noeud|3|1|4|7|2|8|9|0|7|||
|-|-|-|-|-|-|-|-|-|-|-|-|
|**Indice**|0|1|2|3|4|5|6|7|8|||

$Parent(i) = (i-1)/2$

$EnfantD(i) = ?$

$EnfantG(i) = ?$

