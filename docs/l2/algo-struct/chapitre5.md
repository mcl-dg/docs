# Chapitre 5 : Listes chainées
## Illustration

1 éléments contient :

-	1 valeur

-	1 pointeur vers un autre élément

![](https://pads.up8.edu/uploads/66c10c17-d577-4d0f-9363-6f5f3d3066aa.png)

NULL : liste vide

___

## Definition
Une liste chainée représente une liste de valeurs. Chaque valleur rst écrite à côté de l’adresse de la prochaine valeur. Il faut une convention pour représenter une liste vide.

___

## En C :
```c
typedef struct _cel_t{
	int v; //valeur
	(struct _cel_t)* s; //adresse cellule suivante
} cellule_t;
struct _cel_t a;
a.v = 0;
struct _cel_t b;
a.s = &b;
cellule_t c; // struct _cel_t c;
```
![](https://pads.up8.edu/uploads/cc284139-aabb-47a1-b90e-9bb14e50cd4a.png)

___

```c
#include<stdlib.h>
cellule_t* allouerCellule(int v, cellule_t* bs){
	cellule_t* r = (cellule_t*) malloc(sizeof * bs); //ou malloc(sizeof(cellule_t));
	if (r ==  NULL){
		exit(1);
	}
	(*r).v = v;
	(*r).s = bs; //ou r->s = bs;
	return r;
}
```
![](https://pads.up8.edu/uploads/7219cfc0-3e24-4243-95ae-6d376fe35cae.png)


___

```c
cellule_t* l = NULL;
l = allouerCellule(3,l);
l = allouerCellule(2,l);
l = allouerCellule(1,l);
afficherListe(l) ; //1 2 3 \n
 
```
![](https://pads.up8.edu/uploads/62cd0845-34b3-415f-8bf9-adf1ba81ad32.png)

```c
typedef int entier[3]
entier.c; //int c[3]
```
```c
void afficherListe(cellule_t* i){
	while (i !=NULL){
		printf("%d" ,(*i).v);
		i = i->s; //i = (*i).s;
	}
	printf("\n") ;
}
```

```c
void libererListe((cellule_t*)* ini){
	if (*ini == NULL) return;
	libererListe(&(*ini)->s); //ou (&(*(*ini)).s);
	free(*ini);
	*ini = NULL;
}
```
 
