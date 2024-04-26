Código en Python:

    import numpy as np
    import matplotlib.pyplot as plt
    
    def integrasimpson38_fi(xi,fi,tolera = 1e-10):
        
        n = len(xi)
        i = 0
        suma = 0
        while not(i>=(n-3)):
            h  = xi[i+1]-xi[i]
            h1 = (xi[i+2]-xi[i+1])
            h2 = (xi[i+3]-xi[i+2])
            dh = abs(h-h1)+abs(h-h2)
            if dh<tolera:
                unS38 = fi[i]+3*fi[i+1]+3*fi[i+2]+fi[i+3]
                unS38 = (3/8)*h*unS38
                suma = suma + unS38
            else:  
                suma = 'tramos desiguales'
            i = i + 3
        if (i+1)<n: 
            suma = 'tramos incompletos, faltan '
            suma = suma +str(n-(i+1))+' tramos'
        return(suma)
    
    xi = [1.        , 1.33333333, 1.66666667, 2.        ,
          2.33333333, 2.66666667, 3.        ]
    fi = [0.84147098, 1.12229722, 1.28506615, 1.28594075,
          1.10453193, 0.74672307, 0.24442702]
    tolera = 1e-7
    
    n = len(xi)-1
    Area = integrasimpson38_fi(xi,fi,tolera)
    
    print('tramos: ',n)
    print('Integral con Simpson 3/8: ',Area)
    if type(Area)==str:
        print('  Revisar errores')
    
    # Redondear la variable area a tres decimales
    Area = round(Area, 3)
    print ('Integral limitada: ', Area)
