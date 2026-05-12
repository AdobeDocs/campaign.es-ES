---
title: Eliminación de suscripciones
description: Obtenga información sobre cómo eliminar suscripciones con API
role: Developer
level: Experienced
exl-id: 76e2d102-c877-41a6-af87-2f407201a572
TQID: https://experienceleague.adobe.com/tn-B0YAO0bD1dtW3-ovb-xWtupiRaqFD1TMW8Rzu5aY
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
source-wordcount: 239
ht-degree: 0%

---

# Eliminación de suscripciones con API {#mdeleting-subscriptions-api}

<!--NOTE TO WRITER: There are two duplicate headings that seem to have the same content. Delete one? Rename if different?-->

## Eliminación de una suscripción de servicio para un perfil específico {#deleting-service-subscription}

Este es un procedimiento de tres pasos.

1. Recupere la URL de suscripciones para el perfil deseado.
1. Realice una petición GET en la dirección URL de suscripciones.
1. Realice una petición DELETE en la dirección URL de servicio deseada.

Si la solicitud de eliminación se realiza correctamente, el estado de respuesta es 204 Sin contenido.

<br/>

***Solicitud de muestra***

Las cargas útiles de ejemplo siguientes muestran cómo cancelar la suscripción de un perfil a un servicio. En primer lugar, realice una petición GET para recuperar el perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la URL de suscripciones del perfil.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
  }
```

Realice una petición GET en la dirección URL de suscripciones.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la lista de suscripciones del perfil seleccionado, con una URL para cada servicio suscrito.

```
...
"service": {
  "PKey": "<PKEY>",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
  "label": "Sport Newsletter",
  "name": "SVC1",
  "title": "Sport Newsletter (SVC1)"
},
...
```

Realice una petición DELETE en la dirección URL de servicio deseada.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->

## Eliminación de una suscripción de servicio para un perfil específico

Este es un procedimiento de tres pasos.

1. Recupere el servicio deseado y su URL de suscripción.
1. Realice una petición GET en la URL de suscripciones para recuperar todos los perfiles y suscripciones.
1. Realice una petición DELETE en la URL de suscripción de perfil que desee.

Si la solicitud de eliminación se realiza correctamente, el estado de respuesta es 204 Sin contenido.

<br/>

***Solicitud de muestra***

Recupere el registro de servicio.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la URL de suscripciones del servicio.

```
{
  ...
  "messageType": "email",
  "mode": "newsletter",
  "name": "SVC3",
  "subScenarioEventType": "subscriptionEvent",
  "subscriptions": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
  },
  "targetResource": "profile",
  ...
},
```

Realice una petición GET en la dirección URL de suscripciones.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la lista de suscripciones del servicio seleccionado, con una URL (href) para cada suscripción de perfil.

```
{
  "PKey": "<PKEY>",
  "created": "2019-03-26 08:58:04.764Z",
  "email": "",
  "expirationDate": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY>",
  "metadata": "subscriptionRcp",
  "service": ...,
  "serviceName": "SVC3",
  "subscriber": ...,
  ...
}
```

Realice una petición DELETE en la URL de suscripción de perfil que desee.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->
