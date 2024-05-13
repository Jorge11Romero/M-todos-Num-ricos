Ejercicio 1: Resuelve el siguiente problema

        import numpy as np
        
        def quadratic_interpolation(x_values, y_values):
            """
            Realiza interpolación cuadrática para encontrar el polinomio de segundo grado que pasa a través de tres puntos dados.
            
            Argumentos:
            x_values -- Lista de valores x conocidos.
            y_values -- Lista de valores y conocidos correspondientes a los valores x.
            
            Retorna:
            coeffs -- Coeficientes del polinomio cuadrático (a, b, c) en la forma ax^2 + bx + c.
            """
            if len(x_values) != 3 or len(y_values) != 3:
                raise ValueError("Se requieren exactamente tres puntos para la interpolación cuadrática.")
        
            A = np.vstack([x_values**2, x_values, np.ones(3)]).T
            coeffs = np.linalg.solve(A, y_values)
            return coeffs
        
        # Ejemplo de uso:
        x_values = np.array([0, 1, 2])
        y_values = np.array([1, 3, 5])
        coeffs = quadratic_interpolation(x_values, y_values)
        print("Los coeficientes del polinomio cuadrático son:", coeffs)

Resultado por código:


