# Chapitre 3 : Terminaison, Correction, et complexité d’un algorithme


Soit un algorithme A.

## Terminaison :
-	A se termine-t-il pour n’importe quelle valeur d’entrée ?

Réponse : Oui -> avec preuve / Non -> contre-exemple avec preuve

## Correction :
-	Soit P (e,s) une propriété sur s et e structures formelles
-	Si e est l’ensemble des valeurs d’entrée de A et s l’ensemble des valeurs de sorties associées à e est-ce qu’on a P(e,s) ?

Réponse : oui -> preuve associé / non -> contre-exemple

## Complexité :
Quelles sont les performances d’un algorithme ?

-	Combien d’opération « élémentaire » sont effectuée durant le déroulement complet de l’algorithme : complexité en temps ?
-	Quelle « place en mémoire » l’algorithme occupe-t-il à « l’instant le plus gourmand » de son déroulement ? complexité en espace


**Réponse :** suite numérique $\mathbb{N} \rightarrow \mathbb{R}$ avec preuve



Une suite numérique est utilisée pour décrire les « ressources » nécessaires à l’algorithme selon la « taille » des entrées.

**Exemple :** de taille de tableau : son nombre de case
-	Tableau rapide à trier
-	Tableau lent à trier


Analyse dans le pire des cas
-	Pour une taille donnée, on choisit l’entrée de cette taille qui va utiliser le plus de ressource.
Analyse en moyenne
-	Pour une taille donnée, on fait une moyenne des ressources utilisées pour tous les cas selon une certaine distribution

___

## Exemple : Tri à bulle

```c
void triBulle(int n, int* T){
    int change = 1;
    int j;
    int temp;
    while (change==1){
        change ==0;
        for (j=0;j<n-1;j++){
            if (T[j]>T[j+1]){
                change = 1;
                temp = T[j];
                T[j] = T[j+1];
                T[j+1] = temp;
            }
        }
    }
    
}


T[] = {3,7,1,9,4,6,2,1}

```

**On vérifie :**

-	Terminaison ?
-	Correct ?
-	Complexité ?

___

**1.Correct ?**


    -	Entrée : Tableau T d’entiers
    -	Sortie : tableau S d’entiers

Propriétés attendues :

-	S doit contenir les mêmes valeurs que T avec multiplicité (cad. S est le même tableau que T mais à permutation différente)

-	Les valeurs du tableau S doivent être triées selon l’ordre croissant.

OK
___

**2.Terminaison ?**

Le tableau a un nombre fini d’élément, et à chaque itération l’élément le plus grand de la partie non trié est trié.

OK
___
**3.Complexité ?**

-	Complexité en temps :
        $(n^2 \times k)  = O(n^2)$

-	Complexité en espace : $O(n)$



___

## TD

1.	

A -> B

A -> C

B -> C

A -> B

C -> A

C -> B

A -> B

___


A -> B

A -> C

B -> C

A -> B

C -> A

C -> …

A -> B

A -> C

B -> C

B -> …

C -> A

B -> … 



