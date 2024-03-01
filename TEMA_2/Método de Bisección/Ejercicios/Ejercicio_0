# Algoritmo de Bisección

from os import error
import numpy as np

# INGRESO
fx = lambda x: x**3 + 4*x**2 - 10 
xI = 1
xS = 2
error = .005

intervalo = xS-xI

fxI = fx(xI)
fxS = fx(xS)
i = 1
while (intervalo>error):
    xr = (xI+xS)/2
    fxr = fx(xr)
   
    i = i + 1
                 
    cambia = np.sign(fxI)*np.sign(fxr)
    if (cambia<0):
        xS = xr
        fxS = fxr
    else:
        xI=xr
        fxI = fxr
    intervalo = xS-xI
xr = (xI+xS)/2
fxr = fx(xr)


raiz = xr


np.set_printoptions(precision = 4)


print("La raiz es: ",raiz)

#Quiero establecer a cuatro dígitos
print()
print ("La raiz en cuatro numeros despues del punto: ", "{0:.4f}".format(raiz))
