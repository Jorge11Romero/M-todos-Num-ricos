Ejercicio 2: Resuelve el siguiente problema:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/bd54619c-16dc-4971-8843-9da59f9360c5)


Resultado por diez tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/da18a0ba-af78-4b31-a572-4ac1e3e77149)


Resultado por código en Python por 10 tramos:

    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 5
    b = 7
    tramos = 10
    
    h = (b-a)/tramos
    xi = a
    area = 0
    for i in range(0,tramos,2):
        deltaA = (h/3)*(fx(xi)+4*fx(xi+h)+fx(xi+2*h))
        area = area + deltaA
        xi = xi + 2*h
    
    print('tramos:', tramos)
    print('Integral: ', area)
    
    # Redondear la variable area a tres decimales
    area = round(area, 3)
    print ('Integral limitada: ', area)

Respuesta por código por 10 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/1ecfca16-cf01-42c9-8cce-4fab0aa0ffd8)

