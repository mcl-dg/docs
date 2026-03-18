# Chapitre 4 : Suites numériques et domination

On cherche des moyens pour décrire une suite infinie de nombres.

**Exemple de suite :** 1 2 4 8 16 32
___
## Definition formelle : suite numérique

Une suite numérique est une application de $\mathbb{N}$ vers $\mathbb{R}$

On peut (entre autres) définir une suite : 

-	Par une expression directe : $u(n) = 2^n$ ou $u : n \rightarrow 2^n$
-	Ou par une definition recursive : $u(0) = 1, u(n+1) = 2 u(n)$

On préfère, quand c’est possible, des expressions directes.
___
## Exemples de suites

Habituellement $n$ est le nom de la variable.

-	Suite constante : $V(n) = 4 ; V : 4\; 4\; 4\; 4\; 4…$
-	Suite quadratique : $H(n) = n^2 = n \times n ; H : 0\; 1\; 4\; 9\; 16\; 25\; 36…$
-	Suite factorielle : $N(n) = n! = n \times (n-1) \times (n-2)… 3 \times 2 \times 1	\;;\;N :1(par\; convention)\; 1\; 2\; 6\; 24\; 120\; 720…$
-	Suite geometrique : $U(n) = 2^n = 2 \times 2 \times 2 \times … \times 2\; ; \;	U : 1\; 2\; 8\; 16\; 32…$
-	Suite logarithmique : $K(n) = log_2(n)\; ;	\; K : Nan\; 0\; 1\; 1,58…\; 2\; 2,32…\; 2,58…\; 2,80…\; 3…$
-	Suite racine carré : $L(n) = \sqrt{n}\;;\;	L : 0\; 1\; 1,41…\; 1,73…\; 2\; 2,23…\; 2,64…\; 2,82…\; 3 …$


Les algorithmes les plus performants sont ceux dont la complexité croît le plus lentement ($log_2(n)$)

___

## Definition : domination

Soient $(V_n)$ et $(D_n)$ deux suites numériques. On dit que $D$ domine $V$ si

$\exists M \in \mathbb{R}, \exists N_0 \in N, \forall n > N_0, |V_n| \leq M |Dn|$

Où $|x|$ represente la valeur absolue de $x$

### Remarques :
-	Si la suite $D$ ne s’annule plus au bout d’un certain terme, on a : $D$ domine $V$ si et seulement la suite $n \rightarrow \frac{(V_n)}{(D_n)}$ est bornée.
-	Pour 2 suites quelconques, on n’a pas forcément que l’une domine l’autre.

### Notations
-	Si $D$ est une suite on note $O(D)$ l’ensemble des suites dominées par $D$.
-	Si $U$ est une suite on note $\Omega(U)$ l’ensemble des suites qui dominent $U$. (Attention $\Omega$ signifie autre chose en théorie des nombres)
-	Par convention on écrit $U = O(D)$ plutôt que $U \in O(D)$
-	Pour indiquer que $U$ est dominée par $D$ on peut écrire $U<<D$, ou $U= O(D)$ ou $D = \Omega(U)$ (ou $D>>U$).

**Exemple :**

$n = O(n^2)$
$n<<n^2$


___

## Propriétés :
Soient $U,V,W$ des suites (quelconques) et $m$, $w$ des nombres réels (quelconques) alors :

-	Si $U<<V$ et $V<<W$ alors $U<<W$
-	Si $U, V<< W$ alors $mU + V <<W$
-	Si pour tout $n \in \mathbb{N}, |V_n| \leq |m| |W_n|$ alors $V<<W$
-	L’ensemble $O(1)$ est l’ensemble des suites bornées
-	L’ensemble $O(V)$ est égale à l’ensemble $|V|$. $O(1)$
($= \{(v_n \times U_n)_{(n \in \mathbb{N})} /U$ suite bornée$\}$)


**Remarque :** Si $U, F, W$ sont des suites alors
-	$U<<U$
-	$O(U) O(F) = O(F.U)$
-	Si $U<<W$ alors $U.V<<M.V.$

___

## Notation :

Si $U$ et $V$ sont des suites et que on a $U<<V$ et $V<<U$ on note $U = \Theta(V)$ (ou $V = \Theta(U)$ c’est une relation d’équivalence).


## Illustration :

Dans la suite la variable est $n$ et $a,b,c$ sont des nombres positifs non nuls avec $c>1$

-	$log_a(n) << n^b << c^n << n ! << n^n$ (et pas d’égalité de classe)
-	si $a < b$ alors $n^a << n^b$ (et $n^b \neq O(n^a)$)
-	si $a < b$ alors $a^n << b^n$ (et $b^n \neq O(a^n)$)
-	$1 = O(n)$ mais $n \neq O(1)$
-	$4n^5 + 3n^4 + 10n + 20 = \Theta(n^5)$
-	$log_a n = \Theta(log_b n)$ (si $a$ et $b$ différents de $1$)
-	$n log_a n \neq O(log_a n)$ mais $log_a n  = O(n log_a n$) (si $a \neq 1$)
