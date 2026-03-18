# Les fonctions

## Fonction Partielle

!!! info "Definition"

    Une fonction est type de relation, dans lequel un élément de départ a **AU PLUS** _une_ relation dans l'ensemble d'arrivée.

    Autrement dit:

    $\forall x \in A ; (I_x = \{y; f(x) = y\}) \wedge |I_x| \leq 1$


### Domaine de définition d'une fonction

!!! info "Définition"

    Soit $X$ l'ensemble de départ, et $Y$ l'ensemble d'arrivée.

    Le domaine de définition d'une fonction est l'ensemble des éléments de $X$ qui ont une image dans $Y$
    

- $Domaine(f) = \{x; |I_x|=1\}$


### L'image

- d'une variable :
    
    $image(x) = y \iff f(x) = y$

- d'un ensemble :

    $image(A) = \{y; \exists x \in A \wedge f(x) = y \}$

### Egalité entre deux fonctions

!!! info "Définition"

    2 fonctions $f$ et $g$ sont égales si :

    - Elles ont le même domaine de définition :

        $Domaine(f) = Domaine(g)$

    - $\forall x \in Domaine, f(x) = g(x)$

##### Exemple

$f(x) = \frac{(x-3) \times (x^2 -2x +1)}{x-3}$

$g(x) = (x - 1)^2$

- $f$ et $g$ sont-elles égales ?

??? success "Réponse"

    $Domaine(f) = \mathbb{R}$ \ $\{3\}$

    $Domaine(g) = \mathbb{R}$

    **Conclusion :** $f$ et $g$ ne sont pas égales.


## Application

!!! info "Définition"

    Une application est un cas spécifique de fonction qui associe à chaque valeur de l'ensemble de départ une valeur dans l'ensemble d'arrivée. ( Tous les $x$ ont une image par $f$ )

    Une application de $A$ vers $B$ se note $f: A \rightarrow B$.

    L'ensemble des applications de $A$ vers $B$ se note $B^A$.

    $Domaine(f) = A$


##### Exemple

- $X = \{0,1,2,3\}$
- $Y = \{a,b,c\}$
- $G_f = \{(0,a),(1,c),(3,a)\} \subseteq X \times Y$

$f$ est une fonction mais pas une application car $2 \in X$ n'a pas d'image

## Composition de fonctions

!!! info "Définition"

    $(f \circ g)(x) = f(g(x))$

### Chaîne d'application

!!! info ""
    Si:

    - $x \in A$
    - $f : A \rightarrow B$
    - $g : B \rightarrow C$

    Alors:

    - $g \circ f : A \rightarrow C$
    - $(g \circ f)(x) = g(f(x))$

##### Exemple

- $g(x) = x+4$
- $h(x) = x^2 -x$

##### Questions

1. Exprimer $h(g(x))$ et calculer $h(g(2))$.
2. Expimer $g(h(x))$ et calculer $g(h(2))$.

##### Reponses

??? success "Réponses"
    
    1. $h(g(x)) = (x+4)^2 - (x+4)$

        $h(g(2)) = 30$
    2. $g(h(x)) = (x^2 - x) + 4$

        $g(h(2)) = 6$



## Injection

!!! info "Définition"

    Une injection est une application.

    Pour que ce soit une injection il faut que chaque élément de l'ensemble d'arrivée ai **AU PLUS** 1 antécédent.

    $\forall x \in B ; \forall a,b \in A ; f(a) == x \wedge f(b) == x => a == b$


##### Exemple

$f(x) = x^2$

$\mathbb{N}$ injection

$\mathbb{Z}$ ¬injection

$\mathbb{R}$ ¬injection

## Surjection

!!! info "Définition"

    Une Surjection est une application.

    Pour que ce soit une surjection, il faut que chaque élément de l'ensemble d'arrivée ai **AU MOINS** 1 antécédent.

    $\forall x \in B ; \exists a \in A ; f(a)==x$

## Bijection

!!! info "Définition"

    Une bijection est une application.

    Pour que ce soit une Bijection il faut que ce soit à la fois une injection et une surjection.
    
    C'est à dire qu'il existe **UN ET UN SEUL** antécédent par élément d'arrivée.

    $\forall x \in B; \exists!a \in A; f(a)==x$

![](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7b/Surjection_Injection_Bijection-fr.svg/700px-Surjection_Injection_Bijection-fr.svg.png)

|||||||||
|-|-|-|-|-|-|-|-|
|***5***|20|26||||||
|***4***|14|19|25|
|***3***|9|13|18|24|
|***2***|5|8|12|17|23|
|***1***|2|4|7|11|16|22|
|***0***|0|1|3|6|10|15|21|
||***0***|***1***|***2***|***3***|***4***|***5***|***6***|

!!! warning ""

    **Propriétés**

    $\mathbb{N \times N} \rightarrow \mathbb{N}$

    $(a,b) \rightarrow f(a,b)$

    **Bijection**

    $|\mathbb{N \times N}| == |\mathbb{N}|$

    c'est impossible sur $\mathbb{R}$

    $|\mathbb{R \times R}| \neq |\mathbb{R}|$

    $|\mathbb{R \times R}| == |\mathbb{C}|$



## Fonctions identité

!!! info "Définition"

    * si $f$ est une bijection $\exists g ,f \circ g = g \circ f = Id$
    * $g$ peut s'écrire $f^{-1}$



##### Exemples


1. 
    * $f(x) = 3x +2$
    * $g(y) = \frac{y - 2}{3}$


2. 
    * $f(g(y)) = 3 (\frac{y-2}{3}) +2 = (y-2) +2 = y$
    * $g(f(x)) = \frac{(3x +2) -2}{3} =\frac{3x + 2 -2}{3} = x$

3. 
    * $\mathbb{R}+ \rightarrow \mathbb{R}+$
    * $f(x) = \sqrt{x}$
    * $g(y) = y^2$

4. 
    * $f(x)= cos(x)$
    * $g(y) = arccos(y)$

## Fonctions caractéristiques

!!! info "Définition"

    * Soit $E$ et $D \subset E$
    * $f:$ fonction caractéristique de $D$
    * $\forall x \in E,$
        * $f(x) = 1$ si $x \in D$
        * $f(x) = 0$ sinon





#### Exemple pour $D \subset E$ avec $E = \mathbb{R}$ et $D = \mathbb{R}^+$
```c
int fctcar(long double x){
    if (x>=0.0){
        return 1;
    }
    return 0;
}

```

## Image

* $f : E \rightarrow F$
* $A \subset E$
* $G = \{y; \exists x, (x \in A) \wedge f(x) = y\}$
* $G = f(A)$

## Image Réciproque

!!! info ""
    image réciproque = ensemble de départ

* $f : E \rightarrow F$
* $B \subset F$
* $G = \{x; \exists y, (y \in B) \wedge (f(x)=y)\}$
* $G = f^{-1}(B)$ (c'est abusif)

### Exemples
* $\mathbb{R} \rightarrow \mathbb{R}$

#### Carré
* $f(x) = x^2$

* $G = f(\mathbb{R}) = \mathbb{R}^+$

#### Cosinus

* $f(x) = cos(x)$
* $G = f(\mathbb{R}) = [-1,1]$

Image Réciproque
$f^{-1}(\mathbb{R}^+) = \mathbb{R} \subset \mathbb{R}$
$f^{-1}([-1,1]) = \mathbb{R}$


#### Tangente

* $f(x) = tan(x) = \frac{sin(x)}{cos(y)}$
* $G = tan(\mathbb{R}) = \mathbb{R}$

## Parties d'un ensemble

* $E,R$
* $P(E) = \{x; x \subset E\}$
* $E$ discret, dénombrable (ex : $\mathbb{N}$... mais pas $\mathbb{R}$)

* $f : E \rightarrow F$
* $f$ induit application de $P(E)$ vers $P(F)$

|card(E)|card(P(E))|nb$\emptyset$|nb1|nb2|nb3|nb4|nb5
|-|-|-|-|-|-|-|-|
|0|1|1|
|1|2|1|1
|2|4|1|2|1
|3|8|1|3|3|1
|4|16|1|4|6|4|1
|5|32|1|5|10|10|5|1