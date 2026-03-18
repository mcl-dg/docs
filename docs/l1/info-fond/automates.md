# Automates et machine de Turing

## Automates finis


!!! info "Définition"
    
    Un automate est un quintuplet $(K,T,M,I,F)$ avec :

    $K$ : ensemble fini d'états

    $T$ : vocabulaire terminal (alphabet)

    $M$ : Relation $K \times T \times K$

    $I \subset K$ : états initiaux

    $F \subset K$ : états finaux




$\rightarrow$ Sert à construire des mots à partir d'un alphabet de base

___

### 1. Indeterministes

!!! info "Définition"
    Un automate est indéterministe s’il existe au moins un état qui a plusieurs transitions sortantes avec la même étiquette

___

### 2. Déterministes

!!! info "Définition"
    Un automate est déterministe si pour chaque état et chaque symbole de l’alphabet, il y a au plus une transition sortante avec ce symbole.

___


### 3. Complet

!!! info "Définition"
    Un automate est complet s'il est déterministe et si pour chaque état et chaque symbole de l’alphabet, il y a exactement une transition sortante.


### Exemple 1

- $K = \{s,v,u\}$
- $T = \{a,b\}$
- $M = \{(s,a,s),(s,a,v),(v,b,v),(v,b,u)\}$
- $I = S$
- $F = S$

$s,a,s,a,s,a,s,a,v,b,v,b,v,b,u$

Ce qui nous donne : $aaaabbb$

![](https://pads.up8.edu/uploads/a3b04f4e-4e2b-4576-9e03-7e5b36972870.png)

L'automate est **indéterministe** car l'état __S__ a une transition sortante avec deux __a__. Il n'est pas complet.

___

### Exemple 2

- $K = \{q_0,q_1,q_2,q_3\}$
- $T = \{0,1\}$
- $I =\{q_0\}$
- $F = \{q_3\}$


$M$ : 

* $q_0 \rightarrow 0 \rightarrow q_0$
* $q_0 \rightarrow 1 \rightarrow q_1$
* $q_1 \rightarrow 0 \rightarrow q_2$
* $q_1 \rightarrow 1 \rightarrow q_0$
* $q_2 \rightarrow 0 \rightarrow q_3$
* $q_2 \rightarrow 1 \rightarrow q_1$
* $q_3 \rightarrow 0 \rightarrow q_3$
* $q_3 \rightarrow 1 \rightarrow q_3$

![](https://pads.up8.edu/uploads/3c056997-49ef-4f4e-bd06-6b4cbb3fe95f.png)

___

### Exemple 3

- $K = \{q_0,q_1,q_2,q_3\}$
- $T = \{0,1\}$
- $I =\{q_0\}$
- $F = \{q_3\}$

$M_1$ : 

* $q_0 \rightarrow 0 \rightarrow q_0$
* $q_0 \rightarrow 1 \rightarrow q_3$
* $q_1 \rightarrow 0 \rightarrow q_2$
* $q_1 \rightarrow 1 \rightarrow q_1$
* $q_2 \rightarrow 0 \rightarrow q_0$
* $q_2 \rightarrow 1 \rightarrow q_3$
* $q_3 \rightarrow 0 \rightarrow X$
* $q_3 \rightarrow 1 \rightarrow X$

![](https://pads.up8.edu/uploads/1749fb68-2042-4937-bf8e-5254cd6fb6fd.png)

___

## Exercices

### Construire : 

1. **Automate qui reconnait tous les mots formés d'autant de *a* que de *b*.**

    - *Ex :* aababb

        baab

2. **Automate qui reconnait tous les mots dont le préfixe est *ab***

    * $q_0 \rightarrow a \rightarrow q_1$
    * $q_0 \rightarrow b \rightarrow q_2$
    * $q_1 \rightarrow a \rightarrow q_2$
    * $q_1 \rightarrow b \rightarrow q_3$
    * $q_2 \rightarrow a \rightarrow q_2$

    * $q_2 \rightarrow b \rightarrow q_2$
    * $q_3 \rightarrow a \rightarrow q_3$
    * $q_3 \rightarrow b \rightarrow q_3$

3. **Automate qui reconnait tous les mots dont le préfixe est *ba***


4. **Automate qui reconnait tous les mots dont le suffixe est *ab***


    * $q_0 \rightarrow a \rightarrow q_7$
    * $q_0 \rightarrow a \rightarrow q_0$
    * $q_0 \rightarrow b \rightarrow q_0$

    * $q_7 \rightarrow b \rightarrow q_8$
    * $q_7 \rightarrow a \rightarrow q_0$

    ![](https://pads.up8.edu/uploads/2c3de287-23f2-4ef9-b0dd-87023a1c02b7.png)

    **Expression régulière :** $(a|b)*ab$

5. **Automate qui reconnait tous les mots dont le suffixe est *ba***



___

## Propriété
!!! warning ""
    
    $AFD \iff AFI$

    Vrai, il y a toujours un moyen d'écrire un automate déterministe sous forme d'automate indéterminisme, ou inversement

___

## Machine de Turing

!!! info "Définition"

    Une machine de Turing est un automate déterministe. Il est composé d'une une mémoire schématisé par un ruban :

    |$-\infty$||||||$+\infty$|
    |-|-|-|-|-|-|-|


    Dans chaque case de la mémoire, on peut lire, écrire, se déplacer à droite ou à gauche, ou changer d'état.


    $0/1$

    $Lire / Ecrire$

    $D/G$ (droite / gauche)

    $L/R$ (left / right)

    $<Etat, caracter> \rightarrow <Etat',caracter', D/G>$

    ![](https://pads.up8.edu/uploads/26d1d9bb-6fdf-4807-ad10-70e5cd12c4d4.png)

___

## Propriété

!!! warning ""

    $\forall p, un \; programme, \exists m, machine \; de \; Turing$

    et $p$ et $m$ font la même chose

___
## Exercices

### Exercice 1

!!! warning ""
    - Faire tourner la machine de Turing suivante.

$Etats = \{e_1,e_2,e_3,e_4,e_5\}$

$Alphabet = \{0,1\}$

$<e_1,0> \rightarrow arret$

$<e_1,1> \rightarrow <e_2,0,D>$

$<e_2,0> \rightarrow <e_3,0,D>$

$<e_2,1> \rightarrow <e_2,1,D>$

$<e_3,0> \rightarrow <e_4,1,G>$

$<e_3,1> \rightarrow <e_3,1,D>$

$<e_4,0> \rightarrow <e_5,0,G>$

$<e_4,1> \rightarrow <e_4,1,G>$

$<e_5,0> \rightarrow <e_1,1,D>$

$<e_5,1> \rightarrow <e_5,1,G>$


|cases|0|1|2|3|4|5|6|7|8|
|-|-|-|-|-|-|-|-|-|-|
|contenus|0|0|1|1|0|0|0|0|

??? success "Correction"

    |cases|0|1|2|3|4|5|6|7|8|
    |-|-|-|-|-|-|-|-|-|-|
    |contenus|0|0|~~1~~ ~~0~~ 1|~~1~~ ~~1~~ ~~1~~ ~~0~~ 1|~~0~~ ~~0~~ ~~0~~ ~~0~~ 0|~~0~~ ~~1~~ ~~1~~ 1|~~0~~ 1|0|

    ##### Etapes

    $<e_1, case2>$

    $<e_2,case3>$

    $<e_2, case4>$

    $<e_3, case5>$

    $<e_4, case4>$

    $<e_5, case3>$

    $<e_5, case2>$

    $<e_1, case3>$

    $<e_2, case4>$

    $<e_3, case5>$

    $<e_3, case6>$

    $<e_4, case5>$

    $<e_4, case4>$

    $<e_5, case3>$

    $<e_1, case4>$

___


### Exercice 2



!!! warning ""
    Soit l'alphabet : $\{a,b,vide\}$

    1. Ecrire une machine de Turing qui reconnait les mots ayant un nombre pair de $a$.
    2. Donner l'automate
    3. Donner l'expression régulière

        ??? success "Correction (expression régulière)"
            $(aa|b)*$ non

            $b*(b*ab*ab*)*$ oui


___

### Exercice 3


!!! warning ""
    1. Faire tourner la machine de Turing suivante.

$(e_0,a) \rightarrow (e_1, a, R)$

$(e_0,b) \rightarrow (e_2, c, R)$

$(e_0,c) \rightarrow (e_0, c, R)$

$(e_1, a) \rightarrow (e_1, a, R)$

$(e_1, b) \rightarrow (e_2, c, R)$

$(e_1, c) \rightarrow (e_0, c, R)$

$(e_2, a) \rightarrow (e_2, b, L)$

$(e_2, b) \rightarrow (e_2, c, R)$

$(e_2, c) \rightarrow Stop$

|contenus|c|c|a|c|b|a|c|
|-|-|-|-|-|-|-|-|

??? success "Correction"

    |contenus|c|c|a|c|b|a|c|
    |-|-|-|-|-|-|-|-|
    |résultats|c|c|a|c|c|b|c|


    Etats : $e_0$ $e_0$ $e_1$ $e_0$ $e_2$ $e_2$ $stop$

!!! warning ""
    2.Ecrire une machine de Turing qui s'arrête après avoir écrit 0 s'il y a au moins un b dans un mot. Un mot est encadré par "".

    $Alphabet = \{a,b,c,g,t,o,"\}$

    Exemple : "gabtaca0"


??? success "Correction"

    $(e_0, ") \rightarrow (e_1, ", D)$

    $(e_0, x) \rightarrow (e_0, x, D)$

    $(e_1, ") \rightarrow (e_1, ", STOP)$

    $(e_1,b) \rightarrow (e_2, b, D)$

    $(e_1, x) \rightarrow (e_1, b, D)$

    $(e_2, ") \rightarrow (e_3, 0, D)$

    $(e_2,x) \rightarrow (e_2, x, D)$

    $(e_3, x) \rightarrow (e_3, ", STOP)$ 