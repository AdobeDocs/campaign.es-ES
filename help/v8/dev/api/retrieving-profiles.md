---
title: Recuperación de perfiles
description: Obtenga más información sobre cómo recuperar perfiles con API
role: Developer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
TQID: https://experienceleague.adobe.com/pL6dAoJZ-Qb-aP2BWZKTxsYMTpQEM9EZoU3REWE0OoI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 4%

---

# Recuperación de perfiles con API {#retrieving-profiles}

La recuperación de perfiles se realiza con una solicitud **GET**.

A continuación, puede restringir la búsqueda mediante filtros, pedidos y paginación. Para obtener más información, consulte la sección [Operaciones adicionales](sorting.md).

Además, las API de Campaign Standard le permiten buscar perfiles en función de uno de estos campos: correo electrónico, nombre, apellidos o cualquier campo personalizado. Para obtener más información, consulte [esta sección](#searching-field).

<br/>

***Solicitudes de muestra***

* Solicitud de GET de muestra para recuperar todos los perfiles.

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

* Solicitud de GET de muestra para recuperar los 10 primeros valores de correo electrónico.

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
