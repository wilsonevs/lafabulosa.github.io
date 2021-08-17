# lafabulosa.github.io

7	INSTALACIÓN DEL SISTEMA
PASO N°1: Primero que todo debemos configurar nuestro entorno de desarrollo, según las especificaciones de nuestro equipo de la siguiente manera.
PASO N°2: Antes de comenzar debemos conocer que características cuenta nuestro equipo, si nos encontramos en un sistema operativo como es Windows, 
presionamos en el teclado Windows (símbolo ventana de Microsoft) + letra E al mismo tiempo en el cual nos abrirá una ventana. Y buscamos donde dice este es 
mi equipo, le damos clic derecho y seleccionamos la opción “Propiedades”, y hay podremos ver las especificaciones de mi equipo. En nuestro caso contamos con 
Windows 10 de 64 bits.
PASO N°3: Luego debemos instalar un IDE, en este caso puede ser (JetBrain, Intellij IDEA, Atom y Visual Studio Code), pero recomendamos Visual Studio Code.
PASO N°4: Si vamos a descargar Visual Studio Code; ingresamos al siguiente link: https://code.visualstudio.com/download, donde nos brindara la posibilidad de 
escoger según nuestro sistema operativo (Windows, Linux y OS x); en nuestro caso como poseemos Windows 10 de 64 bits, damos clic a la opción User Installer 64 bit.
PASO N°5: Después debemos descargar Xampp en el link: https://www.apachefriends.org/es/download.html , donde nos brindara la posibilidad de escoger según nuestro 
sistema operativo (Windows, Linux y OS x); en nuestro caso como poseemos Windows 10, escogimos Windows 8.0.9 / PHP 8.0.9 y clic en Descargar (64 bit) que es la última versión.
PASO N°6: Una vez descargado el Visual Studio Code y Xampp, procedemos con la instalación de ambas.
PASO N°7: Una vez instalado, abriremos primero Xampp, una vez abierto el Xampp le damos clic el botón start al lado, donde dice MySQL. 
PASO N°8: Una vez inicializado nos permitirá acceder a nuestra base de datos; en el cual tenemos una forma de acceder a nuestra base de datos, y debemos darle 
clic a la letra Admin y nos abrirá una ventana en nuestro navegar con la siguiente ip: http://localhost/phpmyadmin/
PASO N°9: Vamos y buscamos la opción -> SQL y ingresamos el siguiente
comando completo: 
CREATE DATABASE emisora_web;
USE emisora_web;

CREATE TABLE IF NOT EXISTS emisora_web.db_asunto (
  id_asunto INT(11) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  nombre VARCHAR(100) NOT NULL,
  email VARCHAR(75) NOT NULL,
  telefono VARCHAR(20) NOT NULL,
  asunto VARCHAR(20) NOT NULL,
  argumento VARCHAR(500) NOT NULL
  )ENGINE = InnoDB;

CREATE TABLE IF NOT EXISTS emisora_web.db_cliente (
  id_cliente INT(11) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  foto_perfil VARCHAR(100) NOT NULL,
  username VARCHAR(100) NOT NULL,
  firstname VARCHAR(100) NOT NULL,
  lastname VARCHAR(100) NOT NULL,
  ciudad VARCHAR(75) NOT NULL,
  addre VARCHAR(75) NOT NULL,
  telefono VARCHAR(20) NOT NULL,
  email VARCHAR(100) NOT NULL,
  passw VARCHAR(255) NOT NULL,
  rol VARCHAR(255) NOT NULL,
  data_create TIMESTAMP DEFAULT CURRENT_TIMESTAMP()
  )ENGINE = InnoDB;

CREATE TABLE IF NOT EXISTS emisora_web.db_eventos (
  id_eventos INT(11) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  nombre_evento VARCHAR(75) NOT NULL,
  fecha VARCHAR(10) NOT NULL,
  hora VARCHAR(10) NOT NULL,
  patrocinador VARCHAR(75) NOT NULL,
  actividad VARCHAR(75) NOT NULL,
  lugar VARCHAR(75) NOT NULL,
  data_create TIMESTAMP DEFAULT CURRENT_TIMESTAMP()
  )ENGINE = InnoDB;

CREATE TABLE IF NOT EXISTS emisora_web.db_ganador (
  id_ganador INT(11) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  firstname VARCHAR(100) NOT NULL,
  lastname VARCHAR(100) NOT NULL,
  premio_entregado VARCHAR(100) NOT NULL,
  patrocinador VARCHAR(100) NOT NULL,
  codigo VARCHAR(25) NOT NULL,
  fecha_entrega VARCHAR(20) NOT NULL,
  data_create TIMESTAMP DEFAULT CURRENT_TIMESTAMP()
  )ENGINE = InnoDB;

CREATE TABLE IF NOT EXISTS emisora_web.db_sorteos (
  id_sorteos INT(11) NOT NULL PRIMARY KEY AUTO_INCREMENT,
  titulo VARCHAR(100) NOT NULL,
  codigo VARCHAR(25) NOT NULL,
  nombre_producto VARCHAR(100) NOT NULL,
  lugar VARCHAR(100) NOT NULL,
  fecha VARCHAR(10) NOT NULL,
  hora VARCHAR(10) NOT NULL,
  telefono VARCHAR(20) NOT NULL,
  imagen VARCHAR(100) NOT NULL,
  fecha_creacion TIMESTAMP DEFAULT CURRENT_TIMESTAMP()
  )ENGINE = InnoDB;

CREATE TABLE IF NOT EXISTS emisora_web.r_cliente_sorteos (
  id_cliente_sorteos INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  cliente_id  INT(11) NOT NULL,
  sorteos_id  INT(11) NOT NULL,
  data_create TIMESTAMP DEFAULT CURRENT_TIMESTAMP(),
  CONSTRAINT  r_cliente_id FOREIGN KEY (cliente_id) REFERENCES emisora_web.db_cliente (id_cliente) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT  r_sorteos_id FOREIGN KEY (sorteos_id) REFERENCES emisora_web.db_sorteos (id_sorteos) ON DELETE CASCADE ON UPDATE CASCADE
)ENGINE = InnoDB;
PASO N°10: Ya ingresado todo el comando completo, le damos clic donde dice “Continuar”, Una vez creada nuestra base de datos, continuamos con el proceso.
PASO N°11: Luego abriremos Visual Studio Code, damos clic en archivo -> Abrir carpeta y seleccionamos donde queremos almacenar nuestro proyecto.
PASO N°12: Presionamos en el teclado Ctrl + le letra Ñ para abrir nuestra consola.
PASO N°13: Procedemos a clonar el proyecto que se encuentra almacenado desde GitHub, en la siguiente ruta: https://github.com/wilsonevs/proyecto_final_sena.git.
PASO N°14: Luego de que todo está instalado y configurado, procedemos a clonar el proyecto que se encuentra almacenado desde GitHub, en la siguiente 
ruta: https://github.com/wilsonevs/proyecto_final_sena.git.
PASO N°15: Luego en la misma consola instalamos npm init –y y le damos enter varias veces hasta completar.
PASO N°16:  Se crear la carpeta package.json y luego en la consola ingresamos npm i bcryptjs body-parser dotenv ejs express express-session  multer MySQL 
uuid fs-extra http-errors una vez instalado ingresamos entre ultimo comando 
 npm i nodemon  -D. 
PASO N°17: Luego en el package.json dentro de “scripts” ingresamos al siguiente: 
"scripts": {
    "start": "node src/index.js",
    "dev": " nodemon src/index"
  },

PASO N°18: En el comando ingresamos lo siguiente: npm run dev.
PASO N°19: Por último, ingresamos al navegador que recomendamos anteriormente que es Google Chrome en el siguiente: http://localhost:3001/


Requerimientos funcionales y no funcionales del proyecto:
Para este hemos llegado al estudio exacto de cuáles serán los requerimientos funcionales y no funcionales de nuestro proyecto:


ACERCA DE…

EMISORA VIRTUAL LA FABULOSA, es una emisora virtual, pero a la vez es una herramienta de promoción de servicios ofrecidos por la marca Eventos y producciones El Kangry (EPK), 
aquí puede además de escuchar una variada programación musical, conocer los servicios profesionales que puede adquirir o contratar con EPK.
El aplicativo está diseñado en Css, Bootstrap, nodejs, sistema de etiquetas con ejs que trabaja sobre la sintaxis de html, MySQL con XAMPP para la gestión de base de datos, 
se utilizó también GitHub para el control de versiones.
En este manual se explica paso a paso y de forma gráfica la forma en cómo debe usarse este aplicativo web, además de todas las opciones de navegación que se encuentran 
disponibles para su uso.
Esperemos que su experiencia navegando a través de esta página sea de lo más grata y logre satisfacer completamente sus expectativas.

1.1 	Objeto

Crear una aplicación que aloja una emisora virtual cuyo propósito será entretener e informar a la audiencia de Emisora virtual la Fabulosa, sobre los servicios que 
ofrece Eventos y Producciones El Kangry dándolo a conocer de una manera agradable y fresca, tendrá una programación musical crossover, con lo cual se espera llegar 
a una audiencia de todas las edades y gustos en cuanto a la música.


1.2 	Alcance

La aplicación Emisora Virtual la Fabulosa, será el instrumento con el cual Eventos y Producciones EL Kangry logrará el objetivo de entretener, informar sobre sus 
actividades y promocionar sus servicios.

a.	Diseñar una solución de software que resuelva las necesidades de difusión, comunicación e interacción en tiempo real con sus oyentes.
b.	Implementar un sistema donde aloja datos, para lo cual es necesario crear las bases de datos con los niveles de seguridad apropiados que garanticen la protección de los datos en donde se almacenan la información de contactos, sorteos, eventos, datos de los usuarios de la aplicación.
c.	Crear una aplicación, teniendo en cuenta que en la misma debe existir un sistema de reproducción de audio streaming en tiempo real.
d.	En la aplicación deberá tener sistema de registro e inicio de sesión.
e.	Deberá contener un menú con información como nosotros, servicios, galería, contáctenos y sorteos.
f.	Un sistema de chat que permita la interacción del usuario a la cabina de transmisión en vivo.
g.	En la aplicación debe ir también un enlace a las diferentes redes sociales.


No funcionales:
1: Base de datos MySQL.
2: Front end: HTML5, CSS3, BOOTSTRAP 5, JQUERY, SWEETALERT2.
3: Node.js.

Funcionales: 
Código	Requisito Funcional.	Actor.
RF001	Conexión con base de datos.	Oyente, Administrador, Presentador.
RF002	Chat con los presentadores disponible para que los oyentes interactúen con los presentadores.	Oyente,
Presentador.
RF003	La aplicación muestra el contenido de la programación, de los sorteos y ganadores de los anteriores sorteos.	Presentador.

RF004	Descripción de la funcionalidad que tendrá el aplicativo.
-Navegación en el menú principal.
-Visualización de sorteos.
-Registros para participar en los sorteos.
-Chat para comunicarse a la cabina de emisora.
-Audio en vivo de la emisora.
-Muestra los servicios que presta la emisora.
-Sección de contacto para el oyente o usuario.
-Mapa de ubicación de los estudios de la emisora.	Oyente,
Administrador,
Participantes de la emisora.

RF005	Descripción de operaciones realizadas por la pantalla.
-Cliquear en los diferentes campos para acceder a las funcionalidades.
-Llenar el formulario de registro.
-Loguearse con usuario y contraseña.
-Hacer click en los sorteos para participar.
-Hacer click al botón frotante para escuchar el audio en vivo.
-Hacer click en el chat para entablar conversación.
-Dar play al audio en el área de entretenimiento para escuchar el contenido.
-Cliquear en el botón central para regresar de la parte inferior de la pagina al inicio.	Oyente,
Administrador,
Participantes de la emisora.
RF006	El aplicativo permitirá solo el acceso a usuarios para la participación de eventos y rifas	Usuario,
Cliente.

