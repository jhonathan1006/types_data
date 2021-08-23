Tipos de datos y su estructura
================

``` r
#Institución: Unidades Tecnológicas de Santander
# Programa: Ingenieria en Topografía
# Autor: "Aponte Saravia Jhonathan"
```

## Descripción del contexto

A continuación, se presenta aplicaciones básicas de exploración de datos
en lenguaje R, donde se comparten los códigos y las instrucciones para
realizar operaciones elementales con datos de tipo caracter, valores
numéricos, aplicaciones de logica, con valores enteros. El propósito de
la guía, está dirigido a interesados que tengan afinidad a los programas
de ingeniería, cuyo interés es la aproximación con el programa R
Pakchage para desarrollar las habilidades en el uso, así mismo, es de
circulación nacional sin enfoque diferencial.

``` r
#El programa R tiene 6 tipos de datos basicos.
#Caracter: "m", "n"

#Numérico: (comprende a los valores entreros y decimales)
#Interger: (un tipo de datos enteros)
#Lógico: (en datos vectoriales puede estar asociado a FALSO Y VERDADERO)
#Complejo: se refiera a la lectura de numeros complejos y reales y imaginarios. 

#R el programa provee varias funciones para examinar los carateres de los objetos. 

# class() - que tipo de objeto es?
# typeof() - cual es el tipo de datos del objeto
# length() - describe la longitud de los objetos 
# attributes() - Que tiene en los metadatos.
```

### Algunas aplicaciones de tipo caracter.

Caracter: para distinguir el valor del caracter debe estar entre
comillas.

``` r
x <- c("Argentina", "Brasil", "Bolivia","Colombia ","Chile", "Perú")
class(x)
```

    ## [1] "character"

``` r
typeof(x)
```

    ## [1] "character"

``` r
attributes(x)
```

    ## NULL

``` r
length(x)
```

    ## [1] 6

``` r
nchar(x)
```

    ## [1] 9 6 7 9 5 4

``` r
n <- "Jhonathan"
ap <- "Aponte"
am <- "Saravia"

nc<- cbind(n,ap,am)
nc
```

    ##      n           ap       am       
    ## [1,] "Jhonathan" "Aponte" "Saravia"

``` r
paste("mi nombre completo es:",n,ap,am)
```

    ## [1] "mi nombre completo es: Jhonathan Aponte Saravia"

``` r
# Otra forma de conectar los datos es utlizando la funcion colapso (_,.- etc)

paste(x,collapse = ",")
```

    ## [1] "Argentina,Brasil,Bolivia,Colombia ,Chile,Perú"

``` r
# Para subtraer los datos por ejemplo: 

substr("Hola Perú",1, 4)
```

    ## [1] "Hola"

``` r
substr("Hola Perú",5, 9)
```

    ## [1] " Perú"

``` r
# Para reemplazar la cadena de caracteres

gsub("u", "ú", "Hola Peru")
```

    ## [1] "Hola Perú"

``` r
# Para encontrar elementos que ajusten a un patrón 
d <- c("az20", "az21", "az22", "ba30", "ba31", "ab32")
i <- grep("ba", d)
i
```

    ## [1] 4 5

``` r
# Para obervarlo
d[i]
```

    ## [1] "ba30" "ba31"

``` r
# de otra forma

grep("ba", d, value=TRUE)
```

    ## [1] "ba30" "ba31"

``` r
# Elementos que incluyen un caracter por ejemplo "2"
grep("2",d)
```

    ## [1] 1 2 3 6

``` r
# Elementos que terminan en 2
grep("2$",d)
```

    ## [1] 3 6

``` r
grep("2$",d, value = TRUE)
```

    ## [1] "az22" "ab32"

``` r
# Elementos que comienza en a 
grep("^a", d, value = TRUE)
```

    ## [1] "az20" "az21" "az22" "ab32"

``` r
# Cambiar  miniscula a mayuscula 
z <- letters
z
```

    ##  [1] "a" "b" "c" "d" "e" "f" "g" "h" "i" "j" "k" "l" "m" "n" "o" "p" "q" "r" "s"
    ## [20] "t" "u" "v" "w" "x" "y" "z"

``` r
up <- toupper(z)
up
```

    ##  [1] "A" "B" "C" "D" "E" "F" "G" "H" "I" "J" "K" "L" "M" "N" "O" "P" "Q" "R" "S"
    ## [20] "T" "U" "V" "W" "X" "Y" "Z"

``` r
dow<- tolower(up)
dow
```

    ##  [1] "a" "b" "c" "d" "e" "f" "g" "h" "i" "j" "k" "l" "m" "n" "o" "p" "q" "r" "s"
    ## [20] "t" "u" "v" "w" "x" "y" "z"

### Aplicaciones con vectores númericos

Formas de asignación

``` r
a <- c(10.4, 5.6, 3.1, 6.4, 21.7)
a
```

    ## [1] 10.4  5.6  3.1  6.4 21.7

``` r
c(20.1, 7.6, 6.1, 10.4, 30.7) -> b
b
```

    ## [1] 20.1  7.6  6.1 10.4 30.7

``` r
k <- 1/a
k
```

    ## [1] 0.09615385 0.17857143 0.32258065 0.15625000 0.04608295

``` r
k1 <- a*b
k1
```

    ## [1] 209.04  42.56  18.91  66.56 666.19

``` r
k2 <- a^b
k2
```

    ## [1] 2.769301e+20 4.855445e+05 9.938168e+02 2.422544e+08 1.069828e+41

``` r
# cálculos aritmeticos

v <- 2*a + b + 1
v
```

    ## [1] 41.9 19.8 13.3 24.2 75.1

``` r
v1<- cbind(a,b)
v1
```

    ##         a    b
    ## [1,] 10.4 20.1
    ## [2,]  5.6  7.6
    ## [3,]  3.1  6.1
    ## [4,]  6.4 10.4
    ## [5,] 21.7 30.7

``` r
media<- sum(v1)/length(v1)
media
```

    ## [1] 12.21

``` r
mean(v1)
```

    ## [1] 12.21

``` r
#extraer los valores que nos interesa

c(min(v1), max(v1)); length(v1)
```

    ## [1]  3.1 30.7

    ## [1] 10

``` r
# calculo donde integre todo los datos
var1<- sum((v1-mean(v1))^2)/(length(v1)-1)
var1
```

    ## [1] 79.97433

``` r
# considerando cada columna
var(v1)
```

    ##        a       b
    ## a 53.853  74.051
    ## b 74.051 106.907

``` r
summary(v1)
```

    ##        a               b        
    ##  Min.   : 3.10   Min.   : 6.10  
    ##  1st Qu.: 5.60   1st Qu.: 7.60  
    ##  Median : 6.40   Median :10.40  
    ##  Mean   : 9.44   Mean   :14.98  
    ##  3rd Qu.:10.40   3rd Qu.:20.10  
    ##  Max.   :21.70   Max.   :30.70

Generación de sucesiones

``` r
s <- 1:20
s
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20

``` r
p <- pi:10

z<- 15:1
my_seq <- seq(5, 10, length=30)

s4 <- seq(length=51, from=-5, by=.2)
s4
```

    ##  [1] -5.0 -4.8 -4.6 -4.4 -4.2 -4.0 -3.8 -3.6 -3.4 -3.2 -3.0 -2.8 -2.6 -2.4 -2.2
    ## [16] -2.0 -1.8 -1.6 -1.4 -1.2 -1.0 -0.8 -0.6 -0.4 -0.2  0.0  0.2  0.4  0.6  0.8
    ## [31]  1.0  1.2  1.4  1.6  1.8  2.0  2.2  2.4  2.6  2.8  3.0  3.2  3.4  3.6  3.8
    ## [46]  4.0  4.2  4.4  4.6  4.8  5.0

``` r
# Valores aleatorios 
nn<- sample(1:100,10, replace=TRUE)


## Agregando datos a valores faltantes 
m <- c(12, NA, 18, 5, NA, 2,12, 8, 15, 18)
m
```

    ##  [1] 12 NA 18  5 NA  2 12  8 15 18

``` r
datalimp = na.omit(m)
datalimp
```

    ## [1] 12 18  5  2 12  8 15 18
    ## attr(,"na.action")
    ## [1] 2 5
    ## attr(,"class")
    ## [1] "omit"

``` r
# reemplazando los datos numericos

mediadata =mean(datalimp)
m[is.na(m)]= mediadata
m
```

    ##  [1] 12.00 11.25 18.00  5.00 11.25  2.00 12.00  8.00 15.00 18.00

Algunas aplicaciones con operadores lógicos

``` r
nombre <- c("Miguel", "Maria", "Maritza", "Juan", "Maira", "pedro", "patricia")
varon <- c(1,0,0,1,0,1,0)
nota <- c(13,17,9,14,6,10,15)

data <- data.frame(nombre, varon, nota)
head(data)
```

    ##    nombre varon nota
    ## 1  Miguel     1   13
    ## 2   Maria     0   17
    ## 3 Maritza     0    9
    ## 4    Juan     1   14
    ## 5   Maira     0    6
    ## 6   pedro     1   10

``` r
data$varon==1
```

    ## [1]  TRUE FALSE FALSE  TRUE FALSE  TRUE FALSE

``` r
data$varon
```

    ## [1] 1 0 0 1 0 1 0

``` r
data$nombre <- nombre== "Maira"
head(data)
```

    ##   nombre varon nota
    ## 1  FALSE     1   13
    ## 2  FALSE     0   17
    ## 3  FALSE     0    9
    ## 4  FALSE     1   14
    ## 5   TRUE     0    6
    ## 6  FALSE     1   10

``` r
data$nota <- !nota<15
data$nota
```

    ## [1] FALSE  TRUE FALSE FALSE FALSE FALSE  TRUE

``` r
head(data)
```

    ##   nombre varon  nota
    ## 1  FALSE     1 FALSE
    ## 2  FALSE     0  TRUE
    ## 3  FALSE     0 FALSE
    ## 4  FALSE     1 FALSE
    ## 5   TRUE     0 FALSE
    ## 6  FALSE     1 FALSE

``` r
data$nota <- !nota>=13
data$nota
```

    ## [1] FALSE FALSE  TRUE FALSE  TRUE  TRUE FALSE

``` r
data$nombre <- nota <13 | varon==1
data$nombre
```

    ## [1]  TRUE FALSE  TRUE  TRUE  TRUE  TRUE FALSE
