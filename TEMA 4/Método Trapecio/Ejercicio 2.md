Ejercicio 2: Resuelve el siguiente problema:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/9b83a155-f97b-4e4b-adf5-c457ecf9a9e4)

Resultado por diez tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/a3060531-a873-4014-8be8-e6565226272a)


Resultado por código en Python por 10 tramos:

    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 5
    b = 7
    tramos = 10
    
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


Respuesta por código por 1o tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/a49dc0e0-5075-4942-88f0-b145c0615198)


