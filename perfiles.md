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


Obtener todos los empleados de tu misma compañia
------------------------------------------------

El url es el siguiente:

      URL: https://panel.validu.co/api/list_employee/                   
      Method: GET   
      Content-Type: application/json

No hay que enviar datos. Retorna lo siguiente:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
| error      | Bool      | Si se causó algun error   |
|data|Lista|Lista de diccionarios con los siguientes datos|
|id|int|El id dentro del sistema|
|first_name|string|Nombre del empleado|
|phone|int|Numero de telefono|
|employee_status|int|Status del empleado (1 activo, 2 inactivo)|
|rol|int|El rol del empleado (1 admin, 2 usuario)|
|photo|string|Url de su foto de perfil|

Cambiar estado de un perfil
---------------------------

El url es el siguiente:

      URL: https://panel.validu.co/api/change_status/                   
      Method: POST
      Content-Type: application/json

Los valores por enviar son:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|employee_id|int|El id del usuario en el sistema|
|employee_status|int|El estado al que se va a cambiar (1 para activo, 2 para inactivo)|

Los valores retornados:

| Parametro      | Tipo | Descripción     |
| :---        |    :----   |          :--- |
|error|boolean|Si hubo un error|
|message|string|En caso error = true describe el error, sino retorna "ok"|

