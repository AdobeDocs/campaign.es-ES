---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%
---
# Esquema (clase)

Representa la definición del esquema.

Se obtiene un esquema llamando al método de la variable global `application`. Una instancia de este objeto tiene un objeto como prototipo y, por lo tanto, hereda sus métodos.

## Métodos

| Método | Descripción |
| --- | --- |
| [toDocument](m-schema-todocument.md) | Convierte el esquema en un documento XML. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [enumeraciones](p-schema-enumerations.md) | Devuelve la tabla que contiene la lista de [enumeraciones](c-enumeration.md) definidas en este esquema. |
| [id](p-schema-id.md) | El identificador de esquema en forma de cadena. |
| [isLibrary](p-schema-islibrary.md) | Devuelve un valor booleano que especifica si el esquema es una biblioteca de componentes. |
| [labelSingular](p-schema-labelsingular.md) | El nombre singular del esquema en forma de cadena. |
| [mappingType](p-schema-mappingtype.md) | Naturaleza de la asignación de esquemas en forma de cadena |
| [md5](p-schema-md5.md) | El código MD5 del esquema en forma de cadena hexadecimal. |
| [espacio de nombres](p-schema-namespace.md) | Área de nombres del esquema en forma de cadena. |
| [raíz](p-schema-root.md) | Elemento principal del esquema o nulo si no está definido. |
| [userDescription](p-schema-userdescription.md) | La descripción del esquema en forma de cadena. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
