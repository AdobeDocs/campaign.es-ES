---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# getEnv

>[!WARNING]
>
>Esta función está disponible para un entorno local.

>[!NOTE]
>
>Puede deshabilitar esta función pasando la opción **XtkSecurity\_Disable\_GetSetEnv** a **true**.

Devuelve el valor de una variable de entorno.

```text
getEnv (name [, default ])
```

## Parámetros

**nombre** Nombre de la variable.

**valor predeterminado** que se usará si no se encuentra la variable de entorno.

## Valor devuelto

El valor de la variable.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Envío del mensaje
* Regla de tipología
* Importación
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
