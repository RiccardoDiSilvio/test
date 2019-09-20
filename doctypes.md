Obtener los tipos de documento validos
======================================

El url es el siguiente:

      URL: https://panel.validu.co/api/type_document/                  
      Method: GET   
      Content-Type: application/json

No hay que enviar datos. Retorna una lista de diccionarios con los siguientes valores:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|id|int|El id del tipo de documento en el sistema|
|name|string|El nombre del tipo de documento|