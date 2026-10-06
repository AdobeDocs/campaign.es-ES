---
product: campaign
title: Prueba
description: Descubra más información sobre la actividad del flujo de trabajo Prueba
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
TQID: 'https://experienceleague.adobe.com/dXkGOQ-OD-KUwWx29DcE7FqYzbDSF-M6ox8-8cTurjA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 100%
---
# Prueba{#test}



Una actividad de tipo **Prueba** activa la primera transición que cumple la condición asociada a esta. Si no se cumple ninguna condición y si la opción **[!UICONTROL Use the default fork]** está activada, se activa la transición predeterminada.

Una condición es una expresión JavaScript que debe evaluarse como “verdadera” o “falsa”. Para introducir la expresión, haga clic en el icono a la derecha del nombre de la condición y, a continuación, seleccione **[!UICONTROL Edit...]**.

![](assets/edit_test.png)

Para obtener más información sobre todas las funciones adicionales de JavaScript y los métodos SOAP del servidor aplicativo accesible mediante JavaScript de flujo de trabajo, consulte la [Documentación de JSAPI](https://experienceleague.adobe.com/es/tools/campaign-api){target="_blank"}.

También puede insertar variables directamente desde este editor. Para obtener más información sobre cómo trabajar con variables, consulte [esta sección](javascript-scripts-and-templates.md#variables).

Se pueden añadir, eliminar u ordenar las condiciones desde la ventana de edición de la propiedad actividad, pero también se puede modificar desde la transición.

Si el resultado de un cálculo se reutiliza en condiciones diferentes, es posible calcularlo en el guion de inicialización de la actividad. El resultado debe almacenarse en una variable de la tarea a la que deben acceder los scripts de condición (task.vars.xxx).
