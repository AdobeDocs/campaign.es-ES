---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 53%
---
# extAccount

Definición de cuentas externas (correo electrónico, SMS...) utilizado por los módulos

## Métodos

| Método | Descripción |
| --- | --- |
| [Crear esquema FDAS](sm-extaccount-createfdaschema.md) | Crea el esquema de trabajo en la base de datos |
| [DeclareTableSpaces](sm-extaccount-declaretablespaces.md) | Declara las opciones, necesarias para utilizar tablespaces específicos en la base de datos remota a la que se puede acceder a través de la cuenta externa, en la base de datos Adobe Campaign. |
| [DeploySQLFunctions](sm-extaccount-deploysqlfunctions.md) | Implementa las funciones requeridas por Adobe Campaign acceso de datos federado en el servidor RDBMS remoto |
| [TestAccount](sm-extaccount-testaccount.md) | Realiza una prueba de conexión |

## Métodos genéricos

| Método | Descripción |
| --- | --- |
| [crear](f-create.md) | Crea una nueva entidad correspondiente a un esquema determinado. |
| [cargar](f-load.md) | Carga y devuelve una entidad correspondiente a un esquema y una clave determinados. |
| [guardar](m-entity-save.md) | Guarda una entidad en la base de datos. |
