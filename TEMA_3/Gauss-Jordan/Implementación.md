

    import java.util.Scanner;
    import java.util.Scanner;
    
    public class Metodo_GaussJordan {
        private double[][] matriz;
        private double[] vector;
        private int n;

    public Metodo_GaussJordan(int n) {
        this.n = n;
        matriz = new double[n][n];
        vector = new double[n];
    }

    public void ingresarMatrizYVector() {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Ingrese los coeficientes de la matriz:");

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print("Ingrese el coeficiente para la fila " + (i + 1) + ", columna " + (j + 1) + ": ");
                matriz[i][j] = scanner.nextDouble();
            }
        }

        System.out.println("Ingrese el vector de resultados:");

        for (int i = 0; i < n; i++) {
            System.out.print("Ingrese el valor para la fila " + (i + 1) + ": ");
            vector[i] = scanner.nextDouble();
        }

        scanner.close();
    }

    public void resolver() {
        // Método de Gauss-Jordan
        for (int i = 0; i < n; i++) {
            // Encontrar la fila con el elemento más grande en la columna actual
            int maxRow = i;
            for (int k = i + 1; k < n; k++) {
                if (Math.abs(matriz[k][i]) > Math.abs(matriz[maxRow][i])) {
                    maxRow = k;
                }
            }
            
            // Intercambiar filas si es necesario
            if (maxRow != i) {
                double[] temp = matriz[i];
                matriz[i] = matriz[maxRow];
                matriz[maxRow] = temp;

                double tempB = vector[i];
                vector[i] = vector[maxRow];
                vector[maxRow] = tempB;
            }

            // Hacer la fila actual  coeficiente líder igual a 1
            double leadingCoefficient = matriz[i][i];
            for (int j = i; j < n; j++) {
                matriz[i][j] /= leadingCoefficient;
            }
            vector[i] /= leadingCoefficient;

            // Hacer cero todos los demás elementos en la columna actual
            for (int k = 0; k < n; k++) {
                if (k != i) {
                    double factor = matriz[k][i];
                    for (int j = i; j < n; j++) {
                        matriz[k][j] -= factor * matriz[i][j];
                    }
                    vector[k] -= factor * vector[i];
                }
            }
        }
    }

    public void imprimirSolucion() {
        System.out.println("La solución del sistema de ecuaciones es:");
        for (int i = 0; i < n; i++) {
            System.out.println("x" + (i + 1) + " = " + vector[i]);
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Ingrese el tamaño de la matriz y el vector: ");
        int n = scanner.nextInt();

        Metodo_GaussJordan solucionador = new Metodo_GaussJordan(n);
        solucionador.ingresarMatrizYVector();
        solucionador.resolver();
        solucionador.imprimirSolucion();

        scanner.close();
    }
    }
