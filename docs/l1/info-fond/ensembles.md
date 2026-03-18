# Ensembles

## Quantificateurs

### 1. Universel
**Pour tout ($\forall$)**

!!! info "définition"
    est vrai pour toutes les valeur

##### Exemple

- $A = \forall x \in \mathbb{N}; pair(x)$ est faux
- $B = \forall x \in \mathbb{N}; pair(x) \vee impair(x)$ est vrai
- $C = \forall x \in \mathbb{R}; pair (x) \vee impair(x)$ est faux


### 2. Existenciel

**Il existe ($\exists$)**

!!! info "définition"

    est vrai pour au moins une valeur de la variable qui suit

**Il existe une et une seule valeur ($\exists!$)**

!!! info "Définition"
    est vrai pour seulement une valeur de la variable qui suit

##### Exemple
$D = \forall x \in \mathbb{N}; \exists y \in \mathbb{N} \wedge y > x \wedge est\_premier(y)$

Signification : Quel que soit l'entier naturel $x$, il existe un nombre premier $y$ qui est plus grand que lui (vrai)

___

## Inclusion ($\subset$)

!!! info "Définition"

    Un ensemble $A$ est inclus dans $B$ si et seulement si tout les éléments de $A$ sont aussi dans $B$

##### Exemple

**Vrai** :

- $A = \{1, 2, 3\}$
- $B = \mathbb{N}$
- $A \subset B \iff (\forall x, x \in A \Rightarrow x \in B)$

**Faux** :

- $A = \{x; x \in \mathbb{N} \wedge est\_premier(x) \wedge x > 2\}$
- $B = \{x; x \in \mathbb{N} \wedge impair(x) \}$

##### Autres exemples

* $[3,5[ \subset [1,6]$ vrai
* $]3,5[ \subset [3,5]$ vrai
* $[3,5] \subset ]3,6[$ faux
* $[-3,5[ \subset [0,1]$ faux
* $]-\infty,5[ \subset ]-\infty,5]$ vrai
* $]-6,2] \subset ]-3,+\infty[$ faux
* $]-\infty, -1] \cap [3, +\infty[ = \{\} = \emptyset$
* $]0,6] \cap [0,+\infty[ = \{1,2,3,4,5,6\}$

___

## Symboles libres ou liées

### Symbole lié

!!! info "Définition"
    Un symbole lié est un nombre qui revient plusieurs fois dans une expression logique (comme $x$ dans les exemples précédents)

    Une assertion contenant des symboles liés a une valeur de vérité (vraie ou fausse).

### Symbole libre

!!! info "Définition"
    Un symbole libre est un symbole qui est fixé à l'extérieur de l'expression logique, l'expression logique dépend de ses symboles libre mais eux sont indépendants d'elle.

    Une assertion contenant au moins un symbole libre n'a pas de valeur de vérité.

##### Exemple:
$A_y = \{n; n \in \mathbb{N} \wedge x < y\}$

Signification : sachant $y$, l'ensemble A inclus tous les nombre entiers naturels qui sont plus petits que $y$.


___

## Couples / Tuples

!!! info "Définition"
    Un couple (ou un tuple) est un regroupement de 2 variables logiques, elle sont générallement groupé parce que c'est pratique pour le problème donné (ex : coordonées sur le plan)

Pour former des couples à partir de deux ensembles on utilise la notation suivante:
$A \times B = \{(x, y); x \in A \wedge y \in B\}$
$\neq$ $B \times A$
##### Exemple

- $A = \{x, y, z\}$
- $B = \{1, 2, 3, 4\}$
- $A \times B = \{(x,1),(x,2),(x,3),(x,4),(y,1),(y,2),(y,3),(y,4),(z,1),(z,2),(z,3),(z,4)\}$

##### Remarque
!!! warning "Attention"
    L'ordre est significatif.

    $(x, y) \neq (y, x)$

    ##### Exemple

    $(latitude, longitude) \neq (longitude, latitude)$

    Pointe vers 2 endroits défférents du plan

___

## Simplifications


- $n \in \mathbb{N} \Rightarrow [n] = \{1, 2, 3, 4 ... n\}$

- $a \leqslant b \leqslant c \Rightarrow (a \leqslant b) \wedge (b \leqslant c)$

- $\forall x \in A, P$ signifie $\forall x; x \in A \Rightarrow P$

- $\exists x \in A, P$ signifie $\exists x, x \in A \wedge P$

___

## Intervalles

- $a, b \in \mathbb{R} \Rightarrow [a, b] = \{n; a \leqslant n \leqslant b\}$
- $a, b \in \mathbb{R} \Rightarrow ]a, b[ = \{n; a < x < b\}$
- $a, b \in \mathbb{R} \Rightarrow ]a, b] = \{n; a < n \leqslant b\}$
- $a, b \in \mathbb{R} \Rightarrow [a, b[ = \{n; a \leqslant n < b\}$




##### Exemple

$A = \{(x,y); (x+3 = y) \cap (x \in \mathbb{Z}) \cap (x > -5) \cap (x< 4)\}$

$A = \{(-4,-1),(-3,0),(-2,1),(-1,2),(0,3),(1,4),(2,5),(3,6)\}$

___


## Parties d'un ensemble

!!! info "Définition"

    C'est comme si on imaginait tous les groupe d'élément que l'on peut faire avec les éléments d'un ensemble.

Si $A$ est un ensemble, alors $P(A) = \{ensemble \: des \: parties \: de \: A\}$

##### Exemples

- $A = \{1\}$

$P(A) = \{\emptyset, \{1\}\}$

$|P(A)| = 2$

- $B = \{1,2\}$

$P(B) = \{\emptyset, \{1\},\{2\},\{1,2\}\}$

$|P(B)| = 4$

- $C = \{1,2,3\}$

$P(C) = \{\emptyset, \{1\},\{2\},\{3\},\{1,2\},\{1,3\},\{2,3\},\{1,2,3\}\}$

$|P(C)| = 8$


!!! danger "Donc :"
    $|P_n| = 2^n$


___

## Exercices

### Vrai ou Faux

$A = \{1,4,7,8,9\}$

$B = \{8,9,10\}$

* $\forall x \in A \wedge x<10$
* $\forall x \in A \wedge \forall y \in B \wedge x<y$
* Enumerer : $\{y; y \in A \wedge(\forall x \in B, y<x)\}$
* $\forall x \in A, \exists y \in B, x < y$
* $\forall x \in A, \exists y \in B, y < x$
* $\exists y \in B, \forall x \in A, x<y$

??? success "Réponses"

    * $\forall x \in A \wedge x<10$ est vrai
    * $\forall x \in A \wedge \forall y \in B \wedge x<y$ est faux (contre-exemple : $x=8,y=8 \Rightarrow x=y$)
    * Enumerer : $\{y; y \in A \wedge(\forall x \in B, y<x)\} = \{1,4,7\}$
    * $\forall x \in A, \exists y \in B, x < y$ est vrai
    * $\forall x \in A, \exists y \in B, y < x$ est faux
    * $\exists y \in B, \forall x \in A, x<y$ est vrai

### Traduction phrases en expressions mathématiques

1. $\mathbb{N}$ est inclus dans $\mathbb{Z}$.
2. Tout nombre entier different de $-1$ et $+1$ est divisible par un nombre premier (on notera $P$ l'ensemble des nombres premiers).
3. $0$ est plus petit que n'importe quel entier non nul.

??? success "Réponses"

    1. $\mathbb{N} \subset \mathbb{Z} \iff \forall x \in \mathbb{N},x \in \mathbb{Z}$
    2. $\forall x \neq 1 \wedge x \neq -1 \wedge x \in \mathbb{Z} \wedge \exists y ; y \in \mathbb{P} \wedge x \% y == 0$
    3. $\forall x \in \mathbb{N}^* 0 < x$