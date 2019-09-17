Manejar busquedas
==================

Para realizar una busqueda en bases de datos criminales, se usa el siguiente endpoint:

      URL: https://panel.validu.co/api/query_sarlaft/                   
      Method: POST   
      Content-Type: application/json

Los datos por enviar son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|first_name|string|Los nombres de la persona por buscar|
|last_name|string|Los apellidos de la persona por buscar|
|type_query_id|int|El tipo de busqueda por ejecutar (por ahora solo la estandar(1)|
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
|hecho|String|El delito acusado|
|dv|String|Dato vacío|
|informacion|string|La base de datos de la coincidencia|
|coincidencia|string|El metodo por el cual se encontró la coincidencia|


