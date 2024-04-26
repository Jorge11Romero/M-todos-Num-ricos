Código en Python:

           import sympy as sp
        
        # Definir la variable simbólica
        x = sp.symbols('x')
        
        # Entrada de la función como texto
        f_input = input('f(x)= ')
        # Convertir la entrada de texto a una expresión de Sympy
        g = sp.lambdify(x, sp.sympify(f_input), 'numpy')
        
        # Entrada de los límites de integración
        a = float(input('Limite inferior: '))
        b = float(input('Limite superior: '))
        
        # Cálculo del intervalo h
        h = (b - a) / 3
        
        # Cálculo de la integral usando la regla de Simpson 3/8
        I = (3 * h / 8) * (g(a) + 3 * g((2 * a + b) / 3) + 3 * g((a + 2 * b) / 3) + g(b))
        
        # Mostrar el resultado
        print('Valor Aproximado de la Integral:', I)
