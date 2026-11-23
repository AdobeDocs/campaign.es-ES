---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%
---
# InstallPackage

Instale un paquete.

```text
InstallPackage ( XML parameters )
```

## Parámetros

**parameters** elemento XML que contiene el paquete que se va a importar.

## Valor(es) devuelto(s)

Ninguna.

## Observaciones

Un paquete generado por el método SpecFile.Generate() debe encapsularse en un elemento de generador. Ejemplo:

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## Funciones

**Esquema:** [xtk:builder](s-xtk-builder.md)

**Estático:**

Sí
