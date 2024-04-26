Ejercicio 4: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/962d7afc-daaa-4d59-bdee-17f4c797f623)


Resultado para 200 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/dfac6172-6788-4f54-bfba-af6915fc1597)


Resultado por código en Python para 200 tramos:

    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 5
    b = 30
    tramos = 200
    
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


Respuesta por código para 200 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/bb7d5b60-56e6-4043-afe1-3892c18f03fb)
