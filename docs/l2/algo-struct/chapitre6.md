# Chapitre 6 : Arbres binaires


## Illustration d'un arbre

![](https://pads.up8.edu/uploads/436632b7-b6be-45ae-a946-7fcce6d2a128.png)

___

## Exemple
$(3+2) \times (5-4)$
 
![](https://pads.up8.edu/uploads/2302bf76-4a8c-427f-bd46-0add27df9b16.png)
___
## Définition


Un arbre binaire étiqueté (par des entiers) est 

-	Soit l’arbre vide (vide)
-	Soit « l’assemblage » 
    - De 2 arbres
    - Et d’un entier

``A := (vide) | (A,A,I)``

Avec ``I`` : l’ensemble des entiers.

``A`` : l’ensemble des arbres binaires étiqueté par des entiers.

Que contient ``A`` ?
___
``(vide,vide,42)`` :
 ![](https://pads.up8.edu/uploads/5bf5c89c-4513-4086-96da-e8719e86e230.png)

___
``(vide, (vide,vide,42),1)`` : 
 ![](https://pads.up8.edu/uploads/9ba970b0-ab5f-428f-87f7-3287b1c733f8.png)
___

``((vide,vide,42),(vide,vide,42),3)`` :
 ![](https://pads.up8.edu/uploads/11f38f48-6ba8-4390-adaf-1d7ccbbe12fa.png)
___
## Vocabulaire :
 ![](https://pads.up8.edu/uploads/0b83d95a-8dbd-4625-806b-4a69a5308105.png)

Taille : $6$

Hauteur : $4$
___
Si un arbre binaire est de hauteur $h$, alors il possède au plus $2^h -1$ nœuds.


Les nœuds qui ne sont pas des feuilles sont appelés nœuds internes.

-	La taille d’un arbre est son nombre de nœuds
-	La profondeur d’un nœud est le nombre de nœuds rencontrés par un chemin élémentaire allant de ce nœud à la racine.
-	La hauteur d’un arbre est le maximum des profondeurs de ses nœuds s’il est non vide et 0 s’il est vide.

Pour un arbre complet, le nombre de noeuds a une profondeur $p$ est : $2^p$.

___
## En C :
```c
typedef struct_noeud_t{
	int v;
	struct_noeud_t* g;
	struct_noeud_t* d;
} noeud_t;

//l’arbre vide sera représenté par la valeur NULL
```

![](https://pads.up8.edu/uploads/11a5e4c8-6738-4fd9-a3c8-10754bef9bb4.png)
___
## Exemple :
 ![](https://pads.up8.edu/uploads/b1442b7f-d185-48ca-905c-43fcc984780e.png)

![](https://pads.up8.edu/uploads/89f813bb-0e06-4e6a-a858-1189f9d6ace3.png)

 

```c
noeud_t* allN(int pv, noeud_t* pg, noeud_t* pd){
    noeud_t* r = (noeud_t*) malloc(sizeof(noeud_t));
    if (r == NULL){
        printf("erreur d’allocation\n");
        exit(1);
    }
    r->v = pv;
    r->g = pg;
    r->d = pd;
    return r;
}
    
```
___
## Parcours en profondeur d’un arbre

Un parcours est une façon de le représenter sous la forme d’une chaine de caractères.

``Parcours_prefixe(A)`` :

- Si ``A`` est vide on affiche ``V``
- Sinon
    -	On affiche l’étiquette de la racine de ``v``
    -	``Parcours_prefixe(sous-arbre à gauche de la racine)``
    -	``Parcours_prefixe(sous-arbre à droite de la racine)``
___
Il existe d’autres types de parcours en profondeurs.

- Parcours **post-fixe** (ou suffixe)
    - gauche
    - droite
    - racine

- Parcours **infixe**
    - gauche
    - racine
    - droite
