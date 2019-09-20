Obtener balance
================

Para obtener tu balance se usa el siguiente url 
      
      URL: https://panel.validu.co/api/balance/                   
      Method: GET   
      Content-Type: application/json
   
No hay que enviar algun dato. Retorna lo siguiente:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si ocurrió algun error|
|message|string|En caso error = true, describe el error|
|balance|int|El balance de usuario|