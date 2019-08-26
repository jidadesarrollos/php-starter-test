# API

## LOGIN
```
https[s]://auth.dev.graphs.social/v3/login
```
METHOD: GET

#### PARAMETROS
Name           | Description                       
:------------- |:----------------------------------
email          | arkos10@emailna.co 
password       | Admin01          
application_id | 5b51eb29303935456453d09a

## LOGOUT
```
https[s]://auth.dev.graphs.social/v4/login/logout
```
METHOD: GET

#### PARAMETROS
Name           | Description                       
:------------- |:----------------------------------
access_token          | access_token obtenido en el metodo login           

## Listado de POSTS
```
https://api.dev.graphs.social/v4/graphs
```

Name           | Description                       
:------------- |:----------------------------------
containers_ids | 5c6f0eff3039354935b3553a
entities_ids   | 14,23,48,49,50,51 // se pasan estos ids separados por coma
limit          | 30 // Numero de registros por pagina
next           | valor _time_updated_ del ultimo registro de la pagina anterior

 
> **Nota**: La api devuelve un objeto con dos valores, "status" y "data"m=, en `data.entries`
se devuelve un objeto cons los _ids_  y el valor  _time_updated_ del item para validar si está
actualizado. `data.data` contiene la información
de cada _entry_  retornado. La información de los posts se encuentra en
el objeto **document** y el valor _time_updated_  tambien se encuentra en cada item del arreglo "data"
 
 Ejemplo:
 ```
"time_updated": 1557951691,
// ....
{
    "status": "ok",
    "data": {
        "entries" : {
               "5cdd5c7e3039352a4e98c508": 1558011006,
               ...
        },
        "data": {
            "5cdd5c7e3039352a4e98c508" : {
                "id": "5cdd5c7e3039352a4e98c508",
                "time_created": 1558011006,
                "time_updated": 1558011006,
                "document": {
                    "description": "Test Notificaciones",
                    "title": "Post de Prueba"
                }
      
            }      
        }
    }
}

```


### Crear Grafo
```angular2html
https://api.[dev.]graphs.social/v4/graphs/
```
METODO: POST
#### PARAMETROS
Name                 |Description                                          
:--------------------|:----------------------------------------------------
access_token         |access_token obtenido en el login del usuario
entity               | post
container_id         | graphId del usuario // 5d0051fc3039353ff68410e8           
title                | Titulo del post a crear
description          | Contenido tipo texto a agregar al post.        

### Modificar un grafo
```angular2html
https://api.[dev.]graphs.social/v4/graphs/[graphId]
```
METODO: PUT
#### PARAMETROS
Name                 |Description                                          
:--------------------|:----------------------------------------------------
access_token         |access_token obtenido en el login del usuario
[CAMPOS A EDITAR] // el id no es editable.

Nota: "graphId" es el id del grafo seleccionado a editar
### Eliminar un grafo
```angular2html
https://api.[dev.]graphs.social/v4/graphs/[graphId]
```
METODO: DELETE
#### PARAMETROS
Name                 |Description                                          
:--------------------|:----------------------------------------------------
access_token         |access_token obtenido en el login del usuario








