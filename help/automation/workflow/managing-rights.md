---
product: campaign
title: Administración de permisos de flujo de trabajo
description: Obtenga información sobre cómo administrar los permisos de flujo de trabajo
feature: Workflows, Permissions
role: Admin
version: Campaign v8, Campaign Classic v7
exl-id: 3cb8aeec-e758-4b71-adef-67942cf9ded7
TQID: 'https://experienceleague.adobe.com/xZwqhzyDbDM309Q-WNpYoD-BvWiJmaTVHsmf50ywAJk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 96%
---
# Administración de permisos de flujo de trabajo{#managing-rights}



Si no son administradores, los operadores de Adobe Campaign necesitan derechos de acceso para crear, ejecutar o modificar los flujos de trabajo.

En términos generales, los operadores que intervienen en los flujos de trabajo necesitan acceder a los archivos que contienen los datos utilizados durante las diversas actividades (destinatarios, lista de destinatarios, suscripciones, envíos, etc.) y, probablemente, a sus subarchivos.

También se deben asignar a los derechos con un nombre que coincida con las acciones realizadas por los flujos de trabajo a los que afectan (importación de destinatarios, acceso a archivos, fusión, ejecución de secuencias de comandos SQL, etc.).

Para obtener más información sobre la administración de operadores y permisos, consulte [esta sección](../../v8/start/gs-permissions.md).

## Grupos de operadores {#operator-groups-wf}

Los siguientes grupos de operadores están asociados al flujo de trabajo:

* El grupo **[!UICONTROL Workflow execution]** permite controlar la ejecución y la aprobación de los flujos de trabajo de objetivo: el derecho denominado “WORKFLOW” se asigna a los operadores de este grupo. Es necesario para todas las acciones relacionadas con los flujos de trabajo, además de los derechos de acceso a los archivos de datos. De forma predeterminada, el grupo **[!UICONTROL Workflow execution]** tiene acceso de solo lectura a los archivos de flujo de trabajo de objetivo estándar y a las plantillas de flujo de trabajo. Los operadores de este grupo también tienen acceso de lectura y escritura al archivo de aprobaciones pendientes.
* El grupo **[!UICONTROL Workflow supervisors]** permite que los operadores administren las aprobaciones de flujo de trabajo.
* El grupo **[!UICONTROL Operation Managers]** permite el acceso a los flujos de trabajo de campaña.

## Derechos asignados {#named-rights}

Solo el derecho denominado “WORKFLOW” es específico de los flujos de trabajo: permite crear, iniciar y detener flujos de trabajo. Se necesitan derechos de lectura en el archivo de flujo de trabajo para que el derecho llamado sea aplicable. Para flujos de trabajo de objetivo, es necesario tener derechos de lectura sobre el archivo **[!UICONTROL Profiles and Targets]**.

## Cuenta de ejecución del flujo de trabajo {#workflow-execution-account}

Puede configurar la cuenta de ejecución para usarla al nivel de plantilla de flujo de trabajo. La cuenta de ejecución permite asignar autorizaciones directamente al flujo de trabajo, independientemente de si el operador de Adobe Campaign inicia la ejecución. De forma predeterminada, cada flujo de trabajo se ejecuta con los derechos del operador que lo inicia.

Para asignar una cuenta de ejecución a un flujo de trabajo, vaya a la lista de plantillas de flujo de trabajo y haga clic con el botón derecho en la plantilla vinculada al flujo de trabajo. Elija **[!UICONTROL Action > Change execution account...]** y después seleccione la cuenta que desee utilizar.
