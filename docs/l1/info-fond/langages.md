# Langages

### 1. Mots

!!! info "Définition : Alphabet"

    Soit $A$ un ensemble fini "de lettres"

    $A$ est appelé alphabet.

    $A = \{red,green,blue\}$

    $Mot = \{abc...z / a \in A, b \in A,c \in A...\}$

    $(red) (green red)$

    $A^*$ : l'ensemble de tous les mots sur $A$



##### Exemple

* $A = \{0,1\}$
* $A^* =\{\epsilon,0,1,00,01,10,11\}$
* $B =\{x \in A^* \wedge |x| < 9\}$

* $B =\{\epsilon,0,1,00,01,10,11,000,001,010,011...\}$
    * Donc $|B| \simeq2^8-1$


#### Démonstration

$B_i = \{x \in B \wedge |x| = i\}$

|$B_0$|$\epsilon$|nb_element
|-|-|-
|$B_1$|$0,1$|2
|$B_2$|$00,01,10,11$|4
|$B_3$||$8$
|||
|$B_8$||$256$

Donc $|B_i| = 2^i$

$B = B_0 \cup B_1 \cup B_3 ...B_8$


$|B| = |B_0| + |B_1| + |B_2| + ...+ |B_8|$

$=2^0 + 2^1 + 2^n + ... + 2^8$

$=\displaystyle\sum^8_{i=0} 2^i = 2^9 -1$

!!! danger ""

    **Formule générale**

    $\forall i, |B_i| = 2^{i+1}-1$


#### Rappel:

> **Longueur d'un mot :** le nombre de lettre.

> **Cardinal (noté | |):** le nombre d'élément.

### Mots et concaténation

Souvent la concaténation entre 2 mots $m$ et $p$ est notée $m.p$ ou $mp$

$|mp| = |m| + |p|$

### Duplication

$m^2 = m.m$

$m^3 = m.m.m$

$|m^i| = |m| \times i$

$A^* = A^0 \cup A^1 \cup A^2 \cup... A^\infty$

Ordre dans l'alphabet : $<_A$

### Propriétés

!!! warning ""

    Soit l'ordre lexicographique : $<_{lex}$

    1. $\forall m \in A^*$ \ $\epsilon$, $m>_{lex} \epsilon$

    2. $\forall x,y \in A$

        - Si $x<_{lex}y$ alors $\forall a,b \in A, xa <_{lex} yb$

            **Exemple :**

            - $'a'<'b'$
            -  $'abc'<'baaa'$

    3. $\forall w,m,v \in A^*$

        - Si $w<_{lex}v$ alors $mw<_{lex}mv$

            **Exemple :**

            - $cos < sin \Rightarrow arccos < arcsin$

### Ordre militaire ($<_{mil}$)

$w,m \in A^*, w<_{mil} m$ si et seulement si :

* Soit $|w| <|m|$
* Soit $|w| = |m|$

##### Exemple
- $1 <_{mil} 00$
- $11 >_{mil} 10$



#### Exercice
$w= aba, m= caba, v=\epsilon$

1. $A = \{a,b,c\}$
2. $|w| = 3, |n| = 4, |u| = 0$
3. $wm = abacaba, wmw = abacabaaba, vwm^2 = abacabacaba$
4. Soient $z$ et $y$
    - $k = |z|, j = |y|$
    - $|zy| = k + j$
    - $|zyz^2| = 3k +j$
    - $|z^2 y| = 2k + j$

5. **Mirroir (reverse)**
    - $a = 'ete'$
    - $a^{-1} = 'ete'$
    - $m^{-1} = abac$
    - $|w^{-1}| = |w| = 3$
    - $a = 'conca'$
    - $b = 'tener'$
    - $(ab)^{-1} = b^{-1}a^{-1}$ **(formule à démontrer)**

### Démonstration : $(ab)^{-1} = b^{-1}a^{-1}$

- **Initialisation :**
$|b| = 0, (a.b)^{-1} = b^{-1}a^{-1}$

- **HR :**
$|b| = n,$ alors $(a.b)^{-1} = b^{-1} a^{-1}$

- **Hérédité :**

    $|c| = n+1$ alors $(a.c)^{-1} = c^{-1} a^{-1}$

    $c =d.x$ où d est un mot $|d| = n$

    $x$ est une lettre $(x \in A)$

    On a déjà : $(a.d)^{-1} = d^{-1}.a^{-1}$

    $(a.d.x)^{-1} = (d.x)^{-1}.a^{-1}$

    $x.(a.d)^{-1} = x.d^{-1}.a^{-1}$




## Rappels

- $L = \{w...\}$
- $M = \{v...\}$
- $LM = \{x; x:wv,w \in L, v \in M\}$
- $L^* = \{\epsilon, w, w_1,v_2,w_1 w_2 v_2, ...\}$
- $L^+ = \{w,w_1,v_2,w_1 w_2v_2...\}$


$L =\{a,b\}$

$L^*= \{\epsilon, a,b,ab,aa,ba,bb,aaa,aab,aba,baa,abb,bab,bbb...\}$

$L^0 = \{w ; |w| = 0\}$

$L^1 = \{w ; |w| = 1\}$

$L^2 = \{w ; |w| = 2\}$

$L^* =L^0 \cup L^1 \cup L^2 \cup L^3 \cup ...$


$L^0 =\{\epsilon\}$

$L^1 =\{b,a\}$

$L^2 = \{ba,bb,aa,ab\}$

$L^3 = \{bba,bbb,baa,bab,aba,abb,aaa,aab\}$

##### Exemple

- $M= \{ab,c,d\}$
- $L =\{b,a\}$
- $L.M = \{bab,bc,bd,aab,ac,ad\}$
- $M.L = \{abb,aba,cb,ca,db,da\}$
- $|M.L.M| =18$



## Expressions régulières

!!! info "Définition"
    $E$ est une regex sur un alphabet $A$

    $\iff$

    - $E = \emptyset$ ou,

    - $E =\epsilon$ ou,

    - $E=a$ avec $a \in A$, ou,

    - $E = E_1 | E_2$ et $E_1 et E_2$ sont des regex sur $A$, ou,

    - $E= E1.E_2$ et $E_1 et E_2$ sont des regex sur $A$, ou,

    - $E=E_1^*$ et $E_1$ est une regex sur $A$.

##### Exemple

$ab^* = \{\epsilon, a, ab,abb,abbb...\}$

$(ab)^* = \{\epsilon, ab,abab,ababab...\}$

$(a|b)^* = \{\epsilon,a,b,aa,bb,ab,ba...\}$

$(a|b)(c|b) \Rightarrow \{ac,ab,bc,bb\}$

$(a|ba)^* \Rightarrow \{\epsilon,a,ba,aba,baa,aa,baba,a...\}$

$a(aa|b(ab)^* a)^*a : \{aa,aaaa,abaa,aaaaaa,ababaa,ababaa,...\}$