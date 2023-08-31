# CORE BANCARIO

- [CORE BANCARIO](#core-bancario)  
  - [Despliegue](#despliegue)  
  - [Métodos expuestos](#metodos)  

## Despliegue  

**Título del Producto:** Tegrity Core 2  
**Nombre:** tegrity-core-2  
**Version:** 1.0.0  
**Security:** apikey  
**URL:** https://tegrity-core.onrender.com  

## Métodos expuestos

### POST /api/clients

Permite crear un cliente.

#### Ejemplo de Request y Response

##### Request
{
    "first_name":"{{$randomFirstName}}",
    "middel_name": "{{$randomFirstName}}",
    "last_name": "{{$randomLastName}}"
}

##### Response
{
    "uuid": {{uuid}}
}


### PATCH /api/clients/{uuid}

Permite modificar los campos del objeto Client que uno quiera.

#### Ejemplo de Request y Response

##### Request
{
    "middle_name": "Morty"
}

##### Response
{
    "tenant": "7365a80b-b1fe-4560-a044-699e33f9554b",
    "first_name": "Thomas",
    "last_name": "Greenfelder",
    "middle_name": "Morty",
    "external_id": null,
    "active": true,
    "activation_date": null,
    "metadata": null,
    "status": "NEW"
}


### GET /api/clients/query

Permite listar todos los clientes.

#### Ejemplo de Request y Response

##### Response
[
    {
        "uuid": "79613581-d0e8-4b39-b7bf-0420a5186578",
        "first_name": "pollo",
        "last_name": "loco",
        "middle_name": null,
        "external_id": null,
        "created_at": "2023-08-02T15:37:13.112332Z",
        "update_at": "2023-08-02T15:37:13.112367Z",
        "active": false,
        "activation_date": null,
        "metadata": null,
        "status": "NEW"
    },
    {
        "uuid": "cf27603b-9f11-446c-9be2-6705f218b5bb",
        "first_name": "Donna",
        "last_name": "Nader",
        "middle_name": null,
        "external_id": "123",
        "created_at": "2023-08-21T18:39:24.043158Z",
        "update_at": "2023-08-21T18:39:24.043191Z",
        "active": false,
        "activation_date": null,
        "metadata": null,
        "status": "NEW"
    }
[


### DELETE /api/clients/{uuid}

Permite borrar un cliente. (por ahora parece que el metodo no esta disponible)

#### Ejemplo de Request y Response

##### Response
{
    "detail": "Method \"DELETE\" not allowed."
}


### GET /api/clients/{uuid}

Permite buscar un cliente por ID.

#### Ejemplo de Request y Response

##### Response
{
    "first_name": "Thomas",
    "last_name": "Greenfelder",
    "middle_name": null,
    "external_id": null,
    "active": true,
    "activation_date": null,
    "metadata": null,
    "status": "NEW"
}


### POST /api/clients/identifier

Permite definir un tipo de identificador, ej DNI.

#### Ejemplo de Request y Response

##### Request
{
    "client": "9d217374-b4f4-4acb-9f9d-98df0a3a0823",
    "identifier_type":"DNI",
    "identifier_key":"39371777",
    "description": "",
    "metadata": {"hola":"universo"}
}

##### Response (no consegui un 200OK, solo este 404)
{
    "detail": "identifier name not found"
}

