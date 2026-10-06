---
title: Recuperación de perfiles
description: Obtenga más información sobre cómo recuperar perfiles con API
role: Developer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
TQID: 'https://experienceleague.adobe.com/pL6dAoJZ-Qb-aP2BWZKTxsYMTpQEM9EZoU3REWE0OoI'
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
source-wordcount: '234'
ht-degree: 4%
---
# Recuperación de perfiles con API {#retrieving-profiles}

La recuperación de perfiles se realiza con una solicitud **GET**.

A continuación, puede restringir la búsqueda mediante filtros, pedidos y paginación. Para obtener más información, consulte la sección [Operaciones adicionales](sorting.md).

Además, las API de Campaign Standard le permiten buscar perfiles en función de uno de estos campos: correo electrónico, nombre, apellidos o cualquier campo personalizado. Para obtener más información, consulte [esta sección](#searching-field).

<br/>

***Solicitudes de muestra***

* Ejemplo de petición GET para recuperar todos los perfiles.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
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
              "firstName": "John",
              "lastName":"Doe",
              "birthDate": "1980-10-24",
              ...
          },
          ...
  }
  ```

* Ejemplo de petición GET para recuperar los primeros 10 valores de correo electrónico.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Respuesta a la solicitud. El nodo &quot;siguiente&quot; devuelve la dirección URL que le permite acceder a los 10 valores de correo electrónico siguientes.

  ```
  {
  "content": [
      "amy.dakota@mail.com",
      "kristen.smith@mail.com",
      "omalley@mail.com",
      "xander.harrys@mail.com",
      "jane.summer@mail.com",
      "gloria.boston@mail.com",
      "edward.snow@mail.com",
      "dorian.simons@mail.com",
      "peter.paolini@mail.com",
      "mingam+test08@adobe.com"
  ],
  "next": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
      lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
  }
  }
  ```

## Búsqueda de perfiles basados en un campo {#searching-field}

El parámetro **[!UICONTROL filterType]** le permite recuperar perfiles basados en uno de estos campos: correo electrónico, nombre, apellidos o cualquier campo personalizado que se haya agregado en el filtrado avanzado al ampliar el recurso de perfil.

>[!NOTE]
>
>Las búsquedas distinguen entre mayúsculas y minúsculas y solo se realizan en prefijos. Por ejemplo, no podrá buscar un perfil con las últimas letras de su apellido.

***Solicitudes de muestra***

* Solicitud de muestra para filtrar perfiles sobre la base del nombre.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Solicitud de muestra para filtrar perfiles según el apellido.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Solicitud de muestra para filtrar perfiles según el correo electrónico.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

* Solicitud de muestra para filtrar perfiles en función del campo personalizado &quot;Afición&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```
