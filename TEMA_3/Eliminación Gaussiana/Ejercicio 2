Ejercicio 2: Resuleve la siguiente ecuación
   
  |  2x -  y +  3z  = 5
--|  2x + 2y +  3z  = 7
  | -2x + 3y        = -3

Resultado: 

x = 5/2
y = 2/3
z = 2/9 


Resueltado por código en JAVA:

import java.util.Arrays;


public class EliminacionGaussiana {

    public static void main(String[] args) {
        
         // PASO 1: Definir nuestra matriz o nuestro vector
        double[][] A = {{2,-1,3},
                        {2,2,3},
                        {-2,3,0}};
        
        double[][] B = {{5},
                        {7},
                        {-3}};
        
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

Respuesta por código:

Solucion:
[2.5, 0.6666666666666666, 0.22222222222222224]
