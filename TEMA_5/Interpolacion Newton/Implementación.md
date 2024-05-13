El código en Python:

            import numpy as np
    
    def divided_differences(x_values, y_values):
        """
        Calcula las diferencias divididas para la interpolación de Newton.
        
        Argumentos:
        x_values -- Lista de valores x conocidos.
        y_values -- Lista de valores y conocidos correspondientes a los valores x.
        
        Retorna:
        tabla -- Tabla de diferencias divididas.
        """
        n = len(x_values)
        # Crear una matriz vacía para almacenar las diferencias divididas
        tabla = np.zeros((n, n))
        tabla[:, 0] = y_values  # La primera columna es simplemente los valores y dados
        
        for j in range(1, n):
            for i in range(n - j):
                # Calcular la diferencia dividida para el punto (i, j)
                tabla[i, j] = (tabla[i+1, j-1] - tabla[i, j-1]) / (x_values[i+j] - x_values[i])
        
        return tabla
    
    def newton_interpolation(x_values, y_values, x):
        """
        Realiza interpolación de Newton para encontrar el valor y correspondiente a un valor x dado.
        
        Argumentos:
        x_values -- Lista de valores x conocidos.
        y_values -- Lista de valores y conocidos correspondientes a los valores x.
        x -- El valor de x para el cual se quiere interpolar y.
        
        Retorna:
        y -- El valor interpolado correspondiente a x.
        """
        tabla = divided_differences(x_values, y_values)
        n = len(x_values)
        y = tabla[0, 0]
        temp = 1
        
        for i in range(1, n):
            temp *= (x - x_values[i - 1])
            y += tabla[0, i] * temp
        
        return y
    
    # Ejemplo de uso:
    x_values = [0, 1, 2, 3]
    y_values = [1, 3, 5, 4]
    x_interpolate = 2.5
    y_interpolated = newton_interpolation(x_values, y_values, x_interpolate)
    print(f"El valor interpolado para x = {x_interpolate} es y = {y_interpolated}")


