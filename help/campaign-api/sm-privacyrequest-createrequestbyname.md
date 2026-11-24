---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 6%
---
# CreateRequestByName

Crear una nueva solicitud de privacidad con un nombre interno del área de nombres

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## Parámetros

**namespaceName** Nombre interno del área de nombres

**reconciliationValue** valor de reconciliación

**type** valor de reconciliación

**confirmDeletePending** Solicitud de confirmación antes de eliminar los datos

**regulación** tipo de regulación con los siguientes valores:

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## Valor(es) devuelto(s)

**id** ID de solicitud recién creada

## Funciones

**Esquema:** [nms:privacyRequest](s-nms-privacyrequest.md)

**Estático:**

Sí
