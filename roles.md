Listar roles
============

El endpoint es el siguiente:

      URL: https://panel.validu.co/api/roles/                   
      Method: POST      
      Content-Type: application/json

Retorna una lista de diccionarios con los siguientes datos:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|id|int|El id del rol en el sistema|
|name|string|El nombre del rol (Ej. admin, empleado)|