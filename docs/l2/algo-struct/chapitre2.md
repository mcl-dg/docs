# Chapitre 2 : Qu’est-ce qu’un algorithme (déterministe)


## Vocabulaire : 

-	Un algorithme est une opération ou suite d’opération non ambigüe opérant sur des structures formelles.

## Structure Exemple : 

-	Mot binaires, graphe, arborescence

## But algorithme : 

-	Répondre à des questions ? résoudre un problème ?

##### Exemple : 

-	Quel est l’écriture décimale de la somme de deux nombres donnés en écriture décimale ?
-	Quel est l’écriture en chiffre romain de la somme de deux nombres donnés en chiffre romain

##### Exemple :

En langage C :

```c
int euc_pgcd(int a, int b){
	Int c;
	While (b!=0){
		C=a%b;
		a = b;
		b=c;
}
```
Version moins technique

Eucl_pgcd

### Entrées :
-	Entier a
-	Entier b
### Sortie
-	A
### Algorithme :
1.	Si b est nul :
On stoppe
2.	Si b n’est pas nul
o	(a,b) <- (b,r)
R : donne le reste de la division euclidienne de a par b
o	On saute à 1


## Bilan :
-	Un algorithme opère sur de structures formelles
-	Possède un ensemble de valeurs d’entrées et un ensemble de valeurs de sorties (éventuellement vide)
-	Pas d’ambigüité sur les opérations effectuées
-	Déterministe si on exécute deux fois le même algorithme avec les mêmes valeurs d’entrée on obtient deux fois le même déroulement des opérations.

















