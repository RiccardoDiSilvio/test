Manejar perfiles
===================

Obtener un perfil
-----------------

Se usa el siguiente endpoint:
      URL: https://panel.validu.co/api/profile/                   
      Method: GET   
      Content-Type: application/json

Los valores por enviar son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
| employee_id     | int       | El id del usuario por obtener  |

En caso no se envie el parametro, se obtiene el perfil de usuario que está haciendo la llamada a la API

Una vez hecha la llamada, devuelve lo siguiente:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
| error      | Bool      | Si se causó algun error   |
| data   |   Lista   |  La información del usuario, los campos dependen de si se retorna otro usuario o el mismo que opera  |
| Usuario propio| | |
|permissions| lista| Lista de permisos dentro de la api|
|name|string|El nombre real del usuario|
|Minimum reload|int|El monto minimo que debe recargar un usuario en caso recargue (-1 si no tiene minimo)|
|Company|string|La compañia para quien trabaja|
|status|int|Indica el estado del empleado (1 activo, 2 inactivo)|
|username|string|El usuario dentro del sistema|
|balance|int|El balance del usuario|
|Otro usuario|No contiene permissions, balance, company y status| |
|type_document_id|int|Tipo de documento|
|document_number|int|Numero de documento|
|email|String|Correo electronico|
|phone|int|Numero de telefono|
|roles_id|int|El id del rol dentro del sistema|


