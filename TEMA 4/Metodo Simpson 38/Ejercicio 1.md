Ejercicio 1: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/325691ec-5cd0-4f35-8deb-c3a4e5ab5854)

Resultado:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/a429cd5e-74a5-426a-9f19-a8b80cf41601)


Resultado por código en Python:

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


Respuesta por código:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/afb97c12-b1a5-44ba-816b-ff012627f9a1)

