# Rappel en C

## Introduction


### 1. Mémoire


||||||||||||||||||||||||||||
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|355|356|357|...||||||||||||||||||||||||


### 2. Définition des parties de cours


- **Structures de données :** Structurer des données dans la mémoire avec des cases numérotés.

- **Algorithmique :** Résoudre un problème de manière rapide, analyse d'algorithmes (estimer l'efficacité entre 2 algo proposés / faire la preuve qu'ils font leur travail).


___

## Chapitre 1 : Rappel de C

**Illustration : Adresses et pointeurs**

```c

int main(...){
    int a; //dans la memoire il va y avoir des cases réservés pour la variable a (4 cases car 1 case = 1 octet)
    char b; //réserver en mémoire une case pour l'objet b
    b= 3; //mettre 3 dans la case de b
    a = b; //modifier toutes les cases destiné de a par la valeur de b (4 * 8)
    &a; //opérateur de type (int *) permettant de récupérer l'adresse de a
    // l'adresse d'une variable sera toujours le plus petit numéro des cases de la mémoire (que ça soit big endian ou little endian)
    printf("%p",&a); //affiher l'adresse de a
    int * p; //pointeur prêt à mémoriser l'adresse d'un entier (réserver 8 cases / 8 octets)
    p= &a; //stock l'adresse de a dans p
    *p; // représente la valeur de la variable a
    *p = 5; // équivaut à faire a = 5
    *(&a) = 6; // équivaut à faire a = 6
}
```

### Arithmétique des adresses

**Illustration :**

```c
int T[5]; //réserver 5 int dans la mémoires
int* p = T;
*T = 5; //mettre l'entier 5 dans la première case du tableau (T[0])
*(T + 2) = 1; // mettre l'entier 1 dans T[2]
```

___

```c
int a;
int T[10];
int b;
&b - &a; //ok &a et &b sont de type int *
(T+8) - (T+2);
&b < &a;

```

### malloc et free : 

#### Exemple :

```c
#include<stdlib.h>
int* p = malloc(4*sizeof(int)) //alouer 4 cases dans la zone mémoire (16 octets)
*(p+2) = 3
free(p);
```




