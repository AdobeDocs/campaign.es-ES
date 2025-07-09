---
title: Control de un flujo de trabajo
description: Obtenga información sobre cómo controlar un flujo de trabajo con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: 4ed5799c77c647c9f1aeabba7645fbb475d03c09
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 11%

---

# Control de un flujo de trabajo {#controlling-a-workflow}

Puede controlar un flujo de trabajo directamente desde la API de REST, a través de una petición POST que contenga el ID de flujo de trabajo y el comando de ejecución requerido:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Si se cambia el ID del flujo de trabajo en Adobe Campaign, la solicitud de API ya no funcionará.

Hay cuatro comandos de ejecución disponibles para controlar un flujo de trabajo:

* Start
* Pause
* Reanudar
* Stop

Para obtener más información sobre los comandos de ejecución, consulte la [documentación de Campaign](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html).

<br/>

***Solicitudes de muestra***

* Iniciar un flujo de trabajo.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'
  ```

  <!-- + réponse -->

* Detener un flujo de trabajo.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"stop"}'
  ```

  <!-- + réponse -->
