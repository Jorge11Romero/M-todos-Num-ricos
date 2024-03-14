Ejemplo: Resolución de circuitos eléctricos

Imagina que estás trabajando en el diseño y análisis de un circuito eléctrico complejo. 
Para calcular las corrientes y tensiones en cada componente del circuito, necesitas resolver un sistema de ecuaciones lineales 
que represente las leyes fundamentales de la electricidad (ley de Ohm, leyes de Kirchhoff, etc.).

Supongamos que tienes el siguiente sistema de ecuaciones lineales para un circuito eléctrico con tres componentes:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/333d7651-00df-49d3-9277-b95caeed5398)


Dando como resultado:


![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/d4f5f88d-79d0-4c66-b5c9-2b799c22d133)



Programa en ejecución:

    public static void main(String[] args) {
        
         // PASO 1: Definir nuestra matriz o nuestro vector
        double[][] A = {{3,-2,4},
                        {-2,6,-3},
                        {4,-3,7}};
        
        double[][] B = {{10},
                        {-5},
                        {12}};
        
        // Copiamos las matrices originales y las hacemos de tipo flotante
        double[][] A_copy = new double[A.length][A[0].length];
        double[][] B_copy = new double[B.length][B[0].length];
        
        for (int i = 0; i < A.length; i++) {
            A_copy[i] = Arrays.copyOf(A[i], A[i].length);
            B_copy[i] = Arrays.copyOf(B[i], B[i].length);
        }
        
        // Se calcula el tamaño del vector
        int N = B.length;
        
        // Se recorre la matriz
        for (int i = 0; i < N; i++) {
            // Normalización
            double pivot = A_copy[i][i];
            System.out.println("Mi pivote es: " + pivot);
            for (int j = 0; j < A_copy[i].length; j++) {
                A_copy[i][j] /= pivot;
            }
            B_copy[i][0] /= pivot;
            System.out.println("\nSe divide el renglon por el pivote:");
            printMatrix(A_copy);
            System.out.println("\nSe divide el vector por el pivote:");
            printMatrix(B_copy);
            
            // Eliminación hacia adelante
            for (int j = i + 1; j < N; j++) {
                double factor = A_copy[j][i];
                System.out.println("\nConvertir en cero la matriz");
                System.out.println(factor);
                for (int k = 0; k < A_copy[j].length; k++) {
                    A_copy[j][k] -= factor * A_copy[i][k];
                }
                B_copy[j][0] -= factor * B_copy[i][0];
                printMatrix(A_copy);
                printMatrix(B_copy);
            }
        }
        
        // Sustitución hacia atrás
        double[] x = new double[N];
        for (int i = N - 1; i >= 0; i--) {
            System.out.println("\nIteracion " + i);
            System.out.println("B_copy[" + i + "]: " + B_copy[i][0]);
            System.out.println("A_copy[" + i + ", " + (i+1) + ":]: " + Arrays.toString(Arrays.copyOfRange(A_copy[i], i+1, A_copy[i].length)));
            System.out.println("x[" + (i+1) + ":]: " + Arrays.toString(Arrays.copyOfRange(x, i+1, x.length)));
            x[i] = B_copy[i][0];
            for (int j = i + 1; j < N; j++) {
                x[i] -= A_copy[i][j] * x[j];
            }
            System.out.println("x[" + i + "]: " + x[i]);
        }
        
        // Resultados
        System.out.println("\nMatriz A triangularizada:");
        printMatrix(A_copy);
        System.out.println("\nVector B triangularizado:");
        printMatrix(B_copy);
        System.out.println("\nSolucion:");
        System.out.println(Arrays.toString(x));
    }
    
    public static void printMatrix(double[][] matrix) {
        for (double[] row : matrix) {
            System.out.println(Arrays.toString(row));
        }
        
    }
    
}


Resultado con el programa: 


![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/3c64ceb5-0171-47cb-ab88-c0d47b8c732f)


La eliminación Gaussiana es un método poderoso y ampliamente utilizado para resolver sistemas de ecuaciones lineales. 
Sin embargo, como cualquier técnica, tiene sus posibilidades y limitaciones:

Posibilidades:

- Versatilidad: La eliminación Gaussiana es aplicable a una amplia gama de sistemas de ecuaciones lineales, 
incluyendo aquellos con un número arbitrario de ecuaciones e incógnitas.

- Eficiencia: Para sistemas con un número moderado de ecuaciones e incógnitas, la eliminación Gaussiana puede ser bastante eficiente en términos de tiempo de cálculo. 
Es especialmente eficaz cuando se combina con pivoteo parcial para evitar errores de redondeo y divisiones por cero.

- Precisión: Cuando se implementa correctamente, la eliminación Gaussiana produce soluciones precisas y exactas para sistemas de ecuaciones lineales.

- Aplicaciones prácticas: Es ampliamente utilizada en campos como ingeniería, ciencias naturales, economía y computación, donde resolver sistemas de ecuaciones lineales es una tarea común.


Limitaciones:

- Costo computacional: La eliminación Gaussiana puede volverse computacionalmente costosa para sistemas grandes o altamente dispersos debido al número significativo de operaciones aritméticas 
necesarias para reducir la matriz a su forma escalonada.

- Sensibilidad a errores de redondeo: En sistemas mal condicionados o cercanos a la singularidad, la eliminación Gaussiana puede ser sensible a los errores de redondeo, 
lo que puede resultar en soluciones inexactas o no representativas.

- Requisitos de almacenamiento de memoria: Para sistemas grandes, la eliminación Gaussiana puede requerir una cantidad considerable de memoria para almacenar la matriz del sistema y 
las operaciones intermedias, lo que puede ser prohibitivo en entornos con recursos limitados.

- No es adecuada para todos los sistemas: Hay casos en los que la eliminación Gaussiana puede no ser la mejor opción para resolver sistemas de ecuaciones lineales, especialmente 
cuando el sistema tiene una estructura especial que puede explotarse con métodos alternativos, como la factorización LU o métodos iterativos.
