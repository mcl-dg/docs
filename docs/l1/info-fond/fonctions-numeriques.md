### Appliqué aux fonctions

extension à $\mathbb{R}$

* $f : \mathbb{R} \rightarrow \mathbb{R}$
* $x \rightarrow f(x)$
* $f(x) = x^2 - 5x + 6$
* $f'(x) = 2x -5$
* $f''(x) = 2$


![](https://pads.up8.edu/uploads/cc69d845-1c82-4244-a579-e1d2b515aa00.png)

##### Exemple

Si on connait $f(0)$, on calcule le terme suivant avec la différence.

$diff(f(0.01),f(0)) \iff croissance \iff vitesse \iff \frac{f(x + \epsilon) - f(x)}{\epsilon}$

"vitesse" $\lim\limits_{\epsilon \rightarrow 0} \frac{f(x + \epsilon) - f(x)}{\epsilon} = f'(x)$

"accélération" $\lim\limits_{\epsilon \rightarrow 0} \frac{f'(x + \epsilon) - f'(x)}{\epsilon} = f''(x)$

### Formules de dérivées

!!! danger ""

    * $f(x) = x^n$
    * $f'(x) = nx^{n-1}$
    * $g(x) = \frac{1}{x}$
    * $g'(x) = -x^{-2}$
    * $h(x) = a + b$
    * $h'(x) = a' + b'$
    * $m(x) = a * b$
    * $m'(x) = a'b + b'a$
    * $n(x) =\frac{a}{b}$
    * $n'(x) = \frac{a'b - b'a}{b^2}$
    * $l(x) = (g \circ f)$
    * $l'(x) =f'(g) \times g'$


## Exemple 1 : Formule 1

$v = 50 m/s$

$50m * 3600 = 5*36 km = 180 km/h$

$1000m \rightarrow 20s$



||0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|**v**|50|52|54|56|58|60|62|64|66|68|70|72|70|68|66|64|62||||
|**Distance parcourue**|0|50|102|156|212|270|330|392|456|522|590|660|732|802|870|946|1010|


- continuer à accélérer. $\times$
- moins accélérer. $\times$
- ralentir : $2m/s/s$ $\times$
- freiner : $4m/s/s$ Aïe
- freiner à fond : $8m/s/s$

## TP

* Ecrire un programme qui permet d'afficher, seconde après seconde, vitesse et distance parcourue en fonction d'une accélération donnée.

* Utiliser ces fonctions pour déterminer la décélération la meilleure.

!!! info ""

    Pour ce faire, nous allons utiliser les structures suivantes :

    ```c
    typedef struct instant{
        int tps;
        float acc;
        float speed;
        float dist;
    }instant_t;

    typedef struct vect{
        int nbval;
        instant_t* vec;
    }vect_t
    ```

### Utilité de la dérivée

* $diff(i) = u_{i+1} -u_i$
* $\int u \Rightarrow \displaystyle\sum^n_{i=0} u_i$
* $(u v)' = u'v + uv'$
utile pour connaitre la vitesse
* $f(x) = 0$
* $f'(x_1) =0$
* $f'(x_2) = 0$

## Exemple 2

- $TM$ = Temperature moyenne. $\simeq 15$°C
- $TM(i)$  : pour l'année $i$. $\simeq 288$K
- $PPM$ (parties par million) et $GES$ (gaz à effet de serre)
- $78$% Azote
- $21$% Oxygène
- $TM$ dépend de $PPM$
#### Petite parenthèse
- fontes des glaces  = $\Rightarrow +43$K
- micro organique océanique $\Rightarrow +40$K
> "Everything's gonna be alright" (from *No woman no cry)*

##### Exemple
Exprimer $TM(i) / TM(i+1)$ en fonction de $PPM(i)$

- $PPM(1880) = 280$
- $TM(1880) = 280$ K

donc

- $TM(i) = \alpha*PPM(i) + Cte$

$\alpha <1$

$\alpha \simeq 10$%

$TM(i) = Cte + \frac{10 \times ppm(i)}{100}$

$288 = Cte + \frac{10 \times 280}{100}$

$Cte = 288 - \frac{10 \times 280}{100}$

$Cte = 260$

- $PPM(i+1) =PPM(i) + 3.5$

$TM(i+1) = TM(i)$

* $TM(i) = 260 + \frac{PPM(i)}{10}$

* $TM(i+1) = 260 + \frac{PPM(i+1)}{10}$

$=260 + \frac{PPM(i) + 3.5}{10}$

$= 260 + \frac{PPM(i)}{10} + 0.35$

$= TM(i) + 0.35$

* Dérivée sur $\mathbb{R}$ : $TM'(x) = \frac{PPM'(x)}{10}$

#### FORTRAN
- $i\:j\:k\:l\:m\:n \rightarrow INT$
- $x\:y\:z\:h\:t \rightarrow FLOAT$


## Fonction / dérivée / dérivée seconde

- $f \rightarrow f' \rightarrow f''$

$distance \leftarrow vitesse \leftarrow$

### Exemple : "Problème à 3 corps"

- Pas de solution analytique mais mathématique
- trois objet physique qui gravite tout autour qui ont une masse et une vitesse
- $f(m_1,v_1,m_2...)$
- algo de Runge Kutta 4
- $temps = \alpha R^{3/2}$

- $Jupiter \simeq 40' \simeq \frac{2}{3} h \simeq \frac{2}{3 \times 24} j \frac{1}{36} j \simeq \frac{1}{10000} an \frac{1}{36 \times 365} an$

- $\sqrt{5000} = 10 \sqrt{50} \simeq 70 \Rightarrow 70 \times 5000 \times 80 \;ans \Rightarrow 28000000 \;ans$


## Dessiner une courbe à partir d'une fonction
- Utiliser un 'plotteur' (outil permettant d'interpréter une fonction en graphe en latex)

## Fonction exponentielle et logarithmique

### Propriétés

!!! warning "Formules de dérivées"
    - $f(x) = exp(x) = e^x$
    - $f'(x) = e^x$
    - $e^{log(x)} = log \; e^x = x$
    - $log(a \times b) = log(a) + log(b)$
    - $log(a^n) = n \; log(a)$
    - $ln_10(10^x) = x$
    - $ln_2(2^x) = x$
    - $cos' = -sin$
    - $sin' = cos$

!!! info "Graphe $exp(x)$ et $log(x)$"
    ![](https://pads.up8.edu/uploads/af1cdb73-0570-406f-b72d-7ea7edd53626.png)



## Exercice sur la dérivation


!!! warning ""
    - $f_1(x) = 4x^3 - 5x^2 + x - 1$

??? success "Correction"
    $f_1'(x) = 12x^2 - 10 x + 1$

___
!!! warning ""
    - $f_2(x) = (x^2 + 1)(x^3 -2x)$

??? success "Correction"
    $f_2(x) = u \times v$ avec

    - $u =x^2 + 1$
    - $u' =2x$
    - $v = x^3 -2x$
    - $v' =3x^2 -2$
        
    Donc

    $f_2'(x) = u'v + uv' = 2x(x^3 -2x) + (x^2 + 1)(3x^2 -2)$

    $= 2x^4 -4x^2 + 3x^4-2x^2 + 3x^2 -2$

    $= 5x^4 -3x^2 -2$
___
!!! warning ""
    - $f_3(x) = \frac{2x^2 -3}{x^2 + 7}$

??? success "Correction"
    $f_3(x) = \frac{u}{v}$ avec

    - $u=2x^2 -3$
    - $u'=4x$
    - $v=x^2 + 7$
    - $v'=2x$

    Donc

    $f_3'(x) = \frac{u'v - uv'}{v^2}=\frac{4x(x^2 +7) -(2x^2 -3) \times 2x}{(x^2+7)}$
___

!!! warning ""
    - $f_4(x) = 5x^3 - \frac{1}{x} + 3 \sqrt{x}$

??? success "Correction"
    $f_4(x) =u +v+w$ avec

    - $u= 5x^3$
    - $u'=15x^2$
    - $v=\frac{1}{x}$
    - $v'=-\frac{1}{x^2}$
    - $w=r \times s$ avec
    - $r=3; r'=0;s=\sqrt{x};s'=\frac{1}{2 \sqrt{x}}$
    - donc $w'=r's +rs' = 0 \times \sqrt{x} + 3 \times \frac{1}{2 \sqrt{x}} = \frac{3}{2 \sqrt{x}}$

    Donc

    $f_4'(x) =u'+v'+w' =15x^2 - \frac{1}{x^2} + \frac{3}{2 \sqrt{x}}$

___

!!! warning ""
    - $f_5(x) = \frac{1}{x+x^2}$

??? success "Correction"
    $f_5(x)=\frac{1}{u}$ avec

    - $u=x+x^2$

    Donc

    $f_5'(x)=- \frac{1}{u^2} = - \frac{1}{(x+x^2)^2}$