# Non déterminisme, parallélisme, complexité en moyenne ou dans le pire des cas

## Algorithmes non deterministe


!!! info ""
    -	Un algorithme non deterministe ne verifie pas forcement la regle : « Pour 2 executions avec les mêmes entrées alors l’algo se déroule de la même manière »

    -	C'est-à-dire que certaines decisions sont choisies aleatoirement

    -	Transformation

        ``algoNonDeterministe(entree1,entree2,…)``

        =>

        ``algoDeterministe(entree1, entree 2, suiteValeursAleatoires)``

___

## Parallelisme (de flot d’execution)

```c
algorithme1(…){
    retour1= sousAlgorithme1(…)
    retour2 = sousAlgorithme2(…) // n’utilise pas la valeur retour1
}
```
On peut écrire :

```c
algorithme2(…){
    retour2 = sousAlgorithme2(…)
    retour1 = sousAlgorithme1(…) 
}
```
___

## Complexité en moyenne ou dans le pire des cas ?



La complexité moyenne d’un algorithme en temps (resp. en espace) est toujours meilleure que dans le pire des cas en temps (resp . en espace)

-	$(Q_n)_{n \in \mathbb{N}}$ : Nombre d’operations moyen du quicksort selon la taille du tableau.
-	$(Q’_n)_{n \in \mathbb{N}}$ : Nombre d’operations dans le pire des cas du Quicksort
-	$(F’_n)_{n \in \mathbb{N}}$ : Nombre d’operations dans le pire des cas du Tri Fusion.
-	On a $n log(n) << Q, F’ << n log(n) << n^2 << Q’ << n^2$
-	Pourtant le Quicksort est en pratique plus efficace que le Tri Fusion en moyenne.
