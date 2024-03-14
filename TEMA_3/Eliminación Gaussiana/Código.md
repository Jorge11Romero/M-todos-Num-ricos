El método de eliminación Gaussiana es una técnica fundamental en el ámbito del álgebra lineal, utilizado para resolver sistemas de ecuaciones lineales. 
Este método, también conocido como eliminación de Gauss, busca transformar un sistema de ecuaciones lineales en uno equivalente más simple, lo que permite encontrar fácilmente las soluciones.

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/1f8ea584-6fb3-41f6-9334-cb8191ee8a57)

Pasos principales:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/aa413f14-a8c5-4c4e-a066-141d01cc0062)

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/c09efb2f-f838-47c1-8124-c91481575bc0)

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/fa16db06-f336-49bc-b24e-5b1288cb7bd3)


![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/f679851b-28a6-408d-b0c0-528dcb926574)

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/fb03c1f4-8f49-4ed4-aeab-9603fae037da)

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/ab33716b-e87d-4645-81b3-78e58981de03)

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/2f1672fd-b993-4d23-b763-2e0b3609a82b)


El código en JAVA:

import java.util.Arrays;


public class EliminacionGaussiana {

    public static void main(String[] args) {
        
         // PASO 1: Definir nuestra matriz o nuestro vector
        double[][] A = {{1,2,1},
                        {1,0,1},
                        {0,1,2}};
        
        double[][] B = {{0},
                        {2},
                        {1}};
        
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

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/b14f776f-2e7f-4834-ac29-8b674b3012d1)

