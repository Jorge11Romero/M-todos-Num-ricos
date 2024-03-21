
El Método de Gauss-Seidel consiste en hacer iteraciones, a partir de un vector inicial, para encontrar los valores de las incógnitas hasta llegar a una tolerancia deseada, la diferencia radica en que cada vez que se desee encontrar un nuevo valor de una xi, además de usar los valores anteriores de las x, también utiliza valores actuales de las x encontradas antes (desde x0 hasta xi-1). La ecuación es la siguiente:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/bd2c2c89-e472-4add-8b1e-31aa85303c94)

El método de Gauss-Seidel surgio como una modificación del método de Jacobi que acelera la convergencia de éste.

El método de Gauss-Seidel recorta sustancialmente el número de iteraciones a realizar para obtener una cierta precisión en la solución. Evidentemente los criterios de convergencia son similares a los de Jacobi.

Este criterio no solo se aplica a las ecuaciones lineales que se resuelven con el método de Gauss-Seidel sino también para el método iterativo del punto fijo y el método de jacobi. Por tanto, al aplicar este criterio sobre las ecuaciones de Gauss-Seidel y evaluando con respecto a cada una de las incógnitas, obtenemos la expresión siguiente:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/781f0c0e-0af5-4bd9-98be-61a278403169)

El valor absoluto de las pendientes en la ecuación, deben ser menor que la unidad para asegurar la convergencia.
