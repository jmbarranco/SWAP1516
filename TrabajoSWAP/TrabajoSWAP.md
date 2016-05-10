#Bases de Datos Distribuidas
**José Manuel Barranco**

**Qué es una Base de Datos Distribuida (BDD) y un Sistema de Gestión de Bases de Datos (SGBD):** 

Una base de datos distribuida (BDD) es un conjunto de múltiples bases de datos lógicamente relacionadas las cuales se encuentran distribuidas en diferentes espacios lógicos y geográficos e interconectados por una red de comunicaciones. Dichas BDD tienen la capacidad de realizar procesamiento autónomo, esto permite realizar operaciones locales o distribuidas.


 
**Ventajas bases de datos distribuidas y/o replicadas:** 

Una BDD garantiza que cada centro (en caso de usar cada uno el 80% de los datos de su propio centro), si no falla su propio ordenador, puede trabajar al menos al 80%.

**Problemas bases de datos distribuidas y/o replicadas:** 

El problema es gestionar de manera unificada una base de datos de la que hay almacenada distintas partes en varios centros de procesos de datos.

**¿Cuándo son preferibles las bases de datos distribuidas?**

	-Si todos los procesos son locales: Bases de datos independientes

	-Si una instalación hace muchos más accesos que las demás: Bases de datos centralizadas.

	-En cualquier otro caso: Bases de datos distribuidas

**Características de una base de datos distribuida:**

	-Cada localidad puede ejecutar aplicaciones locales

	-Cada localidad participa, al menos, en la ejecución de una aplicación global que requiere acceso a datos de varias localidades.

	-Los programas de aplicación no necesitan saber en qué localidad están los datos para acceder a ellos.

**Configuraciones de red más comunes:**

	-*Totalmente conectada*
	
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/Totalmente-conectada.png)	

	-*Parcialmente conectada*

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/Parcialmente-conectada.png)

	-*Estrella*

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/Estrella.png)

	-*Anillo*

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/Anillo.png)

	-*Estructura de árbol*

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/Estructura-de-arbol.png)

**Distribución del problema**

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/Localidades.png)
	
**Tipos de fragmentación:**

	-*Fragmentación horizontal* (Subconjunto de tuplas): Se define con el operador de selección y se reconstruye con el operador de union.

	
	Localidad1 = Madrid = {Castilla-León, Castilla-La Mancha, Aragón, Madrid, La Rioja} 
	Localidad2 = Barcelona = {Cataluña, Baleares, País Valenciano, Murcia} 
	Localidad3 = La Coruña = {Galicia, Asturias, Cantabria, País Vasco, Navarra} 
	Localidad4 = Sevilla = {Andalucía, Extremadura, Canarias, Ceuta, Melilla}

		
	2^4 = 16 casos a evaluar. 
	Y1= P1^P2^P3P4; FALSO 
	Y2= P1^¬P2^¬P3^¬P4; MADRID VERDADERO 
	Y3= ¬P1^P2^¬P3^¬P4;BARCELONAVERDADERO 
	Y4= ¬P1^¬P2^P3^¬P4;LA CORUÑA VERDADERO 
	Y5= P1^¬P2^¬P3^P4;SEVILLAVERDADERO 
	Y6= ¬P1^¬P2^¬P3^¬P4;MADRIDVERDADERO

	Cliente1= SLY2 Cliente; → Madrid 
	Cliente2= SLY3 Cliente; → Barcelona 
	Cliente3= SLY4 Cliente; → La Coruña 
	Cliente4= SLY5 Cliente; → Sevilla 
	Cliente5= SLY6 Cliente; → Madrid 
		
	Sucursal1= SLY2 Sucursal; → Madrid 
	Sucursal2= SLY3 Sucursal; → Barcelona 
	Sucursal3= SLY4 Sucursal; → La Coruña 
	Sucursal4= SLY5 Sucursal; → Sevilla 
	Sucursal5= SLY6 Sucursal; → Madrid 
	
	Vino1= SLY2 Vino; → Madrid 
	Vino2= SLY3 Vino; → Barcelona 
	Vino3= SLY4 Vino; → La Coruña 
	Vino4= SLY5 Vino; → Sevilla 
	Vino5= SLY6 Vino; → Madrid 
		
	Empleado1=SLy2 Empleado;→ Madrid 
	Empleado2=SLy3 Empleado;→ Barcelona 
	Empleado3=SLy4 Empleado;→ La Coruña 
	Empleado4=SLy5 Empleado;→ Sevilla 
	Empleado5=SLy6 Empleado;→ Madrid
	
	En el caso de SLy6, como no pertenece a ninguna localidad, asignamos una localidad opcional o asignamos una de las anteriores (normalmente, la que tenga mas afluencia)	

	-*Fragmentación vertical* (Subconjunto de atributos)

	-*Fragmentación mixta* (Aplicar fragmentación vertical a una fragmentación horizontal o viceversa)

**Ejemplo disparadores**

Se ejecutan cuando sucede algún evento sobre las tablas a las que se encuentra asociado. Los eventos que hacen que se ejecute un disparador son las operaciones de inserción (INSERT), borrado (DELETE) o actualización (UPDATE), ya que modifican los datos de una tabla.

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/disparadores/Pedido-ciente-sucursal.png)
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/disparadores/salario-menor.png)

**Ejemplo procedimientos**

La ventaja de un procedimiento almacenado es que al ser ejecutado, es ejecutado directamente en el motor de bases de datos, el cual usualmente corre en un servidor separado. Usos típicos para procedimientos almacenados incluyen la validación de datos siendo integrados a la estructura de base de datos.

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/procedimientos/alta-cliente.png)
![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/procedimientos/trasladar-empleado.png)

**Ejemplo índices**

El índice de una base de datos es una estructura de datos que mejora la velocidad de las operaciones, por medio de identificador único de cada fila de una tabla, permitiendo un rápido acceso a los registros de una tabla en una base de datos.

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/indices/cliente.png)

**Ejemplo vistas**

Una vista es una consulta que se presenta como una tabla (virtual) a partir de un conjunto de tablas en una base de datos relacional.

![texto alternativo](https://github.com/jmbarranco/SWAP1516/blob/master/Imagenes/TrabajoSWAP/vistas/sucursal.png)
