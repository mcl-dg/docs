# Chapitre 10 : Arbre Binaire de Recherche et arbre AVL

On veut implanter un « ensemble d’entiers »
___
## Methode 1 : Tableau d’entiers

### Complexité temps

!!! info ""
    -	Ajout : $O(1)$
    -	Test de présence : $O(n)$ -> avec $n$ : taille de l’ensemble
___
## Methode 2 : Arbre binaire de recherche

### Complexité temps (pire des cas)

!!! info ""
    -	Ajout : $O(n)$
    -	Test Présence : $O(n)$

___

## Définition : (ABR : arbre binaire de recherche)

!!! info ""
    On dit qu’un arbre binaire étiqueté par des entiers est un arbre binaire de recherche si pour tout nœud V :

    -	Les etiquettes situées « a gauche » de V sont strictement inférieures à l’étiquette de V
    -	Les étiquettes situées « a droite » de V sont strictement supérieures à l’étiquette de V.

### Illustration :
On ajoute dans cet ordre à un ABR les valeurs suivantes :

$8 \;3\; 16\; 17\; 23\; 2\; 5\; 3\; 1\; 9\; 7$

![](https://pads.up8.edu/uploads/209cc60f-c0c0-4f7e-a6b2-7023d47b12d1.png)

Pour ajouter une valeur on descend dans l’arbre jusqu’à trouver une place vide, à chaque nœud si la valeur à ajouter :

!!! danger ""
    -	Est inferieur -> gauche
    -	Est supérieur -> droite
    -	Est égale -> stop

### Problème : Si l’arbre est « déséquilibré »

$1\; 23\; 2\; 3\; 17\; 3\; 5\; 7\; 16\; 9\; 8$

![](https://pads.up8.edu/uploads/bcc5d485-1d34-4648-904e-1fb76ef5554c.png)



**Idée :** à chaque ajout (non retrait) on effectue des « rotations » (voir suite) pour « équilibrer » l’ABR.
___
## Definition : arbre équilibré

!!! info "Un arbre binaire est dit équilibré, soit :"
    -	S’il est vide
    -	Soit les deux sous-arbres de la racine sont équilibrés et leur hauteur ne diffère que d’au plus 1.


### Exemple : 
![](https://pads.up8.edu/uploads/05105308-eb96-478e-b434-b0201d20bddc.png)
![](https://pads.up8.edu/uploads/44568c08-e4c3-45c7-8c30-dd47c48e00f3.png)


### Théorème :
La hauteur d’un arbre binaire équilibré de n nœud est inférieur à $2 \times log_2(n)$


(**Idée :** par récurrence on montre que dans un arbre équilibré de hauteur h, les nœuds de profondeur $< h/2$ forment un arbre complet)


![](https://pads.up8.edu/uploads/0b7066a2-74c0-4698-92fa-553c70a011f1.png)


___
## Definition : arbre AVL
On appelera AVL, un ABR qui est équilibré.
___
## Rotation (sur un nœud)

![](https://pads.up8.edu/uploads/ef309834-0573-4966-ada4-c5198728a1d9.png)


Une rotation gauche ou droite conserve la structure d’ABR (en modifiant certaines hauteurs)

### Comment utiliser les rotations pour rééquilibrer ?

![](https://pads.up8.edu/uploads/38af0320-c34d-4f14-9a73-43fa1c8a64ff.png)


___

#### Cas possible
![](https://pads.up8.edu/uploads/4e1bdf4a-d5d9-481d-87ce-73ca439880ed.png)
___
#### Cas 2
![](https://pads.up8.edu/uploads/d3e9d1e4-2528-4080-b85a-c9dbb622934c.png)
___
#### Cas 3
![](https://pads.up8.edu/uploads/9daa0919-5f93-486d-a94e-2c847ab9fce8.png)
___
#### Cas 1
![](https://pads.up8.edu/uploads/5554b90b-fe31-4cff-b6b2-0007e562a914.png)

![](https://pads.up8.edu/uploads/a8e9abbd-58de-450d-9317-7cac6798230c.png)


___

Après chaque ajout ou retrait d’un élément, on verifie sur chaque nœud de la branche parcouru s’il est en déséquilibre. Si c’est le cas on rééquilibre avec une rotation ou une double rotation ``RotX(?)`` sur ``RotY(?)``

