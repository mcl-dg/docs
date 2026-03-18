# Chapitre 7 - Conteneurs : pile, file, map, sac, ensemble

!!! info "Définition"
    On distingue les conteneurs qui **mémorise l’ordre** : pile, file
    Des conteneurs de **valeur** : map, sac, ensemble

___

## Exemple : map (dictionnaire)

!!! info "Définition"
    Une map est un objet qui mémorise des couples ``((cle, valeur))`` avec la contrainte suivante il ne peut mémoriser deux couples différents ayant la même valeur de clé.

    Pour implanter une map de telle façon que les operations 'associer' et "getValue" soient efficace on peut utiliser par exemple une table de hachage ou un arbre binaire de recherche.

### Illustration : 

$\{3 \rightarrow "le \; nombre \; 3";$

$1 \rightarrow "le \; premier"; \times$

$1 \rightarrow "prems" \}$

### En C (prototypes) : 

```c
typedef...{
    ...}map_t

void initMap(map_t * m);
void freeMap(map_t * m);

int associerMap(map_t * m, const char * cle, const char * valeur);

const char * getValue(map_t * m, const char * cle);
```

### Exemple d'utilisation en C : 

```c
map_t maMap; // dictionnaire
initMap(&maMap); // {}
associerMap(&maMap, "stylo", "outil pour ecrire");
// {"stylo" → "outil pour ecrire"};
associerMap(&maMap, "ballon", "objet spherique");
// {"stylo" → "outil pour ecrire" ; "ballon" → "objet spherique"}

const char * c = getValue(&maMap, "stylo"); // c = "outil pour ecrire"
associerMap(&maMap, "stylo", "abrev. de stylographe");
// {"stylo" → "abrev de stylographe" ; "ballon" → "objet spherique"}
freeMap(&maMap);
```

___

## La pile

!!! info "Définition"
    Dans une pile on a deux operations : 
    
    - ajouter un objet à la pile (empiler)
    
    - retirer un objet de la pile (dépiler)

    Si on retire un objet de la pile on retire forcément celui qui est le plus "récent"

    LIFO : Last In First Out
    (dernier entrée premier sorti)

___

## La file

!!! info "Définition"
    Comme dans une pile, on a deux opérations :

    - ajouter un objet dans la file (enfiler)
    - retirer un objet d'une file (défiler)

    à la différence d'une pile si on retire un objet, on retire forcément le plus "ancien"

    FIFO : First In First Out
    (Premier entrée premier sorti)

___

## Exemple  : pile et file

### Pile
```c
pile_t * p = initPile();
empiler(p, 1);
empiler(p,2);
int r1 = depiler(p); // 2
int r2 = depiler(p); // 1
libererPile(p);
```

### File

```c
file_t * f = initFile();
enfiler(p,1);
enfiler(p,2);
int r1 = depiler(p); // 1
int r2 = depiler(p); // 2
libererFile(f);
```
___
## Implantation pile avec tableau



|1|3|7|1|||||||||||
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
base de la pile|||sommet de la pile||||||||||

taille max = 14
___
## Implantation de pile avec liste chainée

![](https://pads.up8.edu/uploads/9ab78993-45a8-4aea-9404-ba66cbdf1ad1.png)

___

## Implantation de file avec tableau

(de gauche a droite)

|5|2|2|1|7|~~3~~|~~1~~ 3|
|-|-|-|-|-|-|-|
|||||tête de file|queue de file||

taille max = 7

___

## Implantation avec liste chainée