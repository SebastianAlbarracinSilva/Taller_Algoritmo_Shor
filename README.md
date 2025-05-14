# Taller_Algoritmo_Shor

# Sebastian Albarracin Silva

# Factorización con el algoritmo de Shor

### 1. potencias módulo N

Se calcula una lista con los valores de \( a^x \mod N \) para \( x = 0 \) hasta \( N - 1 \), utilizando la propiedad de que \( a^x = a \cdot a^{x-1} \). Esto se hace de forma iterativa y se almacena el resultado de cada operación.




### 2. período

El período es el menor número entero \( r > 0 \) tal que \( a^r \mod N = 1 \). Se recorre la lista de potencias calculada y se encuentra la primera repetición del valor 1 (después de \( x = 0 \)).

Este valor \( r \) es crucial para intentar la factorización.




### 3. máximo común divisor (MCD)

Se utiliza el algoritmo de Euclides para encontrar el máximo común divisor entre dos números. Esta operación permite obtener factores de \( N \) una vez se haya encontrado el período.




## Proceso de factorización

### Paso 1: valores iniciales

Se elige un número compuesto \( N \) a factorizar, y una base \( a \) tal que \( 1 < a < N \) y \( \gcd(a, N) = 1 \). En este caso, se utiliza \( N = 247 \) y \( a = 2 \).




### Paso 2: potencias de a módulo N

Se genera una lista de valores de \( a^x \mod N \). Esta lista sirve como base para encontrar el período de la función.




### Paso 3: período de la función

Se identifica el menor valor de \( x > 0 \) para el cual \( a^x \mod N = 1 \). Este valor es el período \( r \). Si no se encuentra, el intento de factorización falla.




### Paso 4: validez del período

Para que el método funcione, el período \( r \) debe ser **par**. Si \( r \) es impar, no se puede continuar con la factorización de esta forma y se debe intentar con otro valor de \( a \).




### Paso 5: Calcular \( x = a^{r/2} \mod N \)

Si el período es válido, se calcula \( x = a^{r/2} \mod N \). Este valor se utiliza para encontrar los posibles factores de \( N \).




### Paso 6: Obtener los factores

Se calcula el máximo común divisor de \( x + 1 \) y \( N \), y también de \( x - 1 \) y \( N \). Si alguno de estos divisores es diferente de 1 y de \( N \), entonces se ha encontrado un factor no trivial.




### Paso 7: gráfica

Finalmente, se grafica la función \( f(x) = a^x \mod N \) para visualizar su comportamiento periódico. El gráfico permite observar la repetición de valores, lo que ayuda a identificar el período visualmente.



