---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 36%
---
# ExecuteQuery

Recuperar datos de una consulta

```text
XML output = queryDef.ExecuteQuery () const
```

## Parámetros

Ninguna.

## Valor(es) devuelto(s)

Documento XML de salida **output**

## Observaciones

La consulta admite cuatro tipos de operaciones:

* seleccionar
* get
* getIfExists
* count

## Ejemplo

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## Funciones

**Esquema:** [xtk:queryDef](s-xtk-querydef.md)

**Estático:**

No

**Const:**

Sí

**Solo clave:**

No
