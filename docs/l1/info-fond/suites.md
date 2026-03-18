# Suites


!!! info ""

    * $u \; \mathbb{N} \rightarrow E / \mathbb{N} \; \mathbb{Z} \; \mathbb{R}$

    * $u(i) = y$



## Suites numérique 


!!! info ""

    * $u(i)$ est le $i$ ème mot du dictionnaire
    * $|dictionnaire| \geqslant 50 \; 000$


### 2 façons de désigner une suite numérique

!!! danger ""

    1.  
        * $u(i)=fct(i)$
        * $u(i)=g(u(i-1))$



    2. **Formule implicite**

    $u(i) = \displaystyle\sum^i_{j=0} j$
    * $u(0) = 0$
    * $u(n+1) = u(n) + n + 1 \rightarrow fonction \; recursive$


##### Exemple concret

!!! success "Exemple"

    Vous placez 1000€ à 3 % par an (calculé une fois par an).

    |an|0|1|2|3|
    |-|-|-|-|-|
    |montant|1000|1030|1060.9|1092.2

    ##### Pour touver la formule generale
    * $u(0) = 1000$
    * $u(n+1) = u(n) + 0.03 \times u(n) = (1.03) \times u(n)$
    * $u(n) = 1000 \times (1.03)^n$

    ##### Calcul de $u(1)$ et $u(2)$
    * $u(1) = 1000 \times (1.03)$
    * $u(2) = 1000 \times (1.03)^2$

## Croissance des suites


### Rappel



$u_i = f(i) = g(i-1)$
$u : \mathbb{N} \rightarrow \mathbb{R}$



!!! danger ""
    $u_i$ est croissante ?

    Regarder $signe(u_{i+1} - u_i)$


##### Exemple

!!! success ""

    $u_i = i^2 -5i +6$

    $u_0 = 6$

    $u_1 = 2$

    $u_2 = 0$

    $u_3 = 0$

    $u_4 = 2$

    $u_5 = 6$

    La suite est croissante à partir de $u_3$

    $diff(i+1) = u_{i+1} - u_i = (i+1)^2 - 5(i+1) +6 - i^2 +5i -6$

    $= i^2 + 2i +1 -5i -5 +6 -i^2 + 5i - 6$

    $= 2i -4$