---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 29%
---
# CreateRequestByName

Crear una nueva solicitud RGPD utilizando un nombre interno del espacio de nombres

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending )
```

## Parámetros

**namespaceName** Nombre interno del área de nombres

**reconciliationValue** valor de reconciliación

**type** valor de reconciliación

**confirmDeletePending** Solicitud de confirmación antes de eliminar los datos

## Valor(es) devuelto(s)

**id** ID de solicitud recién creada

## Funciones

**Esquema:** [nms:gdprRequest](s-nms-gdprrequest.md)

**Estático:**

Sí
