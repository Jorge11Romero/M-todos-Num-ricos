Ejercicio 2: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/a68acccb-b607-4b96-9f1d-a4190326dac1)

Resultado:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/8d3f9c21-062f-423f-92f3-831ae027ac31)


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

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/03c0a715-3b14-44cc-bf10-2e67050c6e66)
