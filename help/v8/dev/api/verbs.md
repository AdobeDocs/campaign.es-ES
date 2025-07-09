---
title: GET / POST / PATCH / DELETE verbos
description: Obtenga más información acerca de los verbos utilizados en las API de Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: de97a194-d497-4665-906e-53178fd3b119
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---

# GET / POST / PATCH / DELETE verbos {#verbs}

Los verbos disponibles para realizar operaciones en los recursos son:

* `GET`: recupera un elemento o una colección de elementos
* `POST`: crea un recurso con parámetros.
* `PATCH`: actualiza un recurso con parámetros.
* `DELETE`: elimina un recurso.

<!-- ajouter codes retour -->

<br/>

***Solicitudes de muestra***

* Solicitud GET de ejemplo en la colección de perfiles.


  ```
  $curl  
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Devuelve una matriz de perfiles.


  ```
  {
      "content": [
          {
              "PKey": "<PKEY>",
              "firstName": "Olivia",
              "lastName": "Varney",
              "birthDate": "1977-09-°4",
              "email": "o.varney@mail.com",
          },
          {
              "PKey": "<PKEY>",
              "firstName": "John",
              "lastName": "Doe",
              "birthDate": "1985-08-17",
              "email": "johndoe@mail.com",
          }
      ],
  }
  ```

* Solicitud de GET de ejemplo en un perfil específico.


  ```
  $curl  
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Devuelve el perfil solicitado.


  ```
  {
      "PKey": "<PKEY>",
      "firstName": "John",
      "lastName": "Doe",
      "birthDate": "1985-08-17",
      "email": "johndoe@mail.com",
      ...
  }
  ```

* Ejemplo de solicitud POST para crear un perfil.


  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -d '{"lastName":"Doe"}'
  ```

  Devuelve el perfil con los campos predeterminados.

  ```
  {
      "PKey": "<PKEY>",
      "firstName": "John",
      "lastName": "Doe",
      "birthDate": "1985-08-17",
      "email": "johndoe@mail.com",
  }
  ```

* Solicitud de PATCH de ejemplo para actualizar un perfil.

  ```
  -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -d '{"firstName":"Mark"',"lastName":"Smith"}'
  ```

  Devuelve la PKEY y la URL para recuperar el perfil actualizado.

  ```
  {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>"
  }
  ```

* Ejemplo de solicitud de DELETE para eliminar un perfil.

  ```
  -X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  La solicitud devuelve una respuesta 200, que confirma que el perfil se ha eliminado.
