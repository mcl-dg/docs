# TD7


## Rappel:
```
parcour_postfixe(a)
    si a est vide on affiche ⊥
    sinon 
        parcours_postfixe(s-arbre-gauche de la racine de a)
        parcours_postfixe(s-arbre-droite de la racine de a)
    on affiche l'étiquette de la racine de a.
```
## Exercice 3

``⊥⊥h⊥⊥nx⊥⊥⊥i⊥jez⊥⊥⊥e⊥⊥lgca``

## Exercice 4


![](https://pads.up8.edu/uploads/62965832-8586-4d3f-b8c8-e7a71d0d9eb4.png)


## Bonus

```c
void parcours_prefix(noeud_t* a){
    if (a==NULL){
        printf("v ");
        return;
    }
    printf("%d ", a->v);
    parcours_prefix(a->g);
    parcours_prefix(a->d);
}
```