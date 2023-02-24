# Fusión y lectura de datos XML, TXT en MySQL:

## Creación de la Base de Datos y sus tablas
El Product Owner (de ahora en adelante, P.O.) nos hace llegar tres archivos (.xml, .txt y .sql) con
 el objetivo de fusionarlos en una única base de datos. Para ello, será necesario elaborar un programa que facilite la legibilidad de los datos tal y como nos solicita el P.O., además de automatizar el proceso de limpieza para futuros inputs que lleguen a la base de datos, y los relacione entre ellos.

### Características de la Base de Datos
En un fichero .sql (sql_code.sql) comenzamos este proyecto con la creación de la base de datos "project1", donde se agregará la información de los tres ficheros que nos facita el P.O. en diferentes tablas. Para ello, es necesario crear una tabla para cada fichero en MySQL Workbench ("data_sql", "data_xml", "data_txt").

Las especificaciones que deben cumplir las tablas son:
- "data_sql": debe almacenar los datos del archivo data_sql.sql. Debe ser la tabla madre, donde la clave primaria es de tipo numérico y se corresponde con la columna "index_sql". El resto de columnas son de tipo texto.
- "data_xml": debe almacenar los datos del archivo data_xml.xml. Su clave primaria es "index_xml" y su clave foránea es la columna "index_sql", ambas de tipo numérico. El resto de columnas son de tipo texto.
- "data_txt": debe almacenar los datos del archivo data_txt.txt. Su clave primaria es "index_txt" y su clave foránea es la columna "index_sql", ambas de tipo numérico. El resto de columnas son de tipo texto.

Las tres tablas se relacionarán mediante la columna "index_sql".
Para la creación de las tablas observamos previamente el contenido de las columnas para ajustar las características de la columna al tipo de dato que va a contener.


## Lectura y explicación de la estructura del archivo .sql:
El Product Owner (de ahora en adelante, P.O.) nos hace llegar tres archivos (.xml, .txt y .sql) con el objetivo de fusionarlos en una única base de datos. Para ello, será necesario elaborar un programa que facilite la legibilidad de los datos tal y como nos solicita el P.O., además de automatizar el proceso de limpieza para futuros inputs que lleguen a la base de datos.

### Características del archivo .sql:


Uno de los ficheros que recibimos es un archivo .sql (data_sql.sql). Después de una primera visualización del documento en MySQl Workbench encontramos:

- Al principio del fichero, vemos las características del archivo, que no son necesarias para los objetivos del proyecto.

- A partir de la línea 24 de este archivo, observamos una serie de datos dispuestos de tal manera que se puede apreciar que es una tabla.

- Con relación a la estructura de los datos, se puede apreciar que las filas de la futura tabla están organizados dentro de paréntesis. A su vez, dentro de cada paréntesis, vemos la division de columnas por comas (",").

- Llama la atención el gran número de "errores" que hay registrados.

- Se evidencia que el nombre de las columnas no está disponible en este archivo.

- Al principio de cada línea se observan un número que corresponderá a los "indices_sql". Estos índices relacionan cada fila del archivo .sql con la fila del mismo índice en el archivo .xml y el archivo .txt.

- Por otra parte, estos registros presentan los datos para una columna que el P.O. nos ha pedido que eliminemos (d482xta).



### Limpieza del archivo .sql
Una vez observado todo lo tratado en el apartado anterior, procedemos a trabajar con el archivo .sql en MySQL Workbench. Para ello hemos de tener en cuenta los requerimientos del P.O.:
- Cambiar los "ERROR" por "NULL".
- Quitar la columna d482xta.

Al tomar los datos a introducir del apartado "VALUES" del archivo .sql, observamos que se insertan correctamente en la tabla "data_sql" creada en la base de datos project1.




