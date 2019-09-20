# Autorización en la API

Para tomar cualquier acción en la API, se debe primero pasar por el endpoint de autorización.                         
El endpoint para este proposito es el siguiente:

      URL: https://panel.validu.co/token/ ##La parte de https es necesaria                    
      Method: POST      
      Content-Type: application/json ##Todos los endpoints requieren de JSON en texto

Los valores por enviar son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
| username     | String       | El usuario proveído  |
| password   |   String      |   La password del mismo    |

Una vez hecha la llamada, devuelve lo siguiente:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
| access      | String      | El token de acceso   |
| refresh   |     String    |     Token de refresco, usado para reiniciar el de acceso una vez que se venza  |

El access token se vence después de 15 minutos. Para refrescarlo hay que usar el siguiente endpoint.

      URL: https://panel.validu.co/token/refresh/                   
      Method: POST      
      Content-Type: application/json 

Se envia: 

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
| refresh   |     String    |     Token de refresco, usado para reiniciar el de acceso una vez que se venza  |

Una vez hecha se envía un nuevo access token.
Los parametros retornados son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
| access   |     String    |  El nuevo access token (valido por 15 minutos) |

Para hacer llamadas a cualquier otro endpoint necesitas usar los siguientes headers:

      {
         "x-api-key": "la api key proveida por validu",
         "Authorization": "El access token obtenido por /token/ o /token/refresh/"
      }