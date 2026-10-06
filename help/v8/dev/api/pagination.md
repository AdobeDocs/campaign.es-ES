---
title: Paginación
description: Obtenga información sobre cómo realizar operaciones de paginación.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%
---
# Paginación

De forma predeterminada, se cargan 25 recursos en una lista.

El parámetro **_lineCount** le permite limitar el número de recursos enumerados en la respuesta.  A continuación, puede usar el nodo **next** para mostrar los siguientes resultados.

>[!NOTE]
>
>Utilice siempre el valor de URL devuelto en el nodo **next** para realizar una solicitud de paginación.
>
>La solicitud **_lineStart** se ha calculado y siempre debe usarse en la dirección URL devuelta en el nodo **next**.

<br/>

***Solicitud de muestra***

Ejemplo de solicitud GET para mostrar 1 registro del recurso de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Respuesta a la solicitud, con el nodo **next** para realizar la paginación.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

De manera predeterminada, el nodo **next** no está disponible cuando se interactúa con tablas con una gran cantidad de datos. Para poder realizar la paginación, debe agregar el parámetro **_forcePagination=true** a la dirección URL de la llamada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>El número de registros por encima de los cuales una tabla se considera grande se define en la opción **XtkBigTableThreshold** de Campaign Standard. El valor predeterminado es 100 000 registros.
