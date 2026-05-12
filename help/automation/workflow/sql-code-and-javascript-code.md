---
product: campaign
title: Código SQL y código JavaScript
description: Descubra más información sobre las actividades del flujo de trabajo de código SQL y JavaScript
feature: Workflows
Role: User
level: Experienced
version: Campaign v8, Campaign Classic v7
exl-id: 8c385847-a320-4cd9-9048-2bf9daf2ee07
TQID: https://experienceleague.adobe.com/J1oZUE7vCyJvodf0-09QoG24gWY9P9sSgqsH7rXibgk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 68%

---

# Código SQL y código JavaScript{#sql-code-and-javascript-code}

## Código SQL {#sql-code}

Una actividad de **[!UICONTROL SQL code]** ejecuta una secuencia de comandos SQL. La secuencia de comandos es una plantilla JST.

![](assets/sql_code.png)

* **[!UICONTROL Script]**

  El área central del editor contiene la secuencia de comandos que se va a ejecutar. Esta secuencia de comandos es una plantilla JST y, por lo tanto, se puede configurar según el contexto del flujo de trabajo.

* **[!UICONTROL Processing errors]**

  Consulte [Errores de procesamiento](monitor-workflow-execution.md#processing-errors).

### Notas importantes {#important-notes}

A partir de la versión 8.9.1, las actividades de flujo de trabajo **[!UICONTROL SQL code]** y **[!UICONTROL SQL Data Management]** se han mejorado para proteger mejor las bases de datos PostgreSQL y mantener los flujos de trabajo funcionando sin problemas cuando se ejecuta SQL personalizado desde Campaign. Estas son algunas prácticas recomendadas que debe seguir en caso de errores.

Las opciones están disponibles en **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. Hay dos soluciones disponibles en caso de errores:

**Solución 1**

Establezca `XtkSecurity_FeatureFlag_SqlSensitive` en `0`. La función está desactivada.

**Solución 2**

Modificar `XtkSecurity_SqlSensitive_Methods`. Puede cambiar `<method name="TRUNCATE" action="block"/>` a `<method name="TRUNCATE" action="warn"/>`

Otros métodos como VACUUM FULL, REINDEX, CREATE INDEX, DROP INDEX también están bloqueados de forma predeterminada para proteger la integridad de la base de datos. Tenga cuidado si desea configurarlos para que adviertan en lugar de bloquear. Estos métodos pueden tener un impacto grave en el rendimiento de la base de datos al ejecutarse.

## Código JavaScript y código JavaScript avanzado {#javascript-code}

Las actividades **[!UICONTROL JavaScript code]** y **[!UICONTROL Advanced JavaScript code]** ejecutan un script JavaScript en el contexto de un flujo de trabajo. Para obtener más información sobre los scripts, consulte estas secciones:

* [Plantillas y scripts de JavaScript](javascript-scripts-and-templates.md)
* [Ejemplos de código JavaScript en flujos de trabajo](javascript-in-workflows.md)

### Retraso de ejecución {#exec-delay}

A partir de la versión 20.2, se ha agregado un retraso de ejecución a las actividades **[!UICONTROL JavaScript code]** y **[!UICONTROL Advanced JavaScript code]**. De forma predeterminada, la fase de ejecución no puede exceder de 1 hora. Tras esta demora, el proceso se anula con un mensaje de error y la ejecución de la actividad falla.

Puede cambiar esta demora en el campo **[!UICONTROL Stop execution after]** disponible en estas actividades.

Para omitir este límite, debe establecer el valor en **0**.

### Código JavaScript {#js-code-desc}

![](assets/javascript_code.png)

* **[!UICONTROL Script]**: El área central del editor contiene la secuencia de comandos que se va a ejecutar.

* **[!UICONTROL Process errors]**: Consulte [Errores de procesamiento](monitor-workflow-execution.md#processing-errors).

### Código JavaScript avanzado {#adv-js-code-desc}

![](assets/advanced_javascript_code.png)

* **[!UICONTROL First call]**: La primera zona del editor contiene el script que se activará durante la primera llamada.
* **[!UICONTROL Next calls]**: La segunda zona del editor contiene el script que se ejecutará durante las siguientes llamadas.
* **[!UICONTROL Transitions]**: Puede definir varias transiciones de salida de actividad.
* **[!UICONTROL Schedule]**: La pestaña **[!UICONTROL Schedule]** permite programar el lanzamiento de la actividad.

JavaScript avanzado es una tarea persistente que se recuerda periódicamente si no se ha marcado como completada. Para terminar la tarea y evitar futuras recuperaciones, debe utilizar el método **task.setCompleted()** en la sección **[!UICONTROL Next calls]**:

```
task.postEvent(task.transitionByName("ok")); // to transition to Ok branch
task.setCompleted();

return 0;
```
