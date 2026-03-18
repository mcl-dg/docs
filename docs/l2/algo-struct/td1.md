# TD1

## Exercice 1:


### 1.
||valeur|type|
|-|-|-|
&a | 45245|int *
&b | 45244 | char *
&c | 45241 | short int *
a | 4 | int
b | 2 | char
c | 1 | short int
&a+1 | 45249 | int *
&c+2 | 45245 | short int *
&z-&c |$\frac{(45249 - 45241)}{sizeof(short \;int)} = \frac{8}{2} =4$ |entier
sizeof(c) | 2| entier
sizeof(short int) | 2| entier

### 2.

``` c
printf("%p\n",&a); //0xb0b8 + 5 = 0xb0bd
printf("%d\n",b); //2
printf("%p\n",&c); // 0xb0b9
```

## Exercice 6:

```c
int main(void){
    int a = 0;
    int T[10];
    int b = 0;
    T[10] = 1; // *T+10 = 1
    printf("%d",b); //affiche potentiellement 1
    return 0;
}
```
Solution pour vérifier une potentielle fuite de mémoire :

```bash
gcc -sanitize = address -g
```
