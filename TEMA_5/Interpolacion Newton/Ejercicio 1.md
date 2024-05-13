Ejercicio 1: Resuelve el siguiente problema

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/ddaccdbe-ea7a-4e88-a986-f74aaa8ad1b6)

Resultado para 4 tramos: 

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/443bcfb3-c42c-4ee4-a03a-43449a40a132)

Resultado para 128 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/eff44f53-9daf-4645-b205-b132813eea2b)



Resultado por código en Python para 4 tramos:

    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 1
    b = 3
    tramos = 4
    
    h = (b-a)/tramos
    xi = a
    suma = fx(xi)
    for i in range(0,tramos-1,1):
        xi = xi + h
        suma = suma + 2*fx(xi)
    suma = suma + fx(b)
    area = h*(suma/2)
    
    # Redondear la variable area a tres decimales
    
    
    print ('Tramos: ', tramos)
    print ('Integral: ', area)
    
    area = round(area, 3)
    print ('Integral limitada: ', area)

Respuesta por código para 4 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/1e432ce6-6e42-425c-9fa1-e7a35752a864)


---------------------------------------------------------------------

Resultado por código en Python para 4 tramos:

    import numpy as np
    import matplotlib.pyplot as plt
    
    fx = lambda x: np.sqrt(x)*np.sin(x)
    
    a = 1
    b = 3
    tramos = 128
    
    h = (b-a)/tramos
    xi = a
    suma = fx(xi)
    for i in range(0,tramos-1,1):
        xi = xi + h
        suma = suma + 2*fx(xi)
    suma = suma + fx(b)
    area = h*(suma/2)
    
    # Redondear la variable area a tres decimales
    
    
    print ('Tramos: ', tramos)
    print ('Integral: ', area)
    
    area = round(area, 3)
    print ('Integral limitada: ', area)

Respuesta por código para 128 tramos:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/fd35bc0d-9563-44d6-9f4d-f60d3af78843)


