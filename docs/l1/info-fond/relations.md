# Relations

!!! info "Définition"

    L'objectif est de créer des ensembles de tuple où les valeurs ont un lien logique (exemple : déduire l'une de l'autre avec un calcul)

    Soit $A,B$ deux ensembles.

    $R \ \{(x,y); x \in A \wedge y \in B\}$

##### Exemples

- $A = \{a,b,c,d\}$
- $B = \{1,2,3\}$
- $R = \{(a, 1), (b, 1), (c, 1), (d, 1), (b, 2), (c,3) \}$
- $(a,b) \in R$ s'écrit  $aRb$

Relations internes $(A==B)$
$\mathbb{N} \mathbb{N} : R = \{(a,b) ; a \in \mathbb{N} \wedge b \in \mathbb{N} \wedge a == b * b\}$
$\Rightarrow \{(0,0),(1,1),(4,2),(9,3),(16,4)\}$

___

### Propriétés et catégories

!!! danger "Propriétés"

    - #### Reflexivité:

        $\forall a ; aRa$

    - #### Irreflexivité:

        $\forall a ; \overline{aRa}$

    - #### Symétrie:

        $\forall a, b ; aRb \Rightarrow bRa$

    - #### Antisymétrie:
        
        $\forall a,b ; ((aRb) \wedge (bRa)) \Rightarrow a == b$

        signifie que la seule façon d'avoir de la symétrie c'est que les 2 valeurs soit égales

    - #### Transitivité:

        $\forall a,b,c ;aRb \wedge bRc \Rightarrow a Rc$

___

### Relation d'équivalence (symbole : $\equiv$)

!!! info "Relation à la fois :"

    - Réflexive
    - Symétrique
    - Transitive


##### Exemple

- $aRb \iff a==b$

#### Écriture de partition d'un ensemble
une partition de $\mathbb{N}$ en $a$ sous-ensembles se note $\frac{\mathbb{N}}{a\mathbb{N}}$

___

### Relations d'ordre Large

!!! info "Relation à la fois :"

    - Réflexive
    - Antisymétrique
    - Transitive

##### Exemple
La relation "$\leq$" est d'ordre large.

___

### Relation d'ordre Stricte
!!! info "Relation à la fois :"

    - Irréflexive
    - Transitive

##### Exemple

- La relation "$<$" est d'ordre stricte.

___

### Relation d'ordre Total

!!! info "Définition"
    Relation qui relis toutes les valeurs dans un sens OU (logique) dans un autre.
    
    - $\forall a,b; (aRb) \vee (bRa) \vee a == b$

    Autrement dit, tous les éléments sont comparables.

##### Exemple

- $\leq$

    car $\forall a,b \in \mathbb{R},a \leq b \vee b \leq a$

### Relation d'ordre Partiel

!!! info "Définition"
    
    Relation d'ordre qui n'est pas total.

    Tous les éléments ne sont pas comparables.

##### Exemple

- $\subseteq$

    Soit $E$ un ensemble. Pour deux sous-ensembles quelconque $A$ et $B$ de $E$, $A \subseteq B \vee B \subseteq A$ n'est pas toujours vrai.





## Majorant

!!! info "Définition"

    $(E,\leq)$`//(relation d'ordre large)`
    
    $P \subset E \wedge m \in E$

    $m$ majorant de $P$ si et seulement si:

    $\forall x \in P; (x < m) \vee (x == m)$


##### Exemple

- 4 est le majorant de l'ensemble $\{x \in \mathbb{N}; x^2 < 20\}$
- $\{ x \in \mathbb{N} ; x \in \mathbb{P}\}$ n'a pas de majorant (avec $\mathbb{P}$ l'ensemble des nombres premiers)


## Maximal

!!! info "Définition"

    $(E, <)$ `//(ordre stricte)`

    $m \in E$ est maximal si et seulement si 

    $\forall x \in E ; ¬(m < x) \vee (x==m)$

    (Un élément $m$ est le maximal d'un ensemble $E$ si et seulement si il est plus grand ou égal à tout les éléments $x$ de $E$)


##### Exemple
- $0$ est le maximal de $\mathbb{Z}⁻$

    avec $\mathbb{Z}⁻$ l'ensemble des nombres entiers négatifs.


## Minorant


## Minimal

!!! info "Définition"

    Un élément $m$ est le minimal d'un ensemble $E$ si et seulement si il est supérieur à tous les éléments de $E$ et qu'il appartient à $E$.

##### Exemple

- $0$ est le minimal de $\mathbb{N}$

!!! warning "Remarque"

    Il peut y avoir plusieurs majorants ou minorants dans un ensemble, mais un seul minimal ou maximal.

## Successeur Immédiat

!!! info "Définition"
    
    $y$ succésseur immédiat de $x$ si et seulement si

    $x \leq y \wedge y \neq x \wedge ¬(\exists z; x \leq z \wedge z \leq y)$


##### Exemple

$3$ est un succésseur immédiat de $2$ dans $\mathbb{N}$


## Décrire les relations

### Description graphique d'un ensemble
![description graphique](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.yGJTSw7Pz0BUp4yZ7RgBygHaCX%26pid%3DApi&f=1&ipt=2bd554686b6c808cd347d21d8959ab8dd940e9ea47b76ce6ac80034ea00de2e5&ipo=images)

### Description graphique d'une relation
![relation](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.FJqasN03Wg4FThmoXfXSkwHaER%26pid%3DApi&f=1&ipt=50ca39d6b5b36cee0056f18e913d00fdc4315b0bc3bb5c49c1cd637276e077f3&ipo=images)

![autre exemple](https://pads.up8.edu/uploads/e8d6319f-2afc-47e1-aea3-80b728437386.png)



## Exercice

Soit $R$ la relation définit sur $\mathbb{R}$ par :

$xRy \iff x^2 = y^2$

- Montrer que $R$ est une relation d'équivalence.

??? success "Réponse"

    $R$ est :
    
    1. **Réflexive** : $\forall x \in \mathbb{R}, x^2 = x^2$ donc $xRx$
    2. **Symétrique** : $xRy \iff x^2 = y^2 \iff y^2 = x^2$ donc $yRx$
    3. **Transive** :

        $xRy \wedge yRx \iff x^2 = y^2 \wedge y^2 = z^2 \iff x^2 = y^2 = z^2$ donc $xRz$