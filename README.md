# UF2213
## UF2213: MODELOS DE DATOS Y VISIÓN CONCEPTUAL DE UNA BASE DE DATOS
## UD2 Introducción a las Bases de Datos
### 1. Introducción

En esta unidad, se explorará el origen y el concepto de las bases de datos, así como la evolución de los sistemas gestores de bases de datos. Se abordarán los objetivos y servicios a los que están orientadas las bases de datos. Finalmente, se realizará una descripción de varios tipos de modelos que pueden encontrarse, aunque se focalizará la atención en el modelo relacional, dada su amplia popularidad y reconocimiento en la actualidad.  

<img 
  src="https://iili.io/qdKqXRf.png" 
  alt="image host" 
  width="500" 
  style="display: block; margin: 0 auto;"
/>



<img 
  src="https://files.catbox.moe/j4picy.jpg" 
  alt="image host" 
  width="500" 
  style="display: block; margin: 0 auto;"
/>

Hay distintos tipos de SGBD según la manera en la que se manejen los datos y de distintos tamaños según la capacidad del ordenador.

Generalmente se accede a los datos mediante lenguajes de interrogación, lenguajes de alto nivel que simplifican la tarea de construir las aplicaciones.

En el mercado hay una variedad de Sistemas de Gestión de Bases de Datos (SGBD) disponibles, algunos de ellos están enfocados en su uso personal, mientras que otros están diseñados para un uso más profesional.

<img 
  src="https://files.catbox.moe/4thtb6.jpg" 
  alt="image host" 
  width="360" 
  style="display: block; margin: 0 auto;"
/>

#### **Sistemas libres**

Existen diversos Sistemas de Gestión de Bases de Datos (SGBD) de código abierto y libres en el mercado, entre los cuales se encuentran algunos de los más populares:

- MySQL: es uno de los SGBD más conocidos y utilizado en el mundo.
    
    [https://www.mysql.com/](https://www.mysql.com/)
    
- PostgreSQL: se trata de un SGBD relacional de código abierto y cuenta con características avanzadas.
    
    [https://www.postgresql.org/](https://www.postgresql.org/)
    
- MariaDB: es una bifurcación de MySQL, también de código abierto y compatible con la mayoría de las aplicaciones de MySQL.
    
    [https://mariadb.org/](https://mariadb.org/)
    
- MongoDB: es un SGBD de documentos de código abierto que utiliza un modelo de datos basado en documentos JSON.
    
    [https://www.mongodb.com/](https://www.mongodb.com/)
    
- SQLite: es un SGBD de código abierto, ligero y autónomo, especialmente útil para aplicaciones móviles y embebidas.
    
    [https://sqlite.org/index.html](https://sqlite.org/index.html)

- Firebird: es un SGBD relacional de código abierto que incluye características avanzadas como transacciones ACID, replicación, y soporte para triggers y procedimientos almacenados.
    
    [https://firebirdsql.org/](https://firebirdsql.org/)
    

#### **Sistemas no libres**

Hay varios sistemas de gestión de bases de datos que no son libres, lo que significa que no son de código abierto y requieren una licencia para su uso. Algunos de los más conocidos son:

- Oracle Database: un SGBD relacional muy utilizado en el mundo empresarial, enfocado en la gestión de datos a gran escala y alta disponibilidad.
    
    [https://www.oracle.com/es/database/](https://www.oracle.com/es/database/)
    
- Microsoft SQL Server: un SGBD relacional que funciona en sistemas operativos Windows y es compatible con los lenguajes de programación de Microsoft como .NET.
    
    [https://www.microsoft.com/es-es/sql-server/sql-server-2022](https://www.microsoft.com/es-es/sql-server/sql-server-2022)
    
- IBM DB2: un SGBD relacional utilizado principalmente en entornos empresariales, compatible con una amplia variedad de plataformas.
    
    [https://www.ibm.com/es-es/db2](https://www.ibm.com/es-es/db2)
    
- SAP HANA: un SGBD de memoria en tiempo real utilizado para análisis y aplicaciones en tiempo real.
    
    [https://www.sap.com/spain/products/technology-platform/hana.html](https://www.sap.com/spain/products/technology-platform/hana.html)
    
- Sybase ASE: un SGBD relacional utilizado principalmente en entornos empresariales para aplicaciones de alto rendimiento.
    
    [https://www.sap.com/spain/products/technology-platform/sybase-ase.html](https://www.sap.com/spain/products/technology-platform/sybase-ase.html)

<img 
  src="https://files.catbox.moe/2xgfkh.jpg" 
  alt="image host" 
  width="200" 
  style="display: block; margin: 0 auto;"
/>
<p style="text-align: center; font-style: italic; margin: 0.5em 0;">
  Logotipo de IBM.DB2
</p>
  


#### **Roles**

Dentro de un sistema de gestión de bases de datos (SGBD), los usuarios que interactúan con el sistema pueden desempeñar diferentes roles. Algunos de los roles más comunes son:

- **Administrador de bases de datos:** es responsable de administrar y mantener el sistema de base de datos, lo cual incluye configuración, rendimiento y seguridad. Este rol también puede implicar la creación y eliminación de bases de datos, usuarios y permisos.
    
- **Desarrollador de bases de datos:** se encarga de diseñar, desarrollar y mantener la estructura de la base de datos, incluyendo las tablas, índices, vistas y procedimientos almacenados.
    
- **Usuario final:** es el rol más común y se refiere a aquellos usuarios que utilizan la base de datos para realizar consultas y operaciones diarias, como la inserción, actualización y eliminación de datos.
    
- **Administrador de seguridad:** es responsable de gestionar los usuarios y permisos, lo que incluye la creación, modificación y eliminación de cuentas de usuario y el control de los permisos de acceso a los datos.
    
- **Administrador de copias de seguridad y recuperación:** es el encargado de planificar, implementar y supervisar las políticas de copias de seguridad y recuperación de datos, garantizando la integridad y disponibilidad de la información almacenada en la base de datos.
    

Los roles están diseñados para facilitar la administración del sistema del usuario final sus privilegios sobre el objeto. Sin embargo, los roles no están destinados a ser utilizados por los desarrolladores de aplicaciones, ya que los privilegios para acceder a los objetos dentro del SGBD deben ser concedidos directamente.

Los roles son un conjunto de privilegios etiquetados por un único nombre (el nombre del rol), que pueden ser concedidos a otros usuarios o roles. Una vez creado el rol y asignados sus privilegios se les asignará a los usuarios que deban tener estos privilegios. Así evitamos tener que volver repetir a cada usuario los mismos privilegios.

En general, se crea un rol que va a servir para uno o dos propósitos: para gestionar los privilegios de una aplicación de base de datos o para gestionar los privilegios para un grupo de usuarios.

- **Rol de la aplicación** se otorga una rol de aplicación con todos los privilegios necesarios para ejecutar una aplicación de base de datos dada. Se concede un rol de aplicación a otros roles o usuarios específicos. Una aplicación puede tener varios roles diferentes, es decir, cada rol es asignado con un conjunto diferente de privilegios que permiten mayor o menor acceso a los datos según el rol.
    
- **Rol de usuario** se crea para un grupo de usuarios que necesitan unas autorizaciones comunes. La gestión de los privilegios de usuarios se controla concediendo roles de aplicación y privilegios al rol del usuario asociado o del grupo de usuarios correspondientes.
    

<img 
  src="https://files.catbox.moe/alu3kg.jpg" 
  alt="image host" 
  width="400" 
  style="display: block; margin: 0 auto;"
/>

Por ejemplo, el SGBD Oracle tiene unos roles predefinidos:

- **CONNECT** permite al usuario conectarse a la base de datos, crear tablas, vistas, secuencias, sinónimos... ya que sus privilegios son alter session, create session, create cluster, create table, create view, create synonym, create sequence, create database link.

- **RESOURCE** permite al usuario utilizar los recursos típicos para la programación de la aplicación (clusters, disparadores, paquetes, funciones, etc.). Sus privilegios son create cluster, create table, create procedure, create sequence, create trigger.
    
- **DBA** es típico de los administradores, permite al usuario realizar cualquier función de la base de datos y disponer de cualquier privilegio.
    

La sentencia que permite crear roles es CREATE ROL.


```SQL
CREATE ROLE rol
[NOT IDENTIFIED
| IDENTIFIED {BY password | USING [usuario.] paquete
| EXTERNALLY | GLOBALLY }
];
```

- **NOT IDENTIFIED** indica que el rol no requiere contraseña.
    
- **IDENTIFIED BY** indica que el rol si requiere contraseña.
    
- **EXTERNALLY** crea un rol de usuario externo.
    
- **GLOBALY** crea un rol de usuario global.
    

Ejemplo: Crear un rol y asignar privilegios.

```SQL
CREATE ROLE miPrimerRole;
GRANT SELECT, INSERT, UPDATE, DELETE ON tabla
TO miPrimerRole;
```

Ejemplo: Asignarle un rol a un usuario.

```SQL
GRANT miPrimerRole TO miUsuario;
```

Ejemplo: Eliminar un rol.

```SQL
DROP ROLE miPrimerRole;
```

<img 
  src="https://files.catbox.moe/6ti1df.jpg" 
  alt="image host" 
  width="400" 
  style="display: block; margin: 0 auto;"
/>

#### **Perfiles de Usuario**

Los perfiles de usuario se utilizan para limitar la cantidad de recursos del sistema y de la base de datos disponible para un usuario.

Si no se ha definido un perfil concreto para un usuario, se utiliza un perfil por defecto que especifica los recursos ilimitados.

Los recursos que pueden ser limitados vía perfil son:

- SESSIONS_PER_USER, número de sesiones concurrentes que un usuario puede tener en una instancia.
    
- CPU_PER_SESSION, tiempo que puede usar de la CPU.
    
- CONNECT_TIME, el número de minutos que la sesión puede permanecer activa.
    
- IDLE_TIME, minutos que una sesión puede permanecer sin que sea utilizada de manera activa.
    
- LOGICAL_READS_PER_SESSION, bloques de datos que pueden leer en una sesión.
    
- LOGICAL_READS_PER_CALL, bloques de datos que pueden leer en una operación.
    
- PRIVATE_SGA, cantidad de espacio privado que una sesión puede reservar en la zona de SQL compartida del SGA.
    
- COMPOSITE_LIMIT, número total de recursos por sesión, en unidades de servicio. Esto resulta de un cálculo preponderado de

CPU_PER_SESSION, CONNECT_TIME, LOGICAL_READS_PER_SESSION y PRIVATE_SGA.

Los perfiles se pueden crear vía comando CREATE PROFILE, y se pueden modificar con la sentencia ALTER PROFILE. En general, un perfil por defecto de adecua por los usuarios normales, los usuarios con requerimientos especiales deberán tener perfiles especiales.

#### **Descripción de los elementos funcionales del SGBD**

Los elementos funcionales de un SGBD se pueden dividir en dos componentes **Sistema Gestor de Almacenamiento** y el **Procesador de Consultas**.

##### **El Gestor de Almacenamiento**

Un gestor de almacenamiento es una parte fundamental de un SGBD, que se encarga de administrar el almacenamiento y la organización de los datos en una base de datos.

Su tarea principal es asignar y liberar espacio en disco, organizar la estructura física de los datos, y garantizar la integridad y consistencia de los mismos.

Además, lleva a cabo operaciones como la indexación, compresión, fragmentación, y gestión de transacciones y recuperación de fallos.

Lo componen:

- **Gestor de autorización e integridad:** es un componente clave en un SGBD que se encarga de proteger y garantizar la integridad de los datos almacenados. Su tarea principal es controlar el acceso a los datos y asegurar que solo los usuarios autorizados puedan acceder y modificar los datos. El gestor de autorización define y administra los permisos de acceso para cada usuario o grupo, mientras que el gestor de integridad se encarga de definir restricciones que deben cumplirse para garantizar que los datos sean precisos y consistentes. En definitiva, el gestor de autorización e integridad es fundamental para la seguridad y precisión de los datos almacenados en la base de datos.

- **Gestor transaccional**: es una parte fundamental de un SGBD que se encarga de controlar y gestionar las transacciones en una base de datos. Las transacciones son una serie de operaciones que se ejecutan de forma atomizada y el gestor transaccional se asegura de que todas las operaciones se completen correctamente o que se deshagan todas las operaciones si ocurre algún error en el proceso. Utiliza el mecanismo de registro de transacciones para mantener un registro de las operaciones realizadas y su estado, lo que permite deshacer las operaciones que ya se han realizado en caso de fallos. Además, también garantiza la concurrencia de acceso a los datos, evitando conflictos y garantizando la consistencia de los datos. En definitiva, el gestor transaccional es esencial para garantizar la integridad, la consistencia y la concurrencia de los datos en una base de datos.
    
- **Gestor de archivos**: se refiere a la manera en que se estructuran y acceden a los datos almacenados en la base de datos. El gestor de archivos es un elemento fundamental del SGBD que se encarga de gestionar tanto los archivos de datos como los archivos de control de acceso a los mismos. El gestor de archivos se encarga de organizar físicamente los datos en la base de datos, es decir, cómo se almacenan los datos en los dispositivos de almacenamiento físico, como discos duros y unidades flash, entre otros. También se ocupa de la administración del espacio en disco, es decir, cómo se asigna y libera el espacio de almacenamiento en el dispositivo.
    
- **Gestor de memoria intermedia**: es un componente vital en los Sistemas de Gestión de Bases de Datos (SGBD), ya que se encarga de administrar la memoria temporal conocida como caché. Este almacenamiento temporal tiene como objetivo reducir la cantidad de operaciones de entrada/salida requeridas para acceder a los datos en el disco y mejorar el rendimiento del sistema. El gestor de memoria intermedia utiliza algoritmos para decidir qué datos almacenar en la caché y cuáles deben eliminarse en función de factores como la frecuencia de acceso, la cantidad de memoria disponible y la relevancia de los datos. Además, también garantiza la integridad de los datos almacenados en la caché y asegura que los cambios realizados en los datos se reflejen correctamente en el disco. En general, el gestor de memoria intermedia es crucial para mejorar la eficiencia y el rendimiento de los SGBD.

- **Metadatos o diccionario de datos (DD):** son información almacenada en un sistema de gestión de bases de datos (SGBD) que describe la estructura y contenido de una base de datos. Los metadatos contienen detalles sobre los objetos de la base de datos, como tablas, columnas, índices, procedimientos almacenados, restricciones y relaciones entre ellos. Los metadatos son utilizados por el SGBD para realizar diversas operaciones, como la validación de consultas, la gestión de transacciones y la optimización de consultas. Asimismo, se utilizan para garantizar la integridad y la consistencia de los datos almacenados en la base de datos.
    

##### **El procesador de consultas**

El procesador de consultas en un SGBD se encarga de ejecutar las consultas realizadas por los usuarios en la base de datos.

El procesamiento de consultas implica una serie de etapas, como el análisis sintáctico y semántico de la consulta, la optimización de la consulta para determinar el plan de ejecución más eficiente, la generación del plan de ejecución y finalmente la ejecución de la consulta en sí.

La eficiencia del procesamiento de consultas es un factor clave para el rendimiento de la base de datos, ya que afecta directamente al tiempo de respuesta de las consultas y al uso de recursos del sistema.

Lo componen:

- **Interprete del DDL:** es un componente fundamental de los sistemas de gestión de bases de datos (SGBD), que se utiliza para definir la estructura y las restricciones de los datos almacenados en una base de datos. Su principal función es procesar y ejecutar los comandos DDL enviados por los usuarios, verificando la sintaxis y convirtiéndolos en comandos de bajo nivel que el SGBD pueda entender y procesar. El Intérprete del DDL también es responsable de la gestión de objetos de la base de datos, como tablas, índices, restricciones y vistas. Por ejemplo, si un usuario envía un comando DDL para crear una nueva tabla, el Intérprete del DDL verificará si la tabla ya existe y, si no, creará la tabla utilizando los comandos de bajo nivel correspondientes.

- **Compilador del LMD:** es un componente clave que se encarga de procesar y ejecutar las consultas y comandos de manipulación de datos que se realizan en la base de datos. Su función principal es traducir los comandos DML escritos por el usuario en un lenguaje que pueda entender la base de datos, de manera que se puedan llevar a cabo las operaciones solicitadas de manera eficiente y precisa. El compilador del DML se encarga de analizar la sintaxis y semántica de las consultas y comandos DML para generar un plan de ejecución que permita llevar a cabo la operación de manera óptima. En resumen, el compilador del DML es un componente esencial en un SGBD, ya que permite que los usuarios puedan interactuar con la base de datos de manera efectiva y realizar las operaciones de manipulación de datos necesarias para su aplicación.
    
- **Motor de evaluación de consultas:** es un componente esencial que se encarga de procesar las consultas que se realizan sobre la base de datos. Su función principal es traducir la consulta escrita en un lenguaje de consulta, como SQL, a un plan de ejecución que el SGBD pueda entender y ejecutar. El motor de evaluación de consultas también se encarga de optimizar el plan de ejecución, evaluando diferentes estrategias para recuperar los datos de la base de datos y seleccionando la mejor opción en términos de rendimiento y eficiencia. Además, se encarga de ejecutar el plan de ejecución y recuperar los resultados de la consulta.
    

#### **Características**

- **Independencia física**, el nivel físico puede ser modificado independientemente del nivel conceptual. El usuario no puede ver todos los componentes hardware de la base de datos, que es simplemente una estructura transparente que representa la información almacenada.
    
- **Independencia lógica**, el nivel conceptual puede ser modificado independientemente del nivel físico, es decir, el administrador de la base de datos puede introducir mejoras sin afectar a los demás usuarios alojados en la base de datos.

- **Facilidad de uso**, Las usuarios que no estén familiarizados con la base de datos deben poder almacenar y recuperar información a través de las consultas sin hacer referencia a los componentes técnicos de la base de datos.
    
- **Acceso rápido**, El sistema debe de almacenar y recuperar la información de la manera más rápida posible, para ello se requieren algoritmos de consultas más rápidos.
    
- **Administración centralizada**, se debe poder manipular los datos del sistema y verificar la integridad de una manera centralizada.
    
- **Redundancia controlada**, un SGBD eficaz debe de poder evitar la redundancia de los datos siempre que sea posible, tanto para minimizar los errores como par prevenir el desperdicio de la memoria.
    
- **Verificación de integridad**, Los datos deben de tener una coherencia y cuando unos elementos hacen referencia a otros, estos últimos deben de estar presentes.
    
- **Uso compartida de datos**, que múltiples usuarios puedan acceder simultáneamente a la base de datos.
    
- **Seguridad de los datos**, se refiere a los derechos de acceso a los datos de cada usuario.
    

#### **Funciones**

- **Almacenamiento, extracción y actualización de los datos**, Un SGBD debe proporcionar a los usuarios la capacidad de almacenar datos en la base de datos, acceder a ellos y actualizarlos. Esta es la función fundamental de un SGBD y por supuesto, el SGBD debe ocultar al usuario la estructura física interna (la organización de los ficheros y las estructuras de almacenamiento).
    
- **Un catalogo accesible por el usuario**, debe proporcionar un catálogo en el que se almacenen las descripciones de los datos y que sea accesible por los usuarios. El catálogo se denomina diccionario de datos y contiene información que describe los datos de la base de datos.

- **Soporte de transacciones**, debe proporcionar un mecanismo que garantice que todas las actualizaciones correspondientes a una determinada transacción se realicen, o que no se realice ninguna. Una transacción es un conjunto de acciones que cambian el contenido de la base de datos.
    
- **Servicios de control de concurrencia**, proporciona un mecanismo que asegure que la base de datos se actualice correctamente cuando varios usuarios la están actualizando concurrentemente. Uno de los principales objetivos de los SGBD es el permitir que varios usuarios tengan acceso concurrente a los datos que comparten. El acceso concurrente es relativamente fácil de gestionar si todos los usuarios se dedican a leer datos, ya que no pueden interferir unos con otros. Sin embargo, cuando dos o más usuarios están accediendo a la base de datos y al menos uno de ellos está actualizando datos, pueden interferir de modo que se produzcan inconsistencias en la base de datos. El SGBD se debe encargar de que estas interferencias no se produzcan en el acceso simultáneo.
    
- **Servicios de recuperación**, mecanismo capaz de recuperar la base de datos en caso de que ocurra algún suceso que la dañe.
    
- **Servicios de autorización**, Garantizar que sólo los usuarios autorizados pueden acceder a la base de datos. La protección debe ser contra accesos no autorizados, tanto intencionados como accidentales.
    
- **Soporte para la tramitación de datos**, Un SGBD debe ser capaz de integrarse con algún software de comunicación. Muchos usuarios acceden a la base de datos desde terminales. En ocasiones estos terminales se encuentran conectados directamente a la máquina sobre la que funciona el SGBD. En otras ocasiones los terminales están en lugares remotos, por lo que la comunicación con la máquina que alberga al SGBD se debe hacer a través de una red. En cualquiera de los dos casos, el SGBD recibe peticiones en forma de mensajes y responde de modo similar. Todas estas transmisiones de mensajes las maneja el gestor de comunicaciones de datos. Aunque este gestor no forma parte del SGBD, es necesario que el SGBD se pueda integrar con él para que el sistema sea comercialmente viable.

- **Servicios de integridad**, Son los medios necesarios para garantizar que tanto los datos de la base de datos, como los cambios que se realizan sobre estos datos, sigan ciertas reglas. Se puede considerar como otro modo de proteger la base de datos, pero además de tener que ver con la seguridad. La integridad se ocupa de la calidad de los datos. Normalmente se expresa mediante restricciones, que son una serie de reglas que la base de datos no puede violar.
    
- **Servicios para mejorar la independencia de los datos**, Permitir que se mantenga la independencia entre los programas y la estructura de la base de datos. La independencia de datos física es más fácil de alcanzar, de hecho hay varios tipos de cambios que se pueden realizar sobre la estructura física de la base de datos sin afectar a las vistas. Sin embargo, lograr una completa independencia de datos lógica es más difícil. Añadir una nueva entidad, un atributo o una relación puede ser sencillo, pero no es tan sencillo eliminarlos.
    
- **Servicios de utilidad**, Un SGBD debe proporcionar una serie de herramientas que permitan administrar la base de datos de modo efectivo. Algunas herramientas trabajan a nivel externo, por lo que habrán sido producidas por el administrador de la base de datos. Las herramientas que trabajan a nivel interno deben ser proporcionadas por el distribuidor del SGBD. Algunas de ellas son:
    
    - Herramientas para importar y exportar datos.
        
    - Herramientas para monitorizar el uso y el funcionamiento de la base de datos.
        
    - Programas de análisis estadístico para examinar las prestaciones o las estadísticas de utilización.
        
    - Herramientas para reorganización de índices.
        
- **Herramientas para aprovechar el espacio dejado en el almacenamiento físico por los registros borrados y que consoliden el espacio liberado para reutilizarlo cuando sea necesario.**

#### Terminología de SGDB

###### Campo - Field

Identifica solo un elemento dentro de la tabla con características específicas como tipo de datos, longitud, número de decimales, etc.

###### Consulta - Query

Identifica una instrucción propia del motor de base de datos que interactúa con los datos almacenados en esta. Generalmente son instrucciones de lectura, aun que muchas veces se utiliza el término Query para cualquier instrucción (escritura, procesamiento o administración).

###### Tabla - Table

Identifica un objeto contenedor de información estructurada, esta estructura se repite en todos los registros en ella.

###### Vista - View

Identifica una consulta residente en el servidor que puede ejecutarse con una instrucción simple como si fuera otra tabla de la base de datos.

#### Gestión de índices

El índice de una base de datos es una estructura de datos que mejora la velocidad de las operaciones, permitiendo un rápido acceso a los registros de una tabla en una base de datos. Al aumentar drásticamente la velocidad de acceso, se suelen usar sobre aquellos campos sobre los cuales se hacen frecuentes búsquedas.

El índice tiene un funcionamiento similar al índice de un libro, guardando parejas de elementos: el elemento que se desea indexar y su posición en la base de datos. Para buscar un elemento que esté indexado, sólo hay que buscar en el índice dicho elemento para, una vez encontrado, devolver el registro que se encuentre en la posición marcada por el índice.

Los índices pueden ser creados usando una o más columnas, proporcionando la base tanto para búsquedas rápidas al azar como de un ordenado acceso a registros eficiente.

Los índices pueden ser definidos como únicos o no únicos. Un índice único actúa como una restricción en la tabla previniendo filas idénticas en el índice.

#### Seguridad

<img src="https://files.catbox.moe/b27ofq.jpg" alt="image host" width="100"/>

##### Medidas de seguridad en tratamiento de base de datos

- Físicas: controlar el acceso al equipo. Tarjetas de acceso, etc.
    
- Personal: acceso sólo del personal autorizado. Evitar sobornos, etc.
    
- SO: seguridad a nivel de SO
    
- SGBD: uso herramientas de seguridad que proporcione el SGBD. Perfiles de usuario, vistas, restricciones de uso de vistas, etc.
    

Un BDMS es un programa de software diseñado para gestionar y administrar bases de datos se conoce como un Sistema Manejador de Bases de Datos. Su propósito principal es permitir a los usuarios crear, modificar y eliminar bases de datos, así como también acceder a los datos almacenados en ellas de forma eficiente y segura.

Estos sistemas ofrecen una amplia gama de herramientas y funcionalidades para la gestión de bases de datos, como la creación y modificación de tablas, la definición de relaciones entre ellas, el control de acceso a los datos, la ejecución de consultas y la generación de informes y estadísticas. Existen diferentes tipos de BDMS, desde los más sencillos y orientados a usuarios sin experiencia en programación hasta los más complejos y diseñados para entornos empresariales de alto rendimiento. Algunos ejemplos comunes de BDMS son MySQL, Oracle, Microsoft SQL Server, PostgreSQL y MongoDB.

Las funciones de un BDMS son:

- Identificar y autorizar a los usuarios: uso de códigos de acceso y palabras claves, exámenes, impresiones digitales, reconocimiento de voz, barrido de la retina, etc.
    
- Autorización: usar derechos de acceso dados por el terminal, por la operación que puede realizar o por la hora del día.
    
- Uso de técnicas de cifrado: para proteger datos en Base de Datos distribuidas o con acceso por red o Internet.
    
- Diferentes tipos de cuentas: en especial del ABD con permisos para: creación de cuentas, concesión y revocación de privilegios y asignación de los niveles de seguridad.
    
- Manejo de la tabla de usuarios con código y contraseña, control de las operaciones efectuadas en cada sesión de trabajo por cada usuario y anotadas en la bitácora, lo cual facilita la auditoría de la Base de Datos.
    

#### Respaldos y replicación de bases de datos

Un respaldo o copia de seguridad es una medida preventiva esencial para proteger la información y los datos importantes de una organización o usuario individual en caso de pérdida, daño o robo.

Algunos de los usos más importantes de la copia de seguridad son:

- Recuperación de datos en caso de fallo del sistema
    
- Protección contra virus y malware
    
- Prevención de errores humanos
    
- Cumplimiento de regulaciones y normativas
    
- Facilitación de la migración de datos.
    

En resumen, la copia de seguridad es una medida crucial para proteger los datos y garantizar la continuidad del negocio en caso de un evento adverso.

La **replicación** en bases de datos se refiere a la copia y sincronización de datos entre varias bases de datos. Su objetivo principal es mejorar el rendimiento, la disponibilidad y la recuperación ante desastres. Esto se logra mediante una base de datos principal que se replica en una o varias bases de datos secundarias, de modo que cuando se actualiza la base de datos principal, los cambios se propagan a las bases de datos secundarias para mantenerlas sincronizadas.

Existen diferentes formas de implementar la replicación, como la replicación maestro-esclavo, la replicación en anillo y la replicación en árbol, cada una con sus propias características. La replicación puede mejorar significativamente la disponibilidad de los datos, reducir el tiempo de inactividad y aumentar la escalabilidad del sistema, pero también puede ser compleja de configurar y administrar. Por lo tanto, es importante asegurarse de que se realice de manera segura y confiable para evitar la corrupción de datos.

#### Definición de transacción

Una transacción en un Sistema de Gestión de Bases de Datos (SGBD), es un conjunto de órdenes que se ejecutan formando una unidad de trabajo, es decir, en forma indivisible o atómica.

Un SGBD se dice transaccional, si es capaz de mantener la integridad de los datos, haciendo que estas transacciones no puedan finalizar en un estado intermedio. Cuando por alguna causa el sistema debe cancelar la transacción, empieza a deshacer las órdenes ejecutadas hasta dejar la base de datos en su estado inicial (llamado punto de integridad), como si la orden de la transacción nunca se hubiese realizado.

<img 
  src="https://files.catbox.moe/rj6pf0.jpg" 
  alt="image host" 
  width="400" 
  style="display: block; margin: 0 auto;"
/>


Para esto, el lenguaje de consulta de datos SQL (Structured Query Language), provee los mecanismos para especificar que un conjunto de acciones deben constituir una transacción.

- BEGIN TRAN: Especifica que va a empezar una transacción.
    
- COMMIT TRAN: Le indica al motor que puede considerar la transacción completada con éxito.
    
- ROLLBACK TRAN: Indica que se ha alcanzado un fallo y que debe restablecer la base al punto de integridad.
    

En un sistema ideal, las transacciones deberían garantizar todas las propiedades ACID; en la práctica, a veces alguna de estas propiedades se simplifica o debilita con vistas a obtener un mejor rendimiento.

#### Tipos de protocolos de control de la concurrencia

El control de concurrencia es el proceso que se utiliza para identificar y resolver actualizaciones de datos realizadas por múltiples usuarios simultáneamente.

Dependiendo del sistema gestor de base de datos utiliza un tipo u otro de control de concurrencia.

<img 
  src="https://files.catbox.moe/lhoj3v.jpg" 
  alt="image host" 
  width="160" 
  style="display: block; margin: 0 auto;"
/>

#### Recuperación de transacciones

En cada base de datos contiene al menos un archivo de datos y un archivo de registro de transacciones. SQL Server almacena los datos físicamente en el archivo de datos (.mdf y .ndf). El archivo de transacciones (.ldf) almacena los detalles de todas las modificaciones que se realizan sobre la base de datos de SQL Server.

La escritura en el Log de transacciones es secuencial, y está optimizado para ello. Se podría decir que (por norma general) carece de sentido crear más de un fichero de log de transacciones. Aunque el algoritmo de escritura en los .ldf es algo más complejo: si tuviéramos mas de un fichero, la escritura la haría formando un bucle circular pasando por cada uno de ellos, respetando la secuencialidad en las transacciones. A diferencia de los ficheros de datos, donde si es posible mejorar el rendimiento de una base de datos, aumentado su número.

Acabamos de ver las características y funciones fundamentales de un SGBD, sin embargo, a medida que los SGBD evolucionan, se imponen nuevos objetivos adaptados a las nuevas necesidades y tecnologías. En estos momentos podemos citar como objetivos nuevos o recientes los siguientes:

- Servir eficientemente los Data Warehouse
    
- Adaptarse al desarrollo orientado a objetos.
    
- Incorporar el tiempo como un elemento caracterizado de la información.
    
- Adaptarse al mundo de Internet.
    

### 2. Evolución.

A partir de la necesidad de almacenar grandes cantidades de datos, las industrias desarrollaron un sistema de bases de datos automatizado, para su posterior consulta. Vamos a ver brevemente cómo fue su evolución.

- **1950:** El sistema de bases de datos automatizadas comenzó con el uso de cintas magnéticas, las cuales grababan la información en pistas, sobre una banda plástica, para luego ser leídas y pasar los datos a otras, a modo de backup.
    
- **1960:** En la década de los 60, se pasó de las cintas magnéticas a los discos, lo que supuso un gran adelanto ya que por este soporte se podía acceder a la información directamente sin la necesidad de saber dónde estaban ubicados los datos exactamente y en cuestión de milisegundos.
    

En este momento, nace el modelo de Base de Datos Jerárquica y de Red, donde los datos se guardan en forma de listas y árboles y un mismo nodo podía tener varios padres.

- **1970:** Es esta década, Edgar Frank Codd, definió el concepto de Base de Datos Relacional y una serie de reglas que tenían que cumplir los administradores de bases de datos.
    

Así fue como nacieron las Bases de Datos Relacionales, comenzando con Oracle y el lenguaje SQL.

- **1980:** Ahora, gracias a su bajo nivel de programación y su sencillez, las Bases de Datos Relacionales fueron un fuerte competidor en el mercado con las Bases de Datos Jerárquicas y de Red. Se comienza a investigar en otras técnicas, como las Bases de Datos orientadas a objetos.
    
- **1990:** A principio de esta década se crea el lenguaje SQL para realizar consultas sobre datos de manera más específica, pudiendo aplicar filtros para la búsqueda. A finales de los 90 apareció la World Wide Web(WWW) y con esto se facilitó la consulta a las bases de datos, con capacidad ya para el almacenamiento de grandes cantidades de datos.

En la actualidad, existen multitud de herramientas, tanto en línea como en local, para la administración y consulta de bases de datos.

### 3. Objetivos y servicios.

Los **Sistemas de Gestión de Bases de Datos (SGBD)** se diseñan con múltiples objetivos clave para garantizar un manejo eficiente y efectivo de la información. Estos objetivos abarcan diversas áreas, proporcionando beneficios sustanciales a los usuarios y administradores de bases de datos. Aquí se detallan y amplían algunos de los objetivos fundamentales de los SGBD:

1. **Abstracción de la Información:** Los SGBD ofrecen abstracción de la información al usuario, ocultando detalles sobre el almacenamiento físico de los datos. Esta característica permite que los usuarios interactúen con la base de datos sin necesidad de conocer la complejidad de su estructura de almacenamiento. Se establecen varios niveles de abstracción, simplificando así la interacción con la base de datos y facilitando su comprensión.
    
2. **Independencia:** La independencia de los datos es esencial para la flexibilidad y la evolución del sistema. Los SGBD permiten modificar el esquema, ya sea físico o lógico, de una base de datos sin afectar las aplicaciones que dependen de ella. Esto proporciona un alto grado de adaptabilidad, permitiendo realizar cambios en la estructura de la base de datos sin impactar en las aplicaciones existentes.
    
3. **Consistencia:** A pesar de los esfuerzos por eliminar redundancias, algunas situaciones pueden requerir una atención especial para garantizar la consistencia de los datos. Los SGBD facilitan la implementación de reglas y condiciones para mantener la integridad de la información, asegurando que los datos repetidos se actualicen de manera coherente. También permiten establecer condiciones lógicas para garantizar la validez de los datos almacenados.

4. **Seguridad:** Dada la importancia y el valor de la información almacenada en las bases de datos, la seguridad es una prioridad. Los SGBD implementan sistemas de gestión de permisos que controlan el acceso a los datos. Los usuarios y grupos de usuarios pueden recibir diferentes categorías de permisos, asegurando que solo aquellos autorizados puedan acceder, modificar o eliminar información sensible.
    
5. **Manejo de Transacciones:** Los SGBD facilitan el manejo de transacciones, que son programas ejecutados como una sola operación. Esto garantiza que, en caso de falla, la base de datos permanezca en un estado coherente. Los mecanismos proporcionados por los SGBD simplifican la programación de modificaciones de datos, asegurando la integridad y la consistencia de la base de datos incluso en escenarios complejos.
    
6. **Tiempo de Respuesta:** La eficiencia operativa es esencial, y los SGBD buscan minimizar el tiempo que tardan en proporcionar información solicitada y en procesar y almacenar cambios realizados en la base de datos. La optimización del tiempo de respuesta contribuye significativamente a la usabilidad y la eficacia global del sistema.
    

<img 
  src="https://files.catbox.moe/ks6b2y.jpg" 
  alt="image host" 
  width="200" 
  style="display: block; margin: 0 auto;"
/>

### 4. Modelo lógico de BD:

A continuación, se exploran diversos tipos de modelos de bases de datos, con un enfoque destacado en el modelo relacional:

#### 4.1. Modelo jerárquico.

El modelo jerárquico organiza los datos en una estructura de árbol, donde las relaciones se establecen como padre/hijo. Cada padre puede tener varios hijos, pero cada hijo tiene un solo padre. Este enfoque simplifica las relaciones pero puede resultar limitado en la representación de conexiones más complejas.

<img 
  src="https://files.catbox.moe/bekbgm.jpg" 
  alt="image host" 
  width="540" 
  style="display: block; margin: 0 auto;"
/>

#### 4.2. Modelo en red.

Evolutivo del modelo jerárquico, el modelo en red permite que los nodos hijo tengan más de un nodo padre, posibilitando una mayor diversidad de relaciones entre las entidades. Representado como un grafo de red, consta de registros conectados mediante enlaces, similar a las entidades en el modelo relacional.

<img 
  src="https://files.catbox.moe/k79yb5.jpg" 
  alt="image host" 
  width="240" 
  style="display: block; margin: 0 auto;"
/>

#### 4.3. Modelo relacional.

Basado en tablas o relaciones, el modelo relacional representa los datos mediante claves únicas. Ampliamente utilizado en aplicaciones empresariales y de investigación, utiliza claves foráneas para establecer relaciones entre tablas. Las operaciones se realizan mediante consultas SQL, ofreciendo simplicidad y flexibilidad.

<img 
  src="https://files.catbox.moe/q009j8.jpg" 
  alt="image host" 
  width="380" 
  style="display: block; margin: 0 auto;"
/>

#### 4.4. Modelo relacional extendido.

El modelo ER amplía el modelo relacional, organizando datos en entidades, atributos y relaciones. Incluye características como herencia, subtipos y supertipos, proporcionando mayor flexibilidad en la representación de datos. Aunque más complejo, se utiliza en aplicaciones que requieren precisión y flexibilidad.

<img 
  src="https://files.catbox.moe/npov40.jpg" 
  alt="image host" 
  width="400" 
  style="display: block; margin: 0 auto;"
/>

#### 4.5. Modelo orientado a objetos.

Basado en la idea de objetos, el modelo OOM almacena datos en objetos con propiedades y métodos, clasificados en clases. Permite una representación detallada y precisa de los objetos del mundo real, con herencia de clases y encapsulación de datos. Se utiliza en aplicaciones que requieren una representación exacta de objetos, como juegos y sistemas de información geográfica.

<img 
  src="https://iili.io/qJZOJPR.jpg" 
  alt="image host" 
  width="400" 
  style="display: block; margin: 0 auto;"
/>


