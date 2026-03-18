# Logique booléenne

## Assertions

!!! info "Définition"
    Une **assertion** est une affirmation contenant une valeur de vérité (vraie ou fausse).

##### Exemple

- 2 est un nombre pair. (assertion vraie)
- $\pi$ est un nombre entier. (assertion fausse)

___

## Propositions

!!! info "Définition"
    Une **proposition** est composée d'assertions reliées par des connecteurs logiques.

___

## Opérations logiques

Soit $A$ et $B$ deux assertions.

### Négation ($\neg$)

!!! info "Définition"
    La **négation** designe le complémentaire.

##### Exemple

- $A = 0$
- $\neg A = 1$

### Disjonction ($\vee$)

!!! info "Définition"

    Une disjonction est un "ou" logique.

    Il suffit qu'une assertion soit vraie pour que la proposition soit vraie.

##### Exemple

- $A =$ "$2+2 =4$" (vrai)
- $B =$ "$5 \times 2 =23$" (faux)
- $A \vee B$ est vrai


### Conjonction ($\wedge$)

!!! info "Définition"

    Une conjonction est un "ET" logique.

    Il faut que les deux assertions soient vraies en même temps pour que la proposition soit vraie.

##### Exemple

- $A =$ "$2+2 =4$" (vrai)
- $B =$ "$5 \times 2 =23$" (faux)
- $A \wedge B$ est faux

### Implication ($\Rightarrow$)

!!! info "Définition"
    Une implication de $A$ à $B$ se note $A \Rightarrow B$ et se traduit par "si $A$, alors $B$"
    
    La seule manière pour qu'une implication soit fausse est le cas où $A$ est vrai et $B$ est faux.

    Sinon elle est vraie par défaut.

##### Exemple

- $A =$ "$2+2 =4$" (vrai)
- $B =$ "$5 \times 2 =23$" (faux)
- $A \Rightarrow B$ est faux


### Equivalence ($\iff$)

!!! info "Définition"
    $A$ et $B$ sont équivalents si on remplace $A$ par $B$ dans la table de vérité, les résultats ne changent pas et inversement.

##### Exemple

- $A \Rightarrow B \iff \neg A \vee B$

    car ils ont les mêmes tables de vérités.

### Ou exclusif ($\oplus$)

!!! info "Définition"

    Un "ou exclusif" est une disjonction ("ou") mais qui renvoie faux lorsque les deux assertions sont vraies.

##### Exemple

- $A =$ "$2+2 =4$" (vrai)
- $B =$ "$5 \times 2 =10$" (vrai)
- $A \oplus B$ est faux

___

## Propriétés

- $\neg(\neg A)=A$
- $\neg(A \vee B) = \neg A \wedge \neg B$
- $\neg(A \wedge B) = \neg A \vee \neg B$
- $\neg(A \Rightarrow B) = A \wedge \neg B$

___

## Démonstrations

!!! info "Méthode"
    Pour démontrer une égalité, on développe chaque membres de l'égalité (droite et gauche) et si on parvient au même résultat, l'égalité est vérifié.

1. Démontrer que $\neg(A \cap B) = \neg A \cup \neg B$


    ??? success "Réponse"

        **Partie droite** :

        $\neg A \cup \neg B = \{x : \neg(x \in A) \vee \neg(x \in B)\}$

        **Partie gauche** : 

        $A \cap B = \{x : (x \in A) \wedge (x \in B)\}$

        $\neg(A \cap B) =\{x : \neg((x \in A) \wedge (x \in B))\}$

        *D'après la loi de Morgan,*

        $\neg(A \cap B) = \{x : \neg(x \in A) \vee \neg(x \in B)\}$

2. Démontrer que $\neg(A \cup B) = \neg A \cap \neg B$

    ??? success "Réponse"

        **Partie droite** :

        $\neg A \cap \neg B = \{x : \neg(x \in A) \wedge \neg(x \in B)\}$

        **Partie gauche** : 

        $A \cup B = \{x : (x \in A) \vee (x \in B)\}$

        $\neg(A \cup B) =\{x : \neg((x \in A) \vee (x \in B))\}$

        *D'après la loi de Morgan,*

        $\neg(A \cup B) = \{x : \neg(x \in A) \wedge \neg(x \in B)\}$

3. Démontrer que $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$

    ??? success "Correction"

        **Partie gauche** :

        $A \cap (B \cup C) = \{x; (x \in A) \wedge ((x \in B) \vee (x \in C))\}$

        $A \cap (B \cup C) = \{x; ((x \in A) \wedge (x \in B)) \vee ((x \in A) \wedge (x \in C))\}$ *en appliquant la distributivité.*

        **Partie droite** : 

        $(A \cap B) \cup (A \cap C) = \{x; ((x \in A) \wedge (x \in B)) \vee ((x \in A) \wedge (x \in C))\}$

4. Démontrer que $A \cup (B\cap C) = (A \cup B) \cap (A \cup C)$

    ??? success "Correction"

        **Partie gauche** : 

        $A \cup (B \cap C) = \{x; (x \in A) \vee ((x \in C) \wedge (x \in B)) \}$

        $A \cup (B\cap C) = \{x; ((x \in A) \vee (x \in B)) \wedge ((x \in A) \vee (x \in C))\}$ *en appliquant la distributivité.*

        **Partie droite** : 

        $(A \cup B) \cap (A \cup C) = \{x; ((x \in A) \vee (x \in B)) \wedge ((x \in A) \vee (x \in C))\}$