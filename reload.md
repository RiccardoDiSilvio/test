Crear un cobru de recarga para la cuenta
========================================
En el caso de Validu, para recargar se crean Cobrus, los cuales una vez pagados se abonan a la cuenta de Validu     
El endpoint es el siguiente:

      URL: https://panel.validu.co/api/reload/                   
      Method: POST
      Content-Type: application/json

Valores por enviar:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|amount|int|El valor del cobru|
|description|string|La descripción de la transacción|

Si el valor es mayor que el minimo necesarío (depende de la cuenta), se crea un cobro.

Retorna lo siguiente.

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si hubo un error|
|data|string|El url del cobru creado|
|message|string|En caso haya un error, describe el error|

Para ver el Cobru creado entras a "prod.cobru.co/elurl".