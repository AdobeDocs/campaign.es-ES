---
title: Actualización de perfiles
description: Obtenga más información sobre cómo actualizar perfiles con API
role: Developer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
TQID: 'https://experienceleague.adobe.com/GJc7tW2XdnidUrVaLIpHl3pdHmE4dNLzhtVoUazhuPQ'
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
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%
---
# Actualización de perfiles con API{#updating-profiles-api}

La actualización de perfiles se realiza con una solicitud **PATCH**.

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. El primer paso es **recuperar el perfil**.

1. En una segunda solicitud, realice una **solicitud PATCH** en el perfil con la información completada en la carga.

1. Para comprobar si la solicitud de PATCH ha actualizado el perfil, podemos realizar una solicitud GET final.

<br/>

***Solicitud de muestra***

Ejemplo de petición GET para recuperar un perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Respuesta a la solicitud.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

Solicitud de PATCH para actualizar el atributo &quot;phone&quot;.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

Devuelve la PKEY y la URL para recuperar el perfil actualizado.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
