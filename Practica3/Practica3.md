#Practica 3
**José Manuel Barranco**
Primero, instalamos nginx:
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica3/3.1.png)
Añadimos la dirección del repositorio a nuestra lista de fuentes:
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica3/3.2.png)
Configuramos el archivo default.conf:
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica3/3.3.png)
Utilizamos el comando curl para comprobar que el balanceador funciona correctamente:
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica3/3.4.png)
Configuramos el archivo de configuración del haproxy:
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica3/3.5.png)
Lanzamos haproxy:
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica3/3.6.png)
Comprobamos con curl que funciona el balanceador correctamente:
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica3/3.7.png)

