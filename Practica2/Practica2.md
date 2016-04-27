#Practica 2
**José Manuel Barranco**

Primero, comprobamos que las máquinas virtuales puedan comunicarse. Realizamos un ping a cada una de las IP. 
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.1.png?raw=true)
Sincronizamos la carpeta /var/www de la máquina 2 con la 1.
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.2.png?raw=true)

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.3.png?raw=true)
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.4.png?raw=true)
Añadimos la key en el archivo id_dsa.pub para poder acceder con ssh de una máquina a otra sin necesidad de introducir la contraseña.
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.5.png?raw=true)
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.6.png?raw=true)
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.7.png?raw=true)
Creamos una tarea crontab, para que cada minuto se lance una tarea para que sincronice cada minuto la carpeta /var/www.
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/Practica2/2.8.png?raw=true)

