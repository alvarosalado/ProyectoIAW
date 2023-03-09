Álvaro Salado Palomares	2ºASIR	IAW

![](img/Aspose.Words.2badb1fc-d7aa-42d8-9136-9c18d4a4c086.001.jpeg)

![](img/Aspose.Words.2badb1fc-d7aa-42d8-9136-9c18d4a4c086.002.jpeg)

ES Gran Capitán
Departamento de Informática

Ciclo Formativo de Grado Superior de
Administración de Sistemas Informáticos

**Implantación de Aplicaciones Web**

**Álvaro Salado Palomares– 2ºASIR**

**Proyecto: Proyecto Final (Tienda Álvaro Salado)**

**Curso 2022/2023**

Índice de contenido

1.- Introducción	

2.- Objetivos y requisitos del proyecto	

3.- Estudio previo	

3.1.- Estado actual	

3.2.- Estudio de soluciones existentes	

4.- Plan de trabajo	

5.- Diseño	

5.1.- Diseño general	

5.2.- Diseño detallado

6.- Implantación	

7.- Recursos	

7.1.- Herramientas hardware	

7.2.- Herramientas software	

7.3.- Personal	

7.4.- Presupuesto	

8.- Conclusiones	

8.1.- Grado de consecución de objetivos	

8.2.- Problemas encontrados

8.3.- Futuras mejoras	

9.- Referencias / bibliografía	

10.- Anexos	


# **1.- Introducción**
En este proyecto vamos a crear una página web de una tienda de ropa, con accesos de usuarios y acceso de administradores, se podrán hacer pedidos y listar el stock.
# **2.- Objetivos y requisitos del proyecto**
Clothing Corp. acaba de abrir una pequeña tienda de ropa. El propietario quiere utilizar los servicios en la nube para alojar el sitio web, realizar un seguimiento de los clientes y las compras y detectar patrones de datos para que su estrategia de marketing y producción sea eficiente.

Para cumplir el requisito de este proyecto, vamos a crear una página web dinámica donde los usuarios/clientes podrán registrar sus datos personales para asi poder comprar la ropa de esta tienda.

La tienda estará adminsitrada por un usuario admin que será quien añada productos.
# **3.- Estudio previo**
Para que los clientes puedan hacer sus pedidos rellenaran un formulario de registro que lo almacenaremos en nuestra base de datos y posteriormente ya podrán iniciar sesión.
## ***3.1.- Estado actual***
Para realizar este proyecto, hemos creado una página web dinámica para realizar diferentes formularios y poder registrar tanto los datos de clientes, como los datos de compras de sus clientes. Asi ya los clientes podrán hacer sus compras como gusten y nosotros podremos recoger sus datos para asi hacer estrategias de marketing.
## ***3.2.- Estudio de soluciones existentes***
Realizaremos un despliegue en AWS con diferentes servicios.

\- Crearemos una instancia EC2 donde alojaremos nuestra página web y los distintos formularios creados para registrar los datos y compras de los clientes.

\- Crearemos una instancia RDS que es donde se alojará nuestra base de datos la cual almacenará los datos registrados de los formularios que rellenan los usuarios

\- Crearemos una VPC de manera que nuestros sitios tendrán la posibilidad de conectarse desde diferentes zonas.
# **4.- Plan de trabajo**
El plan de trabajo seria montar una VPC propia en Amazon en la que meteremos a nuestra maquinas EC2 y RDS.

Una vez tengamos esto hecho, montaríamos  la base de datos y la ec2 que será quien alojará la página web, crearemos un grupo de seguridad para la ec2 y otro para la RDS para poder tener mayor seguridad.

En el grupo de seguridad de la ec2 solo se tendrá acceso mediante HTTP y podrá acceder todo el mundo.

En el grupo de seguridad de la RDS solo se podrá conectar el grupo de seguridad de la ec2.

# **5.- Diseño**
## ***5.1.- Diseño general***
Nuestro diseño es una página web de una tienda que venderá productos a los clientes, los clientes se pueden registrar y posteriormente iniciar sesión. El usuario admin puede entrar como admin a la página y subir productos para que estos productos puedan ser vendidos. Cuando todo esto este hecho securizamos las maquinas.
## ***5.2.- Diseño detallado***
Hemos creado nuestra propia VPC que alojara a las instancias ec2 y RDS para que asi tengamos conexión desde distintas zonas.

En la siguiente captura podemos ver como hemos creado ,as subredes y nos proporciona un mapa de las redes que tendrán salida a internet (publicas) y las redes que no podrán salir a internet (privadas). Cada subred tiene una tabla de enrutamiento dependiendo de si son publicas o privadas

![](img/Aspose.Words.2badb1fc-d7aa-42d8-9136-9c18d4a4c086.003.png)

En nuestra instancia RDS añadiremos las subredes.

![](img/Aspose.Words.2badb1fc-d7aa-42d8-9136-9c18d4a4c086.004.png)

# **6.- Implantación**
La implementación que hay que hacer para la solución de este  proyecto  seria crear un escenario de AWS en el que alojaremos un servidor web y un servidor de base de datos para que nuestra pagina web vaya correctamente. Durante este proceso debemos tener nuestro escenario securizado para no tener vulnerabilidades.
# **7.- Recursos**
## ***7.1.- Herramientas hardware***
Instancia EC2 con la siguiente configuración:

\- S.O à Ubuntu 22.04

\- Tipo de instancia: t2.micro

\- 1 CPU

\- 8 GB de almacenamiento 
## ***7.2.- Herramientas software***
Instancia EC2 con la siguiente configuración software:

\- Servicio Apache.

\- Servicio MySQL.

\- Servicio PHP.

\- Grupo de seguridad.

Instancia RDS con la siguiente configuración software:

\- Servicio MySQL.

\- Grupo de seguridad.
## ***7.3.- Personal***
Como estamos empezando y somos una empresa pequeña, solo nos bastará con un usuario admin que será quien administre toda la página, si nos va bien aumentaremos el personal.

## ***7.4.- Presupuesto***
Este será el presupuesto por utilizar una instancia EC2.

![](img/Aspose.Words.2badb1fc-d7aa-42d8-9136-9c18d4a4c086.005.png)

Este es el presupuesto previsto que tenemos para este mes.

![](img/Aspose.Words.2badb1fc-d7aa-42d8-9136-9c18d4a4c086.006.png)

# **8.- Conclusiones**
## ***8.1.- Grado de consecución de objetivos***
\- Creación de instancias y configuracionà Hecho

\- Creación página webà Hecho

\- Creación base de datos à Hecho

\- Securización à Hecho
## ***8.2.- Problemas encontrados***
El mayor problema que he encontrado en el proyecto son las inserciones de datos desde la pagina web a la base de datos que hemos asociado previamente. La solución que he podido encontrar es la inserción de datos mediante un código PHP de inserción y de conexión con la base de datos, a raíz de este código he podido hacer todo.
## ***8.3.- Futuras mejoras***
Como mejoras para el futuro de este proyecto seria la implementación de un cluster y de un proxy inverso con balance de carga, para que cuando la empresa vaya mejor y tengamos mas clientes la pagina web siga funcionando correctamente y y no se colapsen los servidores, lo que nos provocaría una perdida de dinero. Otra mejora que podemos hacer seria que al añadir productos podamos subir la imagen directamente y no la tengamos que subir desde el html. 
# **9.- Referencias / bibliografía**
Las referencias que he seguido han sido las siguientes:

\- [W3Schools](https://www.w3schools.com/bootstrap5/index.php)

\- [Bootstrap](https://startbootstrap.com)

\- [Moodle](https://moodle.iesgrancapitan.org/course/view.php?id=152&section=0)
# **10.- Anexos**
Por ejemplo, planos, especificaciones de los programas que se usen...

- Visual Studio Code
- CMD
- AWS
- WinSCP
- MySQL Worbench
- Google Photos


