El código en Python:

           def lagrange_interpolation(x_values, y_values, x):
            """
            Realiza interpolación de Lagrange para encontrar el valor y correspondiente a un valor x dado.
            
            Argumentos:
            x_values -- Lista de valores x conocidos.
            y_values -- Lista de valores y conocidos correspondientes a los valores x.
            x -- El valor de x para el cual se quiere interpolar y.
            
            Retorna:
            y -- El valor interpolado correspondiente a x.
            """
            n = len(x_values)
            if n != len(y_values):
                raise ValueError("Las listas x_values e y_values deben tener la misma longitud.")
        
            y = 0
            for i in range(n):
                term = y_values[i]
                for j in range(n):
                    if j != i:
                        term *= (x - x_values[j]) / (x_values[i] - x_values[j])
                y += term
            return y
        
        # Ejemplo de uso:
        x_values = [0, 1, 2, 3, 4]
        y_values = [1, 3, 5, 4, 2]
        x_interpolate = 2.5
        y_interpolated = lagrange_interpolation(x_values, y_values, x_interpolate)
        print(f"El valor interpolado para x = {x_interpolate} es y = {y_interpolated}")


