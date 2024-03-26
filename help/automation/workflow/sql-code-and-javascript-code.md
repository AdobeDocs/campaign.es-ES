---
product: campaign
title: Código SQL y código JavaScript
description: Descubra más información sobre las actividades de flujo de trabajo de código SQL y código JavaScript
feature: Workflows
Role: User
Level: Experienced
exl-id: 8c385847-a320-4cd9-9048-2bf9daf2ee07
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 100%

---

# Código SQL y código JavaScript{#sql-code-and-javascript-code}



## Código SQL {#sql-code}

Una actividad de **[!UICONTROL SQL code]** ejecuta una secuencia de comandos SQL. La secuencia de comandos es una plantilla JST.

![](assets/sql_code.png)

* **[!UICONTROL Script]**

  El área central del editor contiene la secuencia de comandos que se va a ejecutar. Esta secuencia de comandos es una plantilla JST y, por lo tanto, se puede configurar según el contexto del flujo de trabajo.

* **[!UICONTROL Processing errors]**

  Consulte [Errores de procesamiento](monitor-workflow-execution.md#processing-errors).

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
