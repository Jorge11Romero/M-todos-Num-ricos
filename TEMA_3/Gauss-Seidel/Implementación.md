
    
    import java.util.Arrays;
    import java.util.Scanner;
    
    public class GaussSeidel {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Pedir al usuario las dimensiones de la matriz
        System.out.println("Ingrese el número de filas de la matriz:");
        int filas = scanner.nextInt();
        System.out.println("Ingrese el número de columnas de la matriz:");
        int columnas = scanner.nextInt();

        // Declarar las matrices y el vector
        double[][] A = new double[filas][columnas];
        double[][] B = new double[filas][1];

        // Pedir al usuario los valores de la matriz A
        System.out.println("Ingrese los elementos de la matriz A:");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print("A[" + i + "][" + j + "]: ");
                A[i][j] = scanner.nextDouble();
            }
        }

        // Pedir al usuario los valores del vector B
        System.out.println("Ingrese los elementos del vector B:");
        for (int i = 0; i < filas; i++) {
            System.out.print("B[" + i + "]: ");
            B[i][0] = scanner.nextDouble();
        }

        // Realizar el algoritmo de Gauss-Seidel
        double[] x = new double[filas]; // Vector inicial
        double[] xPrev = new double[filas]; // Vector previo
        Arrays.fill(xPrev, 0); // Inicializar el vector previo con ceros

        double error = 1e-6; // Error permitido
        int iteracionesMax = 5000; // Máximo número de iteraciones

        int iteraciones = 0;
        while (iteraciones < iteracionesMax) {
            for (int i = 0; i < filas; i++) {
                double sum = 0;
                for (int j = 0; j < columnas; j++) {
                    if (j != i) {
                        sum += A[i][j] * x[j];
                    }
                }
                x[i] = (B[i][0] - sum) / A[i][i];
            }

            // Verificar convergencia
            boolean converge = true;
            for (int i = 0; i < filas; i++) {
                if (Math.abs(x[i] - xPrev[i]) > error) {
                    converge = false;
                    break;
                }
            }

            if (converge) {
                break;
            }

            // Actualizar el vector previo
            System.arraycopy(x, 0, xPrev, 0, filas);
            iteraciones++;
        }

        // Imprimir resultados
        if (iteraciones == iteracionesMax) {
            System.out.println("El método no converge después de " + iteracionesMax + " iteraciones.");
        } else {
            System.out.println("El método converge después de " + iteraciones + " iteraciones.");
            System.out.println("Solución:");
            System.out.println(Arrays.toString(x));
        }

        scanner.close(); // Cerrar el scanner
    }
    }

          



