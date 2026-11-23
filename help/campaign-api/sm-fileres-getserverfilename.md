---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 51%
---
# GetServerFileName

Devuelve el nombre del archivo en el servidor después de copiarlo, si es necesario, en la carpeta de carga.

```text
String serverFileName = fileRes.GetServerFileName ()
```

## Parámetros

Ninguna.

## Valor(es) devuelto(s)

**serverFileName** Nombre completo del archivo en el servidor (vacío si no se encuentra el archivo).

## Ejemplo

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## Funciones

**Esquema:** [xtk:fileRes](s-xtk-fileres.md)

**Estático:**

No

**Const:**

No

**Solo clave:**

No
