Ejercicio 3: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/1d964c96-e05a-484d-ae64-cba0df7174d9)


Resultado por 150 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/1679cbda-f428-4504-a6ff-b7d933482350)


Resultado por código en Python para 150 tramos:

    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 1
    b = 15
    tramos = 150
    
    h = (b-a)/tramos
    xi = a
    suma = fx(xi)
    for i in range(0,tramos-1,1):
        xi = xi + h
        suma = suma + 2*fx(xi)
    suma = suma + fx(b)
    area = h*(suma/2)
    
    print ('Tramos: ', tramos)
    print ('Integral: ', area)
    
    # Redondear la variable area a tres decimales
    area = round(area, 3)
    print ('Integral limitada: ', area)

Respuesta por código para 150 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/48e5a321-1502-4a77-a674-b1d93bb94d6a)

