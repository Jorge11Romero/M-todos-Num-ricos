Ejercicio 3: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/b1add599-0ccf-40f5-a883-335b661f4a4e)

Resultado por 150 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/bf107a6d-d8ee-44f3-a390-34e37fa3785f)

Resultado por código en Python para 150 tramos:


    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 1
    b = 15
    tramos = 150
    
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

Respuesta por código para 150 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/95780191-b33b-4d7a-a977-8d181c2776da)
