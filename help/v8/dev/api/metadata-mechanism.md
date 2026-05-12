---
title: Mecanismo de metadatos
description: Más información sobre el mecanismo de metadatos.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
TQID: https://experienceleague.adobe.com/yi2PDkImYnF-UqGqklMAlvGAIHl9GE47VsCEGj6--yU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 1%

---

# Mecanismo de metadatos {#metadata-mechanism}

Puede recuperar los metadatos de los recursos mediante **resourceType** en una petición GET:

`GET /profileAndServices/resourceType/<resourceName>`

La respuesta devuelve los metadatos principales del recurso (todos los demás campos son descriptivos o internos):

* El nodo **Content** devuelve los campos del recurso. Para cada campo en el nodo **content**, se pueden encontrar los siguientes campos:

   * &quot;apiName&quot;: nombre del atributo utilizado en las API.
   * &quot;tipo&quot;: es la definición de tipo de alto nivel (cadena, número, vínculo, colección, enumeración...).
   * &quot;dataPolicy&quot;: el valor del campo debe seguir las reglas de directiva dadas. Por ejemplo, si la regla dataPolicy se establece en &quot;correo electrónico&quot;, el valor debe ser un correo electrónico válido. Durante un PATCH o un POST, dataPolicy puede comprobar el valor o modificarlo para transformarlo (smartCase por ejemplo).
   * &quot;category&quot;: proporciona la categoría del campo en el editor de consultas.
   * &quot;resType&quot;: es el tipo técnico.

     Si &quot;type&quot; se completa con el valor &quot;link&quot; o &quot;collection&quot;, el valor resTarget es el nombre del recurso al que se dirige el vínculo.
Si &quot;type&quot; se completa con el valor &quot;enumeration&quot;, se agrega un campo &quot;values&quot; y cada valor de enumeración se detalla en el nodo **values**.

* El nodo **Filters** devuelve la URL para recuperar los filtros asociados. Para obtener más información sobre los filtros, consulte [esta sección](sorting.md#filtering).

<!-- créer une section au même niveau sur les liens -->
<!--
dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien
-->
<!-- plus reparler du node Data -->

<br/>

***Solicitud de muestra***

Realice una petición GET en el recurso.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la descripción completa del recurso de perfil.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
