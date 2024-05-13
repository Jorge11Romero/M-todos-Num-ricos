
El método del trapecio es un método de integración numérica que aproxima el valor de una integral definida dividiendo el área bajo la curva en trapezoides y sumando las áreas de estos trapezoides. Aquí tienes un algoritmo básico para implementar el método del trapecio:

Para integrar la función  en el intervalo [1,3]

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/5cd41645-2d53-45e0-8fc9-73e1060f8365)

Tramos = 4

La base de los trapecios (xi-xi+1), si esta base tiene valores equidistantes se sustituye por la variable h.

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/43e621bc-0eb2-40d0-b0a0-0a09ef1e9e93)

Para cada tramo, el área de un trapecio es:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/d5a1a4ea-c8a1-4e33-b97d-77274b4db8b3)

Por lo que cada trapecio en cada subintervalo tendrá un área de:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/ebda2098-8115-4a66-865b-900cb51ca08e)

El integral de todo el intervalo es la suma de todos los trapecios.

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/7a0f1bc3-fc42-43ba-8f3c-252a332af75c)

Si se quiere tomar el factor común entre las sumas de áreas de cada tramo, también se tiene la forma de la ecuación con un h equidistante entre cada tramo del intervalo.

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/4b9ae48f-1a75-4a62-93a9-d968eb749aa5)

Interpretando la fórmula,  el integral es la suma de:

- Una vez la función evaluada en cada extremo.
- Más dos veces cada valor de la función evaluada en los puntos intermedios.
- El resultado de la suma se multiplica por h/2.
  
En caso que los puntos no sean equidistantes la simplificación NO procede, y se sumaran las áreas de los trapecios de cada tramo.

Teniendo como resultado:

![image](https://github.com/Jorge11Romero/M-todos-Num-ricos/assets/147437900/3007ceea-12b1-4c88-a91d-ca0f35678deb)
