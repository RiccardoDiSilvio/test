Obtener compañias
==================

Para obtener un listado de todas las compañias se llama el siguiente endpoint:

      URL: https://panel.validu.co/api/company/                   
      Method: GET   
      Content-Type: application/json


No se necesita enviar algun dato y retorna una lista de diccionarios cada uno con los siguientes datos:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|id|int|Id de la compañia en el database|
|photo|string|Url de la foto de perfil de la compañia|
|status|int|Indica el estado de la compañia (1 activa, 2 inactiva)|