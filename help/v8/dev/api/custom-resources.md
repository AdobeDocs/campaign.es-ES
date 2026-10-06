---
title: Recursos personalizados
description: Obtenga más información sobre la administración de recursos personalizados con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
TQID: 'https://experienceleague.adobe.com/T-CLyTlNyyuckhraPX-rAU7TOrMfMbcZdrDcneiflg0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 2%
---
# Recursos personalizados {#custom-resources}

Adobe Campaign viene con un modelo de datos predefinido, donde los datos se definen a través de diferentes recursos. Puede enriquecer el modelo de datos que se proporciona ampliando los recursos para agregar sus propios campos o tablas personalizadas, como las tablas de compras o de productos.

Se puede acceder a los recursos personalizados mediante las API que usan el extremo **/profileAndServicesExt** y el nombre del recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para los recursos que no están listos para usarse, utilice siempre el prefijo <b>&quot;cus&quot;</b> antes del nombre del recurso.

Puede realizar cualquier operación con recursos personalizados, siempre y cuando estén vinculados a la tabla Perfil. Por ejemplo, veamos la estructura de las tablas a continuación:

![texto alternativo](assets/cusresources.png)

En ese caso, todos los recursos de las tablas **Transaction**, **TransactionDetails** y **Product** están disponibles siempre que estén vinculados a la tabla **Profile**.

<br/>

***Solicitud de muestra***

Ejemplo de solicitud GET para acceder al recurso profileAndServicesExt ampliado.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Devuelve la lista de todos los recursos personalizados vinculados. A continuación, puede utilizar las direcciones URL de los recursos para realizar cualquier tarea de la API descrita en esta documentación.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```
