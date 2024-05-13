Ejercicio 4: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/30059a79-c26f-497a-a162-1fa2fb6f0929)

Resultado para 200 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/c3e040b6-2c10-4dde-a984-ba6dda63680d)

Resultado por código en Python para 200 tramos:


    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 5
    b = 30
    tramos = 200
    
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

Respuesta por código para 200 tramos:

 ![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/5c4ab247-baf3-46ee-9490-5e28893bcd2a)
