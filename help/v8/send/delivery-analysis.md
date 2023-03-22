---
title: Análisis de envíos
description: Descubra cómo preparar y comprobar su envío
feature: Personalization
role: User
level: Beginner
source-git-commit: 51b333492ad50849751208c7549dc00f66140b82
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Análisis de envíos {#analyze-delivery}

El análisis es el paso de preparación de la entrega. Se puede iniciar una vez que la audiencia de destino esté definida y el contenido del mensaje esté listo y probado. Durante el análisis de la entrega, se calcula la población objetivo y se prepara el contenido de la entrega. Una vez finalizada, la entrega está listo para realizarse.

## Inicie el análisis {#start-the-analysis}

Para preparar la entrega, asegúrese de que el contenido de la entrega y el destinatario se hayan definido y siga los pasos a continuación:

1. En las ventanas de envío, haga clic en el **[!UICONTROL Send]** botón.
1. Select **[!UICONTROL Deliver as soon as possible]** para realizar el cálculo de audiencia y la preparación de contenido para un envío inmediato. También puede posponer la entrega a una fecha posterior, u obtener una estimación de la población sin preparar el contenido.

   ![](assets/delivery-analysis-start.png)

1. Haga clic en **[!UICONTROL Analyze]** para iniciar el análisis manualmente. La barra de progreso muestra el progreso del análisis.

   Se aplica un conjunto de reglas de comprobación durante el análisis de envío. Estas reglas se definen en una **tipología**, que se selecciona en la variable **[!UICONTROL Typology]** en las propiedades de entrega. Obtenga más información sobre las tipologías en [esta sección](../../automation/campaign-opt/campaign-typologies.md).

   De forma predeterminada, en el caso de los correos electrónicos, el análisis cubre los siguientes puntos:

   * Aprobación del objeto
   * Aprobación de las URL e imágenes
   * Aprobación de las etiquetas de URL
   * Aprobación del vínculo de baja
   * Comprobación del tamaño de las pruebas
   * Comprobación del periodo de validez
   * Comprobación de la programación de las olas


1. Puede detener el análisis en cualquier momento haciendo clic en el botón **[!UICONTROL Stop]** botón.

   No se envían mensajes durante la fase de preparación. Por lo tanto, puede iniciar o cancelar el análisis sin riesgos.

   >[!IMPORTANT]
   >
   >Al ejecutarse, el análisis detiene el envío (o prueba). Cualquier modificación al envío (o la prueba) debe ir seguida de otro análisis antes de ser válida.

   Cuando termina el análisis, la sección superior de la ventana indica si la preparación del envío ha finalizado o si se ha producido algún error. Se muestran todos los pasos, advertencias y errores de validación. Los iconos de color muestran el tipo de mensaje:

   * Un icono azul indica un mensaje informativo.
   * El icono amarillo indica un error de procesamiento no crítico.
   * El icono rojo indica un error crítico que impide realizar la entrega.

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. Haga clic en **[!UICONTROL Close]** para corregir los errores. Después de realizar los cambios, reinicie el análisis haciendo clic en **[!UICONTROL Analyze]**.

   >[!NOTE]
   >
   >Haga clic en el **[!UICONTROL Change the main delivery target]** vínculo si el número de mensajes que desea enviar no coincide con sus expectativas. Esta opción permite cambiar la definición de la población objetivo y reiniciar el análisis.

1. Después de comprobar el resultado del análisis, haga clic en **[!UICONTROL Confirm delivery]** para enviar el mensaje al destinatario principal.


## Configuración del análisis {#analysis-settings}

Vaya a la **[!UICONTROL Analysis]** de las propiedades de entrega para definir la configuración de la preparación del mensaje durante la fase de análisis.

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

Esta pestaña proporciona acceso a las siguientes opciones:

* **[!UICONTROL Label and code of the delivery]**: las opciones de esta sección se utilizan para calcular los valores de estos campos durante la fase de análisis de envío. El campo **[!UICONTROL Compute the execution folder during the delivery analysis]** calcula el nombre de la carpeta que debe contener esta acción de entrega durante la fase de análisis.

* **[!UICONTROL Approval mode]**: este campo permite definir el envío manual o automático una vez finalizado el análisis. 

   Si se generan advertencias durante el análisis (por ejemplo, si se acentúan ciertos caracteres en el asunto de la entrega, etc.), puede configurar la entrega para definir si se debe ejecutar o no. De forma predeterminada, el usuario debe confirmar la entrega de los mensajes al final de la fase de análisis: esta es la validación **manual**.

   Seleccione otro modo de aprobación en la lista desplegable del campo apropiado.

   Están disponibles los siguientes modos de aprobación:

   * **[!UICONTROL Manual]**: al final de la fase de análisis, el usuario debe confirmar la entrega para iniciarlo. Para ello, haga clic en el botón **[!UICONTROL Start]** para iniciar la entrega.
   * **[!UICONTROL Semi-automatic]**: la entrega comienza automáticamente si la fase de análisis no genera mensajes de advertencia.
   * **[!UICONTROL Automatic]**: la entrega comienza automáticamente al final de la fase de análisis, independientemente de su resultado.

* **[!UICONTROL Start job in a detached process]**: esta opción permite iniciar el análisis de envío en un proceso independiente. La función de análisis utiliza el proceso del servidor de aplicaciones de Adobe Campaign (web nlserver) de forma predeterminada. Al seleccionar esta opción, se asegura de que el análisis se complete incluso en caso de que falle el servidor de aplicaciones.
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]**: esta opción añade los registros de consulta SQL al diario de entrega durante la fase de análisis.
* **[!UICONTROL Ignore personalization scripts during sending]**: esta opción permite evitar la interpretación de las directrices de JavaScript que se encuentran en el contenido HTML. Se visualizan tal y como están en los contenidos enviados. Estas directivas se introducen con `<%=` etiqueta.


