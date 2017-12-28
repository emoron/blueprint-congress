HOST: http://emoron.ddns.net/api

--- Amiutem API v1 ---
---
Aplicacion amiutem para registro de asistentes a congreso
---

--
Asistentes
La siguiente seccion esta relacionada a los recursos de asistentes
--
Lista los usuarios registrados en el sistema
GET /api/asistentes
< 200
< Content-Type: application/json
[{"folio_id":40,"nombreCompleto":"LEONEL SALVADOR LERMA ROJAS","email":"llerma@itdurango.edu.mx","universidad":"Instituto Tecnológico de Durango","direccion":"Blvd. Felipe Pescador 1830 Ote. Colonia Nueva Vizcaya","estado":10,"paymentType":"estudiante","ciudad":"Durango","facturacion":".."}]


Recibe asistente desde el registro principal
GET /admin/asistentes/edit/[:id]
< 200
< Content-Type: application/json
{"folio_id  : 32,
           "nombreCompleto"  : "edgard",
           "universidad"    : "Instituto Tecnológico de Durango",
           "direccion"      : "Blvd. Felipe Pescador 1830 Ote. Colonia Nueva Vizcaya",
           "codigo"   	: "34553",
           "estado"  : "Mexico DF",
           "telefono"   : "4455443453",
           "paymentType"    : "student",
           "ciudad"     : "Ciudad de Mexico",
           "facturacion": "TRUE"
}


Almacenar usuarios que provienen del registro principal


Almacena usuarios en la DataBase
POST /asistentes/save
> Content-Type: application/json
{ "product":"1AB23ORM", "quantity": 2 }
< 201
< Content-Type: application/json
{ "status": "created", "url": "/shopping-cart/2" }


-- Ponencias --
Estos recursos se relacionan a ponencias 
GET /ponencias
< 200
< Content-Type: application/json
[
    {
        "idPonencia": 11,
        "titulo": "PROCESO INDUCTIVO-DEDUCTIVO DE ENSEÑANZA-APRENDIZAJE DEL ANÁLISIS COMBINATORIO O TÉCNICAS DE CONTAR",
        "nombreCompleto": "LEONEL SALVADOR  LERMA ROJAS, MARA ALEJANDRA LERMA GARCÍA, PEDRO LUIS LERMA GARCÍA"
    }
]

-- Usuarios --
Relacionada con los usuarios que se registran por primera vez
POST /usuarios/sendmail
< 200
< Content-Type: application/json


-- Almacena usuarios --
POST /usuarios/save
> Content-Type: application/json
{ "product":"1AB23ORM", "quantity": 2 }
< 201
< Content-Type: text/plain
"true"


-- Usuarios Existentes --
Verifique quee un usuario no existe en la base de datos
GET /usuarios/verify[/questions]
< 200
< Content-Type: text/plain
"false"


-- Revisa el correo existente en la DBN --
Regresa *true* si el usuario existe en el sistema de lo contrario *false*
GET /usuarios/check[/email]
< 200
< Content-Type: text/plain
"true"
"false"

--
Clientes
La siguiente seccion esta relacionada a los recursos de asistentes
--
