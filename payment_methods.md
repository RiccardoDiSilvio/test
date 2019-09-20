Listar metodos de pago
========================

El endpoint es el siguiente

      URL: https://panel.validu.co/api/list_payment_methods/                   
      Method: GET   
      Content-Type: application/json

No hay que enviar algun dato. Retorna una lista de diccionarios con los siguientes datos:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|id|int|Id del metodo dentro del sistema|
|name|string|Nombre del metodo|
|photo|string|Url de la foto del icono usada en el sitio web|
