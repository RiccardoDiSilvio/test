Obtener lista de bancos
=======================

El endpoint es el siguiente:

      URL: https://panel.validu.co/api/list_bank_cobru/                   
      Method: GET   
      Content-Type: application/json

No hay que enviar datos. Retorna lo siguiente:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|bool|Si encontró un error|
|message|string|En caso haya encontrado un error describe el error|
|data|lista|Lista de diccionarios con los siguientes datos|
|bankName|string|Nombre del banco|
|bankCode|int|Codígo del banco|