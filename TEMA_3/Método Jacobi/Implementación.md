

    package método_jacobi;
    
    import java.util.Scanner;
    
    public class MetodoJacobi {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);

        // Solicitar el tamaño del sistema
        System.out.print("Ingrese el tamaño del sistema: ");
        int tam = sc.nextInt();

        // Validar el tamaño del sistema
        if (tam < 2) {
            System.out.println("El tamaño del sistema debe ser mayor o igual a 2.");
            return;
        }

        // Solicitar la matriz de coeficientes y el vector de resultados
        double[][] matrizCoeficientes = new double[tam][tam];
        double[] vectorResultados = new double[tam];

        System.out.println("Ingrese la matriz de coeficientes:");
        for (int i = 0; i < tam; i++) {
            for (int j = 0; j < tam; j++) {
                System.out.print("Ingrese el elemento [" + (i + 1) + "][" + (j + 1) + "]: ");
                matrizCoeficientes[i][j] = sc.nextDouble();
            }
        }

        System.out.println("Ingrese el vector de resultados:");
        for (int i = 0; i < tam; i++) {
            System.out.print("Ingrese el elemento [" + (i + 1) + "]: ");
            vectorResultados[i] = sc.nextDouble();
        }

        // Definir el vector inicial (se quedan en 0)
        double[] vectorInicial = new double[tam];
        double[] vectorAnterior = new double[tam];

        int maxIteraciones = 50;

        // Realizar iteraciones en el método de Jacobi
        for (int k = 0; k < maxIteraciones; k++) {
            System.out.print("Iteración " + (k + 1) + ": ");

            // Calcular nuevos valores de x
            double[] x = new double[tam];
            for (int i = 0; i < tam; i++) {
                double sum = 0;
                for (int j = 0; j < tam; j++) {
                    if (j != i) {
                        sum += matrizCoeficientes[i][j] * vectorInicial[j];
                    }
                }
                x[i] = (vectorResultados[i] - sum) / matrizCoeficientes[i][i];
            }

            double errorAbsoluto = calcularErrorAbsoluto(x, vectorAnterior);

            if (k > 0 && errorAbsoluto < 0.05) {
                System.out.println("Error absoluto menor al 5% en la iteración " + (k + 1) + ".");
                break; // Romper el ciclo
            }

            // Mostrar resultados de la iteración
            for (int i = 0; i < tam; i++) {
                System.out.printf("x%d = %.4f ", i + 1, x[i]);
            }
            System.out.println();

            // Actualizar el vector inicial y el vector anterior para la próxima iteración
            System.arraycopy(x, 0, vectorInicial, 0, tam);
            System.arraycopy(x, 0, vectorAnterior, 0, tam);
        }
    }

    private static double calcularErrorAbsoluto(double[] vectorActual, double[] vectorAnterior) {
        double maxError = 0;
        for (int i = 0; i < vectorActual.length; i++) {
            double error = Math.abs((vectorActual[i] - vectorAnterior[i]) / Math.abs(vectorActual[i]));
            maxError = Math.max(maxError, error);
        }
        return maxError;
      }
    }
