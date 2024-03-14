Ejercicio 4: Resuleve la siguiente ecuación

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/8ea8f055-131c-4c7d-99a9-a1ad71bd39b6)


Resultado: 

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/c2b87f4a-dde8-493c-ab32-a646edf50b1e)


Resueltado por código en JAVA:

    public static void main(String[] args) {
        
         // PASO 1: Definir nuestra matriz o nuestro vector
        double[][] A = {{5,2,0},
                        {2,1,-1},
                        {2,3,-1}};
        
        double[][] B = {{2},
                        {0},
                        {3}};
        
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
    


Respuesta por código:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/c8e53fdc-c7f6-4b4d-8436-94fa5f170965)

