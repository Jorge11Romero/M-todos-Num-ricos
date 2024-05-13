Ejercicio 3: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/770fb571-fadb-4555-b9a9-6532d16ebb80)

Resultado:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/d2528a61-f99c-4e69-bc84-52ac61fb845f)

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

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/bdefe1e6-6570-4780-87e1-b25c821172be)




