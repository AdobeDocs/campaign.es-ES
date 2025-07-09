---
title: Operaciones adicionales
description: Obtenga más información sobre cómo realizar operaciones adicionales
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 1%

---

# Operaciones adicionales {#additional-operations}

## Orden {#sorting}

La ordenación está disponible de forma predeterminada en orden ascendente. Para ordenar en orden descendente, agregue **%20desc** al valor del parámetro **_order**.

Para saber si un campo se puede ordenar, compruebe el parámetro &quot;ordenable&quot; en los metadatos del recurso. Para obtener más información, consulte [esta sección](metadata-mechanism.md).

<br/>

***Solicitudes de muestra***

* Solicitud de GET de ejemplo para recuperar correos electrónicos en la base de datos ordenados alfabéticamente.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Respuesta a la solicitud.

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* Solicitud GET de ejemplo para recuperar el correo electrónico en la base de datos en orden alfa descendente.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Respuesta a la solicitud.

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```

## Filtrado {#filtering}

### Recuperando metadatos de filtros

Los filtros están disponibles para cada recurso. Para identificar los filtros asociados a un recurso, debe realizar una petición GET en los metadatos del recurso. Esta solicitud devuelve la dirección URL donde se definen todos los filtros para un recurso determinado. Para obtener más información sobre metadatos, consulte [esta sección](metadata-mechanism.md).

Para identificar los metadatos de un filtro y determinar cómo utilizarlos, se debe realizar una petición GET en la dirección URL devuelta anteriormente.

<br/>

***Solicitud de muestra***

Las siguientes cargas útiles de ejemplo muestran cómo recuperar los metadatos de filtro &quot;byText&quot; para el recurso de &quot;perfil&quot;. Primero realice una solicitud GET en la métrica de recursos &quot;perfil&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la dirección URL donde se describen los filtros.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

Realice una petición GET en la dirección URL. Devuelve la lista de filtros para el recurso de perfil, con los metadatos asociados a cada filtro.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

### Estructura de metadatos de filtros

La misma estructura de metadatos está disponible para cada filtro:

* Los campos **@formType** y **@webPage** son campos técnicos.
* El campo **data** proporciona un ejemplo sobre cómo usar el filtro.
* El nodo **metadata** describe los parámetros del filtro.
* El nodo **condition** describe lo que el filtro pretende hacer. Los parámetros de filtro descritos en el nodo de metadatos se utilizan para crear condiciones de filtro. Para cada condición de filtro, si **enabledIf** es true, se aplicará **expr**.

<br/>

Ejemplo de estructura de metadatos de filtro:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

### Uso de filtros

El filtrado se realiza con la siguiente solicitud:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

Es posible combinar varios filtros en una sola solicitud:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***Solicitudes de muestra***

* Solicitud de GET de ejemplo para recuperar los recursos del &quot;servicio&quot; con el tipo &quot;correo electrónico&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
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
              "created": "2019-09-25 23:20:35.000Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
              "label": "Marketing Newsletter",
              "lastModified": "2019-09-25 23:20:35.000Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              ...
          },
          ...
      ],
      ...
  }
  ```

* Solicitud de GET de muestra para recuperar los recursos de &quot;perfil&quot; que contienen &quot;Listo&quot; en
los campos correo electrónico o apellidos (el filtro por texto busca en los campos correo electrónico y apellidos).

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
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
          }
          ...
      ],
      ...
  }
  ```

* Solicitud de GET de ejemplo para recuperar los recursos de servicios con el tipo &quot;correo electrónico&quot; y la etiqueta &quot;deporte&quot;.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
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
              "created": "2019-09-26 09:36:01.014Z",
              "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
              "label": "sport",
              "lastModified": "2019-09-26 09:36:01.014Z",
              "limitedDuration": false,
              "messageType": "email",
              "mode": "newsletter",
              "name": "SVC13",
              ...
          }
      ],
      ...
  }
  ```

### Filtros personalizados

Si desea utilizar un filtro personalizado, debe crearlo y personalizarlo en la interfaz de Adobe Campaign Standard. El filtro personalizado tendrá el mismo comportamiento que los filtros predeterminados:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Para obtener más información, consulte la documentación de Campaign Standard:

* [Configurando definición de filtro](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [Caso de uso: invocando a un recurso mediante una clave de identificación compuesta](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html).

<br/>

***Solicitud de muestra***

Solicitud de GET de muestra para recuperar los recursos de &quot;perfil&quot; con importes de transacción de 100 $ o más. Tenga en cuenta que el filtro &quot;byAmount&quot; se ha definido primero en la interfaz de Adobe Campaign Standard y se ha vinculado a la tabla personalizada &quot;Transaction&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->

## Recuento {#counting}

La API de REST de Adobe Campaign puede contar el número de registros de una solicitud. Para ello, utilice la dirección URL que se devuelve en el nodo **count**.

<br/>

***Solicitud de muestra***

Para contar todos los servicios que tienen un valor **messageType** igual a &quot;sms&quot;, realice una petición GET con el filtro **byChannel**.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=sms \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve los servicios correspondientes al filtro.

```
{
    "content": [
        {
            ...
            "messageType": "sms",
            "mode": "newsletter",
            "name": "SVC6",
            ...
        },
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy"
    },
    "serverSidePagination": true
}
```

Realice una petición GET en la dirección URL del nodo **count** para recuperar el número de resultados.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve el número de registros.

```
{
    "count": 26
}
```

## Paginación {#pagination}

De forma predeterminada, se cargan 25 recursos en una lista.

El parámetro **_lineCount** le permite limitar el número de recursos enumerados en la respuesta.  A continuación, puede usar el nodo **next** para mostrar los siguientes resultados.

>[!NOTE]
>
>Utilice siempre el valor de URL devuelto en el nodo **next** para realizar una solicitud de paginación.
>
>La solicitud **_lineStart** se ha calculado y siempre debe usarse en la dirección URL devuelta en el nodo **next**.

<br/>

***Solicitud de muestra***

Solicitud de GET de ejemplo para mostrar 1 registro del recurso de perfil.

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
