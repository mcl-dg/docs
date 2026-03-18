# Récurrences

1. #### Le principe d'Hofstadter (au partiel)
> "Toute chose pour être faite prend plus de temps que ce qu'on a prévu au départ même si dans cette prévision on a tenu compte du principe d'Hofstadter"

2. #### Règle générale

!!! info ""

    - borne
    - formule générale
    - convergence

```racket
(define (somcarre n)
    (if (= n 0)
        0
        (+ n(somcarre(*(- n 1)(- n 1)))))) ;injuste
        (+ (* n n)(somcarre(- n 1))) ;juste
```

$\forall n \in \mathbb{N}^*, \; n-1$ est plus proche de $0$ que $n$.

$\forall x,y \in \mathbb{R}, x \neq y \; \; \;\rightarrow$ il y a autant d'éléments dans $[x,y]$ que dans $\mathbb{R}$


3.**Fonctions récursives**

* $fib(n)$
    * $0$ si $n = 0$
    * $1$ si $n = 1$
    * $fib(n-1) + fib(n - 2)$ sinon
* 0 1 1 2 3 5 8 13 21 34 55 89 144

```c
int fib(unsigned int n){
    int i,a,b,c;
    if (n<2) return n;
    a=0;
    b=1;
    for (i = 2; i<=n; i++){
        c = a + b;
        a = b;
        b = c;
    }
    return c;
}
```

|$n$|$log_2(n)$||
|-|-|-|
$1024$|$10$|k
$1000000$|$20$|M
$1000000000$|$30$|G
$10^{12}$|$40$|T
$10^{15}$|$50$|P
$10^{18}$|$60$

4.**Raisonnements par récurrence**


* $P_n \forall n$
* $P_0$ vrai
* $P_n \Rightarrow P_{n+1}$

### 

* $Q_n \forall n$ ?
* $P_0, P_1$ vrais
* $P_{n} \wedge P_{n+1} \Rightarrow P_{n+2}$

##### Exemple

$Q_n$ : $n$ a la même parité que $n+2$

- $Q_0$ vrai
- $Q_1$ vrai

Si $Q_n$ et $Q_{n+1}$,alors $Q_{n+2}$


## Exercices

**Démonstration 1**

* $A_n =(\displaystyle\sum^n_{i=0} i)^2 = (0+1+2+3+...+n)^2$
* $B_n =\displaystyle\sum^n_{i=0} i^3 = 0^3+1^3 + 2^3 + 3^3 + ... + n^3$

$A_n = B_n$

$A_0 = 0, A_1=1,A_2=9,A_3=36$

$B_0 =0, B_1 = 1, B_2 = 9, B_3=36$

!!! warning ""
    - Démontrer que $A_n=B_n \Rightarrow A_{n+1} = B_{n+1}$

??? success "Correction"

    **Initialisation** : $A_0 = B_0$

    **HR** : $A_n = B_n \Rightarrow A_{n+1} = B_{n+1}$

    **Heredité** : 

    $A_{n+1} = (\frac{(n+1)(n+2)}{2})^2 = \frac{(n+1)^2 (n^2 + 4n + 4)}{4}$

    $=\frac{n^2(n+1)^2}{4} + \frac{4n(n+1)^2}{4} + ...$

    $A_n = (\frac{n(n+1)}{2})^2$

    $B_n = A_n$

    $B_{n+1} = A_n +(n+1)^3$


**Démonstration 2**

- $fib(n) = \frac{1}{\sqrt{5}}(\varphi^n - \varphi'^n)$

- $\varphi = \frac{1 + \sqrt{5}}{2}$

- $\varphi' = \frac{1 - \sqrt{5}}{2}$

!!! warning ""

    Démontrer que :

    - vrai pour $0$ et $1$
    - vrai pour $n$ et $n+1$ alors vrai pour $n+2$

??? success "Correction"

    **Initialisation :**

    $B(0)$ vrai

    $B(1)$ vrai

    **HR :**

    Supposons que $B(n) \wedge B(n+1) \Rightarrow B(n+2)$

    **Hérédité :**

    * $f(n)= \frac{1}{\sqrt{5}} (\frac{1 + \sqrt{5}}{2})^n - \frac{1}{\sqrt{5}} (\frac{1 - \sqrt{5}}{2})^n$

    * $f(n+1) =\frac{1}{\sqrt{5}} (\frac{1 + \sqrt{5}}{2})^{n+1} -\frac{1}{\sqrt{5}} (\frac{1 - \sqrt{5}}{2})^{n+1}$

    * $f(n+2) =\frac{1}{\sqrt{5}} (\frac{1 + \sqrt{5}}{2})^{n+2} -\frac{1}{\sqrt{5}} (\frac{1 - \sqrt{5}}{2})^{n+2}$

    $=(\frac{1 + \sqrt{5}}{2})^{n+2} -(\frac{1 - \sqrt{5}}{2})^{n+2}$

    $=\frac{1}{\sqrt{5}} (\frac{1 + \sqrt{5}}{2})^{n+2} -\frac{1}{\sqrt{5}} (\frac{1 - \sqrt{5}}{2})^{n+2}$

    $=(\frac{1 + \sqrt{5}}{2})^{n} -(\frac{1 - \sqrt{5}}{2})^{n}$


    * $(1 + \sqrt{5})^{n+2} - (1- \sqrt{5})^{n+2} = 2(1 + \sqrt{5})^{n+1} -2 (1- \sqrt{5})^{n+1} + 4(1 + \sqrt{5})^n -4(1 - \sqrt{5})^n$

    $= (1 + \sqrt{5})^n (4 + 2 (1 + \sqrt{5})) - (1 - \sqrt{5})^n (4 + 2 (1- \sqrt{5}))$

    $= (1 + \sqrt{5})^n (6 + 2 \sqrt{5}) - (1 - \sqrt{5})^n (6 - 2 \sqrt{5})$


    * $(1 + \sqrt{5})^n ((1 + \sqrt{5}) \times (1 + \sqrt{5})) - (1 - \sqrt{5})^n((1 - \sqrt{5}) (1- \sqrt{5}))$

    $= (1 + \sqrt{5})^n (1 + \sqrt{5} + \sqrt{5} + 5) - (1 - \sqrt{5})^n (1 - \sqrt{5} - \sqrt{5} + 5)$

    $=(1 + \sqrt{5})^n (6 + 2\sqrt{5}) - (1 -\sqrt{5})^n (6-2\sqrt{5})$ **Vrai**


**Démonstration 3**
!!! warning ""
    * $P_n$ : $\forall n \; \exists a,b \in \mathbb{Z}$ et $(1 +\sqrt{2})^n = a + b\sqrt{2}$

??? success "Correction"

    * $P_0$ : $\exists a,b / (1 + \sqrt{2})^0 = a + b\sqrt{2}$
    * $P_1$ :

    $a = 1;    b=0;
    a = 1;    b= 1$

    * $P_2$ : $(1+\sqrt{2})^2 = 1 + 2 \sqrt{2} + 2 = 3 + 2\sqrt{2}$

    * $\sqrt{5} \times \sqrt{5} = 5^{1/2} \times 5^{1/2} = 5^{1/2 +1/2} = 5^1 = 5$

    $P_n \Rightarrow P_{n+1}$

    $(1 + \sqrt{2})^n =a + b \sqrt{2}$

    $(1+\sqrt{2})^{n+1} = c + d\sqrt{2}$

    $(1+\sqrt{2})^n \times (1 + \sqrt{2}) = (a+b\sqrt{2}) (1+\sqrt{2})$

    $= a +a \sqrt{2} + b\sqrt{2} + b *2$

    $=(a+2b) + (a+b) +\sqrt{2}$


**Démonstration 4 : Nombre de sommets d'un arbre binaire en fonction de sa profondeur maximale**


|$P_n$|nb_sommets_max||nb_feuilles|
|-|-|-|-|
|-1|0||0
|0|1||1
|1|3|$2^2 -1$|2
|2|7|$2^3 -1$|4
|3|15|$2^4 -1$|8
||31|
||63|$2^{p+1} -1$
||127|
||255|
||511|
||1023|

??? success "Correction"

    **Initialisation :**

    vrai pour $p=0$

    **HR :**

    $nbs(p) = 2^{p+1} -1$

    $nbs(p+1) = 2^{p+2} -1$

    **Hérédité :**

    $nbs(p+1) = f(nbs(p),p)$

    $nbs(p+1) = 2 \times nbs(p) +1 =2(2^{p+1} -1) + 1 = 2^{p+2} -1$

**Démonstration 5**

!!! warning ""

    Démontrer que :

    - $\forall n \exists a,b ; (1 + \sqrt(2))^n = a + b \sqrt{2}$

??? success "Correction"

    **Initialisation :**

    $P(0)$ Vrai

    $P(1)$ Vrai

    **HR :**

    $P(n) \Rightarrow P(n+1)$

    $\exists a,b;\forall n \exists a,b ; (1 + \sqrt(2))^n = a + b \sqrt{2} \Rightarrow \exists c,d ; (1 + \sqrt{2})^{n+1} = c + d\sqrt{2}$

    **Hérédité :**

    $(1+ \sqrt{2})^2 = a + b \sqrt{2}$

    $(1+ \sqrt{2})^{n+1} = (a + b \sqrt{2})(1+\sqrt{2})$

    $= a + b\sqrt{2} + b\sqrt{2} + b(\sqrt{2} * \sqrt{2})$

    $= a + 2b + (a +b) \sqrt{2}$

    $c=a+2b$

    $d=a+b$

**Démonstration 6**

!!! warning ""

    Démontrer par récurrence que :

    - $\forall a,b \in \mathbb{Z},a^2 - b^2 =(a - b)(a + b)$

??? success "Correction"

    - Notons cette propriété $P(n)$. Démontrons d'abord $P(0)$, puis $P(n) \Rightarrow P(n+1)$.

    - Pour $n = b$ : 
        - **Initialisation :**
        $P(0) \iff a^2 - 0^2 = (a - 0)(a + 0) \iff a^2 = a^2$
        - **HR :**
        $P(n) \iff a^2 -n^2 = (a-n)(a+n)$
        - **Hérédité :**

            $P(n+1) \iff a^2 - (n+1)^2 = (a - (n+1))(a + (n+1))$
            
            $\iff a^2 -n^2 - 2n -1 = ((a - n)-1)((a+n) +1)$
            
            $\iff a^2 -n^2 - 2n -1 =(a-n)(a+n) + (a-n) \times 1 + (-1)(a+n)+(-1) \times 1$
            
            $\iff a^2 -n^2 - 2n -1 = (a-n)(a+n) + a - n -a - n - 1$
            
            $\iff a^2 -n^2 - 2n -1 = (a-n)(a+n) -1 -2n  \; \; \;\; \; vrai$

---

**Démonstration 7**

!!! warning ""

    Démontrer que

    - $\displaystyle\sum^{n}_{i=0} i = \frac{n(n+1)}{2} \iff 0 + 1 + 2 + ... + n = \frac{n(n+1)}{2}$


    **A démontrer :** $\displaystyle\sum^{n}_{i=0} i = \frac{n(n+1)}{2} \Rightarrow \displaystyle\sum^{n+1}_{i=0} i = \frac{(n+1)(n+2)}{2}$

??? success "Correction"

    **Initialisaton :**

    - $P(0) \iff 0 = 0$

    - $P(1) \iff 1 = 1$

    - $P(2) \iff 3 = 3$

    > *"So far so good."*

    **HR :**

    - $0 + 1 + 2 + ... + n = \frac{n(n+1)}{2}$

    **Heredité :**

    - $\displaystyle\sum^{n}_{i=0} i + n + 1 = \frac{(n(n+1) +2 (n+1))}{2}= \frac{n(n+1)}{2} + n+ 1$

---

**Démonstration 8**

Soit $sc(n)$, la somme des carrés des entiers de $0$ à $n$.


!!! warning ""

    #### 1. Trouver la formule :
    - $sc(n) = \displaystyle\sum^{n}_{i=0} i^2 =?$

|$n$|0|1|2|3|4
|-|-|-|-|-|-
|$sc$|0|1|5|14|30
|$n^2$|0|1|4|9|16
|$n^3$|0|1|8|27|64


??? success "Correction"

    - $s(n) = an^3 +bn^2 + cn + d$
    - $s(0) =0 \Rightarrow d = 0$
    - $s(1) =1 \Rightarrow a + b + c =1 \iff a=1-b-c$
    - $s(2) =5 \Rightarrow 8a + 4b + 2c =5 \Rightarrow8(1-b-c) +4b +2c =5$
        $\iff 8 - 4b - 6c = 5$
        
        $\iff 3 = 4b -6c$
        
        $\iff b = \frac{3-6c}{4}$

    - $s(3) = 14 \Rightarrow 27a +9b + 3c = 14 \Rightarrow 27(1-b-c) + 9b + 3c = 14$

        $\iff 27(1- \frac{3-6c}{4} -c) + 9 (\frac{3-6c}{4}) + 3c = 14$

        $\iff 14 = 27 - \frac{3 \times 27}{4} + 27 \times \frac{6c}{4} - 27c + \frac{27}{4} - \frac{54c}{4} + 3c$

        $\iff 0 = 13 - \frac{27}{2} + c(\frac{27 \times 6}{4} - 27 - \frac{54}{4} + 3)$




    $c = \frac{1}{6}$

    $b = \frac{3- \frac{6}{6}}{4} = \frac{1}{2}$

    $a = 1 - \frac{1}{2} - \frac{1}{6} = \frac{2}{6}$

    **Donc** $s(n)= \frac{1}{6}(2n^3 + 3n^2 + n) \iff \frac{n(2n+1)(n+1)}{6}$
___

!!! warning ""

    #### 2. Demontrer par récurrence que $s(n)$ est vrai pour tout $n$.

??? success "Correction"

    **Initialisation :**

    - $P(0) : \displaystyle\sum^{n}_{i=0} i^2 = \frac{1}{6}(2 \times 0^3 + 3 \times 0^2 + 0) = 0$

    **HR :**

    - $s(n)= \frac{1}{6}(2n^3 + 3n^2 + n)$

    **Hérédité :**

    - $P(n) \Rightarrow P(n+1)$

        $sc(n+1) = \frac{1}{6}(2(n+1)^3 + 3(n+1)^2 + n+1)$

        $\iff sc(n+1) = \frac{1}{6}(2n^3 + 6n^2 + 6n + 2 + 3n^2 + 6n + 3 + n + 1)$

        $\iff sc(n+1) = \frac{1}{6}(2n^3 + 9n^2 + 13n +6)$

        $\iff sc(n+1) = \frac{1}{6} (2n^3 + 3n^2 + n) + \frac{1}{6} (6n^2 + 12n + 6)$

___
**Démonstration 9**

!!! warning ""

    - $u_0 = 1$

    - $u_{n+1} = u_n + 2n + 3$

    Demontrer que $u_n = (n+1)^2$


??? success "Correction"

    - $P(0) \Rightarrow u_0 = 1 = (0+1)^2$

    - $P(n) \Rightarrow P(n+1)$

    - $P(n) \iff u_n = (n+1)^2 \Rightarrow P(n+1) \iff u_{n+1} = (n+2)^2$

        $\iff u_{n+1} = u_n + 3 = (n+2)^2$

        $= (n+1)^2 +2n + 3$

        $= n^2 + 2n + 1 + 2n + 3$

        $= n^2 + 4n + 4 = (n+2)^2$ 

___

**Démonstration 10**

!!! warning ""

    **Démontrez que**

    $\displaystyle\sum^n_{i=0} i^3 = (\displaystyle\sum^n_{i=0} i)^2 = (\frac{n(n+1)}{2})^2$

??? success "Correction"

    $P(n) \iff s(n) = (\frac{n(n+1)}{2})^2$

    **Initialisation**

    - $P(0) \iff s(0)= 0$

    **Ce qu'on doit démontrer**

    - $P(n) \Rightarrow P(n+1)$

    **Hérédité**

    - $s(n) = (\frac{n(n+1)}{2})^2 = 0^3 + 1^3 + 2^3 +...+n^3$

    - $s(n+1) = (\frac{(n+1)(n+2)}{2})^2 = 0^3 + 1^3 +...+n^3 + (n+1)^3$

        $= (\frac{n \times (n+1) + 2(n+1)}{2})^2  = (\frac{n \times (n+1)}{2})^2 + (n+1)^3$

        $= \frac{(n \times (n+1))^2 + 4 \times n \times (n+1) \times (n+1)  + 4(n+1)^2}{4}$

        $= \frac{(n \times (n+1))^2}{4} + \frac{4n(n+1)^2}{4} + \frac{4(n+1)^2}{4}$

        $= \frac{(n \times (n+1))^2}{4}+ \frac{4n(n^2 + 2n + 1)}{4} + \frac{4(n^2 + 2n + 1)}{4}$

        $= \frac{(n \times (n+1))^2}{4} + n^3 + 2n^2 + n + n^2 + 2n +1$

        $=\frac{(n \times (n+1))^2}{4} + n^3 + 3n^2 + 3n + 1$

        $= \frac{(n \times (n+1))^2}{4}+(n+1)^3$

___

## Croissance d'une suite démontrée par récurrence

##### Exemple

!!! warning ""

    - $u_0 = 2$
    - $u_{n+1} = \frac{1}{3} u_n +2$
    - $u$ est croissante ?


??? success "Correction"

    $P(0) : u_1 > u_0$

    $P(n) : u_{n+1} > u_n$

    $P(n+1) : u_{n+2} > u_{n+1}$

    **Hérédité :** Supposons $P(n)$ vraie, donc $u_{n+1} > u_n$
    Montrons que $P(n+1)$ vraie, donc $u_{n+2} > u_{n+1}$

    $u_{n+1} > u_n$

    $\iff \frac{1}{3} (u_{n+1}) > \frac{1}{3} u_n$

    $\iff \frac{1}{3} (u_{n+1}) + 2 > \frac{1}{3} u_n +2$

    $\iff u_{n+2} > u_{n+1}$

