---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 6%
---
# Aplicación (clase)

Esta clase tiene una sola instancia que proporciona acceso a determinadas propiedades del servidor aplicativo. Se puede acceder a este singleton a través de la variable global `application`.

## Métodos

| Método | Descripción |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | Comprueba si hay un paquete instalado. |
| [getSchema](m-application-getschema.md) | Devuelve una asignación a un esquema de Adobe Campaign o nulo si el esquema no existe. |
| [getDBMSType](m-application-getdbmstype.md) | Devuelve el tipo de servidor de la base de datos. |
| [getNewIds](m-application-getnewids.md) | Devuelve una lista de los ID de las claves internas de la base de datos. |
| [getConnection](m-application-getconnection.md) | Devuelve una nueva conexión al servidor de base de datos. |
| [getTimezoneJson](m-application-gettimezonejson.md) | Devuelve una cadena de caracteres que es la representación JSON de la lista de diferencias horarias con la hora UTC y su fecha de inicio en comparación con el periodo UNIX de una zona horaria. |
| [onLog](m-application-onlog.md) | Agrega o elimina una función de interceptación para los mensajes escritos en el historial |
| [onTrace](m-application-ontrace.md) | Agrega o elimina una función de interceptación de mensajes de seguimiento. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | Devuelve el número de compilación del servidor aplicativo. |
| [instanceName](p-application-instancename.md) | Nombre de la instancia en la que se ejecuta el script. |
| [instanceVarDir](p-application-instancevardir.md) | Ruta de acceso completa del directorio &quot;var&quot; para la instancia en la que se ejecuta el script. |
| [instanceUploadDir](p-application-instanceuploaddir.md) | Ruta de acceso completa del directorio &quot;cargar&quot; para la instancia en la que se ejecuta el script. |
| [operador](p-application-operator.md) | Devuelve un objeto que contiene información sobre el operador actual (nombre, identificadores, derechos, etc.). |
| [configuración regional](p-application-locale.md) | Devuelve una cadena de caracteres que coincide con la instancia Local. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
