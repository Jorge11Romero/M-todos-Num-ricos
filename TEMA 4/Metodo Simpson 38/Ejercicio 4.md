Ejercicio 3: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/e244cc3d-e6b0-40a0-94a0-c450724fb8d5)

Resultado:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/e9865a60-c561-4ff6-aa6f-9257bcab388c)


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

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/b0efe8cf-aef5-45b4-80ea-5c5eaf0e31b6)


