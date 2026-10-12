## 1. Introducción
En esta práctica se ha trabajado con MongoDB Atlas, una plataforma en la nube que permite gestionar bases de datos NoSQL sin necesidad de instalación local.
El objetivo principal del ejercicio ha sido aprender a:
Importar datos desde un archivo JSON
Realizar consultas sobre la base de datos
Exportar datos filtrados a un nuevo archivo
Todo ello utilizando las herramientas proporcionadas por MongoDB Atlas.

## 2. Creación del entorno
En primer lugar, se ha creado una cuenta en MongoDB Atlas y se ha generado un nuevo proyecto.
Posteriormente, se ha configurado un clúster en la nube seleccionando:
Proveedor: Amazon Web Services (AWS).
Región: Francia, como consecuencia de poner free.
La elección del proveedor no afecta directamente al desarrollo de la práctica, pero determina la ubicación física de los servidores donde se almacenan los datos.

## 3. Creación de la base de datos
Una vez creado el clúster, se ha procedido a la creación de la base de datos:
Nombre de la base de datos: biblio
Nombre de la colección: libros
Esta colección será la encargada de almacenar los documentos importados desde el archivo JSON.

## 4. Importación de datos
Para la importación de datos se ha utilizado un archivo en formato JSON que contiene un conjunto de libros organizados en forma de array.
Durante este proceso surgió un problema importante: al intentar insertar el contenido del archivo directamente mediante la opción “Insert Document”, se produjo un error (INVALID_DOCUMENT). Esto se debe a que dicha opción solo permite insertar un único documento, mientras que el archivo contenía múltiples documentos dentro de un array ([ ]).
Finalmente, se solucionó utilizando la opción de importación adecuada dentro de la interfaz de MongoDB Atlas, que permite cargar archivos JSON completos.
Cabe destacar que, al realizar la práctica desde un dispositivo móvil, la interfaz presenta ciertas limitaciones, lo que hizo que este paso resultara más complejo de lo esperado.

## 5. Consultas básicas (find)
Una vez importados los datos, se han realizado distintas consultas sobre la colección.
Por ejemplo, para obtener los libros del género Fantasía se ha utilizado el siguiente filtro:
JSON
{ "genero": "Fantasia" }
Este tipo de consultas permite filtrar documentos en función de condiciones específicas, utilizando una sintaxis basada en JSON.
También se han realizado otras consultas como:
Libros publicados antes de 1950
Libros de un autor concreto
Estas operaciones se ejecutan directamente desde el panel de MongoDB Atlas.

## 6. Operaciones de agregación (aggregation)
Uno de los puntos más importantes de la práctica ha sido el uso de agregaciones.
En concreto, se ha utilizado una operación para agrupar los libros por género y contar cuántos hay en cada categoría.
Esta operación se basa en:
$group → agrupa los documentos
$sum → cuenta el número de elementos
El resultado muestra el número total de libros por cada género existente en la colección.

## 7. Uso de inteligencia artificial
Durante la realización de la práctica, se ha utilizado la funcionalidad de asistencia basada en inteligencia artificial integrada en MongoDB Atlas.
Esta herramienta permite generar consultas complejas, como agregaciones, a partir de descripciones en lenguaje natural, facilitando el trabajo y mejorando la comprensión de las operaciones realizadas.
Posteriormente, se ha analizado el resultado para comprender su funcionamiento.

## 8. Exportación de datos
Para la exportación de datos, MongoDB proporciona el comando:

mongoexport --db biblio --collection libros 
--query '{"genero": "Fantasia"}' --out libros_fantasia.json

Este comando permite exportar los documentos que cumplen una determinada condición (en este caso, los libros del género Fantasía) a un archivo JSON.

Sin embargo, debido a las limitaciones del dispositivo móvil, no ha sido posible ejecutar este comando directamente, ya que requiere el uso de una terminal.
Por ello, se ha simulado el proceso mediante la visualización de los datos filtrados dentro de MongoDB Atlas.

## 9. Problemas encontrados
Durante la práctica se han identificado varias dificultades:
 *Limitaciones de la interfaz en dispositivos móviles. solo hace falta ver la verticalidad de las capturas para saber que el ejercicio se hizo íntegramente con movil,
y tampoco que es sea un smartphone reciente, puesto que es de 2020.
 *Error al meter el contenido dek documento '.json' (INVALID_DOCUMENT)
Imposibilidad de ejecutar comandos como mongoimport y mongoexport
 *Dificultades en el uso de agregaciones desde el móvil
A pesar de estos problemas, se han encontrado soluciones alternativas que han permitido completar la práctica.

## 10. Conclusión
Esta práctica ha permitido adquirir conocimientos sobre el uso de bases de datos NoSQL en la nube, así como sobre la gestión de datos en MongoDB.
Se ha aprendido a:
Importar datos desde archivos JSON
Realizar consultas básicas
Comprender el funcionamiento de las agregaciones
Utilizar herramientas modernas, 
como MongoDB Atlas, lo que aporta una visión práctica y aplicada al mundo profesional.
