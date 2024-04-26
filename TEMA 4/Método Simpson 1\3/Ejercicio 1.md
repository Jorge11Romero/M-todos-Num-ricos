Ejercicio 1: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/5f5c2ad6-5330-4ba4-96c0-27edbc5b8048)


Resultado para 4 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/8eed2f17-963a-4830-9e8c-080db9bf7f35)

Resultado por código en Python para 4 tramos:

    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 1
    b = 3
    tramos = 4
    
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

Respuesta por código para 4 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/1799b398-da6d-49ed-a5e9-0e86f5fa5c69)

