# ORGANIZACION DE COMPUTADORAS

## Representacion de información en Sistema de Cómputo

Para operar, las computadoras utilizacn señales eléctricas.

Si bien las señales electricas pueden adoptar infinitos valores, desde los comienzos de la computación se observó que era mas fácil operar con ellas si se asumía que podían tomar solo DOS valores discretos:
1. Alto = 1
2. Bajo = 0

De esta manera se cambia el enfoque de análisis. Pasando de un problema eléctrico a un problema matemático.

Esta única señal, alto o bajo, es la variable binaria, la minima unidad de informacion que puede tomar esos dos valores posibles conocida como **BIT**

### Tipos de datos:

Las computadoras manejan 2 tipos básicos de datos (binarios):

- Numéricos
  - Enteros (con/sin signo)
  - Reales (con signo)
  - decimales codificados en binario(BCD)
- Alfanuméricos (caracteres)
  - Alfabéticos
  - Simbolos

## Representacion de números enteros:

- Sin signo: Numeros positivos
  - Binario sin signo (BSS)
- Con signo: numeros positivos y negativos
  - Módulo y signo (Binario con signo / BCS)
  - Complemento a uno (Ca1) - Complemento a la base reducida
  - Complemento a dos (ca2) - Complemento a la base
  - Exceso
____
### Binario sin signo(BSS):
    
Son combinaciones de 1 y 0 que tienen las siguiente caracteristicas:

- Todos los numeros se consideran positivos (incluyendo el 0)
- Se asigna una combinación de bits diferente por cada representación (por cada valor de la variable)
- La cantidad de combinaciones distintas depende de la cantidad de bits empleados en la representacion(2^n)
- La cantidad de combinaciones debe abarcar el rango del número a representar
- La asignacion se ordena correlativamente en forma acendente a partir de 0

La cantidad de representaciones distintas depende del numero de bits:
- Si se usa n bits, se pueden representar 2^n numeros distintos
- El rango de un numero en BSS es, por lo tanto:
- 0 -> (2^n - 1)

____

### Binario con signo (BCS):

- El bit mas significativo representa únicamente el signo
- Los n-1 bits restantes representan el valor absoluto 
- Un 0 significa positivo, un 1 significa negativo
- Rango de la magnitud: 0 -> 2^(n-1) - 1
- Rango del numero en BCS: -(2^(n-1) - 1) -> +(2^(n-1) - 1)

Ej:
1. +32 = 0010 0000
2. -32 = 1010 0000

Propiedades:
- El primer bit solo indica el signo
- Los positivos empiezan con 0
- Los negativos empiezan con 1
- Hay 2 representaciones del cero
- El intervalo es simétrico
- Dado que el 0 está duplicado, hay en total 2^n -1 numeros distintos.

_____

**Complementos:**
"Se define el complemento de un numero A a un numero N (con A menor que N) como la cantidad que le falta a A para llegar a N.

Complemento a N de A = N - A

### Complemento a 1 (Ca1):

Se define la representacion en CA1 de la siguiente manera:
- Los numeros positivos se representan igual que en BSS y BCS.
- Los numeros negativos (que son complementarios de los positivos) se obtienen como Ca1 de los positivos: Es decir
  - N negativo = Ca1 de N positivo.

Donde N = 2^n - 1

Ejemplo:

    +7 = 0000 0111
    -7 = N - 7positivo
    -7 = N - 0000 0111

    # Como N = 2^n -1, N =  2^8 -1

      -7 = 1111 1111 - 0000 0111
    > -7 = 1111 1000 <

**Notar que el numero negativo expresado en Ca1, es igual al numero positivo con los bits invertidos**


Propiedades: 
-   Los positivos comienzan con 0
-   Los negativos comienzan con 1
-   Los complementarios tienen bits invertidos
-   Hay 2 representaciones del 0
-   Rango de representacion en Ca1: -(2^(n-1) -1) --> +(2^(n-1) -1)


Para saber qué numero decimal representa un numero dado en Ca1: Ej_ 1110 0000
1. Invierto los bits: 0001 1111
2. Leo en BSS : 31
3. Agrego el menos entendiendo que era un numero negativo: -31

____

### Complemento a 2 (Ca2)
