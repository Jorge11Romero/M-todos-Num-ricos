Ejercicio 1: Resuleve la siguiente ecuación

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/5e7c688b-de43-4554-a4bf-b1272722a61c)


Resultado:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/a52a125b-b3a7-44bd-86f8-16b3c6b3eee2)


Resueltado por código en JAVA:

    import java.util.Arrays;
    import java.util.Scanner;
    
    public class Gauss_Seidel {
  
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Pedir al usuario el tamaño del sistema de ecuaciones
        System.out.print("Ingrese el número de ecuaciones: ");
        int n = scanner.nextInt();

        // Crear matrices para almacenar los coeficientes y los términos independientes
        double[][] coeficientes = new double[n][n];
        double[] b = new double[n];

        // Pedir al usuario los coeficientes y términos independientes
        System.out.println("Ingrese los coeficientes de las ecuaciones:");
        for (int i = 0; i < n; i++) {
            System.out.printf("Ecuación %d:\n", i + 1);
            for (int j = 0; j < n; j++) {
                System.out.printf("Coeficiente %d: ", j + 1);
                coeficientes[i][j] = scanner.nextDouble();
            }
            System.out.print("Término independiente: ");
            b[i] = scanner.nextDouble();
        }

        // Pedir al usuario el porcentaje de error aceptado
        System.out.print("Ingrese el porcentaje de error aceptado: ");
        double error = scanner.nextDouble();

        // Llamar al método GaussSeidel para calcular los resultados
        double[] resultados = gaussSeidel(coeficientes, b, error);

        // Imprimir los resultados
        System.out.println("Resultados:");
        for (int i = 0; i < n; i++) {
            System.out.printf("x%d = %.4f\n", i + 1, resultados[i]);
        }

        scanner.close();
    }

    // Método para el cálculo de los resultados mediante el método de Gauss-Seidel
    public static double[] gaussSeidel(double[][] coeficientes, double[] b, double error) {
        int n = b.length;
        double[] resultados = new double[n];
        double[] nuevosResultados = new double[n];
        double[] errores = new double[n];
        double maxError;

        // Inicializar los resultados
        for (int i = 0; i < n; i++) {
            resultados[i] = 0; // Suponer todos los resultados iniciales como 0
        }

        // Iterar hasta que se alcance el error deseado
        do {
            // Calcular los nuevos resultados
            for (int i = 0; i < n; i++) {
                double sum = 0;
                for (int j = 0; j < n; j++) {
                    if (j != i) {
                        sum += coeficientes[i][j] * resultados[j];
                    }
                }
                nuevosResultados[i] = (b[i] - sum) / coeficientes[i][i];
            }

            // Calcular el error de cada resultado
            maxError = 0;
            for (int i = 0; i < n; i++) {
                errores[i] = Math.abs((nuevosResultados[i] - resultados[i]) / nuevosResultados[i]);
                if (errores[i] > maxError) {
                    maxError = errores[i];
                }
            }

            // Actualizar los resultados con los nuevos resultados
            System.arraycopy(nuevosResultados, 0, resultados, 0, n);

        } while (maxError > error);

        return resultados;
    }
    }


Respuesta por código:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/ea410bbf-3e96-44e1-873d-8fa0ae765f1d)
