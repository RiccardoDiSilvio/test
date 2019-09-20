Manejar busquedas
==================


Realizar busquedas
------------------ 

Para realizar una busqueda en bases de datos criminales, se usa el siguiente endpoint:

      URL: https://panel.validu.co/api/query_sarlaft/                   
      Method: POST   
      Content-Type: application/json

Los datos por enviar son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|first_name|string|Los nombres de la persona por buscar|
|last_name|string|Los apellidos de la persona por buscar|
|type_query_id|int|El tipo de busqueda por ejecutar|
|document_number|int|El numero de documento, se puede dejar en blanco en caso que no se conozca|

Los datos retornados son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si encontró un error o no|
|message|string|En caso error = true, describe el error|
|data|lista|Contiene un diccionario con los siguientes datos|
|id|int|El id del query en el sistema|
|last_name|string|Los apellidos del buscado|
|date_created|String|La hora en GMT en la que se realizó la busqueda|
|document_number|int|El numero de documento|
|name|string|El nombre del buscado|
|data|Lista|Lista de diccionarios con los siguientes datos|
|codcliente|int|El id de Validu en las bases de datos ajenas|
|porcentaje|int|El porcentaje de coincidencia|
|id_encontrado|int|El numero de cedula proveido|
|nombreencontrado|string|El nombre completo proveido|
|fecha_noticia|string|La fecha de la noticia en la que aparece el buscado, en formato MM-DD-YYYY|
|fuente|string|La fuente de la noticia ej. Prensa|
|hecho|string|El delito acusado|
|dv|string|Dato vacío|
|informacion|string|La base de datos de la coincidencia|
|coincidencia|string|El metodo por el cual se encontró la coincidencia|



Obtener todos los tipos de busquedas
------------------------------------

Para esto se usa el siguiente endpoint:

      URL: https://panel.validu.co/api/type_query/                   
      Method: GET   
      Content-Type: application/json
   
No hay que enviar datos. Devuelve lo siguiente:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|bool|Si encontró algun error|
|message|string|Si error = true, describe el error|
|data|lista|Lista de diccionarios con los siguientes datos|
|id|int|Id del tipo de busqueda|
|name|String|Nombre del tipo de busqueda|
|price|int|Precio bruto de la busqueda|
|fee|int|Tarifa de la busqueda|


Obtener todos tus queries pasados
---------------------------------

El endpoint para esto es:

      URL: https://panel.validu.co/api/logs_query/                   
      Method: GET   
      Content-Type: application/json

No hay que enviar algun dato. Retorna lo siguiente:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|bool|Si encontró algun error|
|message|string|Si error = true describe el error|
|data|lista|Contiene diccionarios con los siguientes datos|
|id|int|Id del query en el sistema|
|last_name|string|Apellidos del buscado|
|date_query|string|Fecha y hora del query en formato ISO|
|document_number|int|Numero de documento del buscado|
|id_query|int|Id del tipo de query|
|name|string|Nombre del buscado|
|percent|int|Porcentaje de coincidencias en bases de datos|

Obtener un query pasado
-----------------------

El endpoint es el siguiente:

      URL: https://panel.validu.co/api/retrieve_single_logquery/?log_query_id=≤id>                  
      Method: GET   
      Content-Type: application/json

El parametro id debe ser el id del query dentro del sistema (ver /query_sarlaft/)

Los parametros recibidos son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si encontró un error o no|
|message|string|En caso error = true, describe el error|
|data|lista|Contiene un diccionario con los siguientes datos|
|id|int|El id del query en el sistema|
|last_name|string|Los apellidos del buscado|
|date_created|String|La hora en GMT en la que se realizó la busqueda|
|document_number|int|El numero de documento|
|name|string|El nombre del buscado|
|data|Lista|Lista de diccionarios con los siguientes datos|
|codcliente|int|El id de Validu en las bases de datos ajenas|
|porcentaje|int|El porcentaje de coincidencia|
|id_encontrado|int|El numero de cedula proveido|
|nombreencontrado|string|El nombre completo proveido|
|fecha_noticia|string|La fecha de la noticia en la que aparece el buscado, en formato MM-DD-YYYY|
|fuente|string|La fuente de la noticia ej. Prensa|
|hecho|string|El delito acusado|
|dv|string|Dato vacío|
|informacion|string|La base de datos de la coincidencia|
|coincidencia|string|El metodo por el cual se encontró la coincidencia|

Obtener un resumen de tus busquedas en un rango de tiempo
-------------------------------------------------------

El endpoint es el siguiente:

      URL: https://panel.validu.co/api/summary/                  
      Method: POST   
      Content-Type: application/json

Datos por enviar:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|date_start|string|El inicio del rango en formato YYYY-MM-DD|
|date_end|string|El fin del rango en formato YYYY-MM-DD|
|type_query|int|El tipo de resumen por retornar, puede ser cualquier numero en [0,4]|

Para cada valor de type_query retorna un diferente tipo y numero de datos:

Si type_query = 1 muestra un resumen de los gastos diarios y retorna lo siguiente

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si hubo un error|
|message|string|Si error = false, describe el error|
|data|Lista|Lista de diccionarios con los siguientes datos, uno para cada día en el rango|
|spend|int|El total gastado en busquedas ese día|
|total|int|El numero de busquedas ese día|
|date|string|El día de en formato YYYY-MM-DD|

Si type_query = 2 muestra el numero de busquedas por cada tipo de busqueda en el rango de tiempo

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si hubo un error|
|message|string|Si error = false, describe el error|
|data|Lista|Lista de diccionarios con los siguientes datos, uno por cada tipo de busqueda|
|type|string|El nombre del tipo de busqueda|
|total|int|El numero de busqueda|

Si type_query = 3 retorna el numero de busquedas ejecutadas en el rango de tiempo

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si hubo un error|
|message|string|Si error = false, describe el error|
|data|int|El numero de busquedas ejecutadas|

Si type_query = 4 retorna el total gastado en busquedas

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si hubo un error|
|message|string|Si error = false, describe el error|
|data|int|El total gastado en busquedas|

Y si type_query = 0 retorna todos los datos anteriormente descritos en el siguiente formato:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si hubo un error|
|message|string|Si error = false, describe el error|
|data|Lista|Contiene un diccionario con los siguientes datos|
|query_pie|Lista|Lista de diccionarios con los siguientes datos, uno por cada tipo de busqueda|
|type|string|El nombre del tipo de busqueda|
|total|int|El numero de busqueda|
|query_bar|Lista|Lista de diccionarios con los siguientes datos, uno para cada día en el rango|
|spend|int|El total gastado en busquedas ese día|
|total|int|El numero de busquedas ese día|
|date|string|El día de en formato YYYY-MM-DD|
|count_query|int|El numero de busquedas ejecutadas|
|count_balance|int|El total gastado en busquedas|


