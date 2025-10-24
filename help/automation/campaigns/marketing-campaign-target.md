---
product: campaign
title: Público destinatario de la campaña de marketing
description: Aprenda a definir el público de las campañas de marketing
feature: Campaigns, Audiences
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 70a63632-f66d-40f2-806d-bde89303936a
source-git-commit: 26829656f8e06434ca3207c0c7b62ba907765972
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 78%

---

# Selección del público de las campañas {#marketing-campaign-deliveries}

En una campaña de marketing, puede definir lo siguiente por envío:

* La audiencia de destino. Puede enviar mensajes a una [lista de destinatarios](#send-to-a-group) o crear una [audiencia en un flujo de trabajo](#build-the-main-target-in-a-workflow)
* Un grupo de control. Puede [agregar un grupo de control](#add-a-control-group) para supervisar el comportamiento de los destinatarios después de enviar el mensaje
* Direcciones semilla: obtenga más información en [esta sección](../../v8/audiences/test-profiles.md).

Parte de esta información se hereda de la [plantilla de campaña](marketing-campaign-templates.md#campaign-templates).

<!--
To build the delivery target, you can define filtering criteria for the recipients in the database. This recipient selection mode is presented in [this section](../../delivery/using/steps-defining-the-target-population.md).
-->

## Enviar a un grupo{#send-to-a-group}

Puede importar una población a una lista y luego establecer como objetivo esta lista en las entregas. Para realizar esto, siga los pasos a continuación:

1. Edite la entrega y haga clic en el vínculo **[!UICONTROL To]** para cambiar la población de destino.
1. En la pestaña **[!UICONTROL Main target]**, seleccione la opción **[!UICONTROL Defined via the database]** y haga clic en **[!UICONTROL Add]** para seleccionar destinatarios.

   ![](assets/select-main-target.png)

1. Elija **[!UICONTROL A list of recipients]**.

   ![](assets/target-a-list.png)


1. Haga clic en **[!UICONTROL Next]** para seleccionar la lista.

   ![](assets/select-the-list.png)

   Puede refinar el objetivo añadiendo nuevos criterios de filtrado.

1. Haga clic en **[!UICONTROL Finish]** una vez que se hayan definido todos los criterios y guarde el destinatario principal.

## Creación del público en un flujo de trabajo de campaña {#build-the-main-target-in-a-workflow}

El objetivo principal de una entrega también se puede definir en el flujo de trabajo de campaña: este entorno gráfico permite crear un objetivo utilizando consultas, pruebas y operadores: unión, deduplicación, uso compartido, etc.

>[!IMPORTANT]
>
>No debe añadir más de 28 flujos de trabajo en una campaña. Más allá de este límite, los flujos de trabajo adicionales no se ven en la interfaz y pueden dar lugar a errores.

### Creación del flujo de trabajo {#create-a-targeting-workflow}

El objetivo se puede crear mediante una combinación de condiciones de filtrado en una secuencia gráfica de un flujo de trabajo. Puede crear poblaciones y subpoblaciones según lo necesite. Para mostrar el editor de flujo de trabajo, haga clic en la pestaña **[!UICONTROL Targeting and workflows]** del panel de control de campañas.

![](assets/targeting-and-wf-tab.png)

La población de destino se extrae de la base de datos de Adobe Campaign a través de una o varias consultas ubicadas en un flujo de trabajo. Aprenda a generar una consulta en [esta sección](../workflow/query.md).

Puede iniciar consultas y compartir poblaciones mediante cuadros como Unión, Intersección, Compartir, Exclusión, etc.

Seleccione los objetos de las listas a la izquierda del espacio de trabajo y enlácelos para crear el objetivo.

![](assets/campaign-wf.png)

En el diagrama, vincule las consultas de objetivo y de programación necesarias para la creación del objetivo en el diagrama. Puede ejecutar el objetivo mientras la creación está en curso para comprobar la población extraída de la base de datos.

>[!NOTE]
>
>En [esta sección](../workflow/query.md) se detallan ejemplos y procedimientos para definir consultas.

La sección izquierda del editor contiene una biblioteca de objetos gráficos que representan actividades. La primera pestaña contiene las actividades de objetivos, y la segunda pestaña contiene las actividades de control de flujo, que se utilizan a menudo para coordinar las actividades de objetivos.

Es posible acceder a las funciones de formato y ejecución del flujo de trabajo de objetivos mediante la barra de herramientas del editor de diagramas.

![](assets/wf-diagram.png)

>[!NOTE]
>
>Las actividades disponibles para generar el diagrama, así como todas las características de presentación y presentación, se detallan en [esta sección](../workflow/about-workflows.md).

Puede crear varios flujos de trabajo de objetivos para una sola campaña. Para agregar un flujo de trabajo:

1. Vaya a la sección superior izquierda de la zona de creación del flujo de trabajo, haga clic con el botón derecho del ratón y seleccione **[!UICONTROL Add]**. También puede utilizar el botón **[!UICONTROL New]** situado encima de esta zona.

   ![](assets/add-a-wf.png)

1. Seleccione la plantilla **[!UICONTROL New workflow]** y asigne un nombre a este flujo de trabajo.
1. Haga clic en **[!UICONTROL OK]** para confirmar la creación del flujo de trabajo y, a continuación, cree el diagrama para este flujo de trabajo.

### Ejecución del flujo de trabajo {#execute-a-workflow}

Los flujos de trabajo de destino se pueden iniciar manualmente mediante el botón **[!UICONTROL Start]** de la barra de herramientas, siempre que tenga los derechos adecuados.

La segmentación se puede programar para la ejecución automática según una programación (programador) o un evento (señal externa, importación de archivos, etc.).

Las acciones relacionadas con la ejecución del flujo de trabajo de destino (inicio, parada, pausa, etc.) son procesos **asincrónicos**: el comando se guarda y se aplica en cuanto el servidor esté disponible para su aplicación.

Los iconos de la barra de herramientas permiten realizar acciones en cuanto a la ejecución del flujo de trabajo de destino.

* Inicio o reinicio

   * El icono **[!UICONTROL Start]** permite iniciar el flujo de trabajo de destino. Al hacer clic en este icono, todas las actividades sin transición de entrada se activan (excepto los saltos de extremo final).

     ![](assets/start.png)

     El servidor tiene en cuenta la solicitud, tal como muestra su estado: **[!UICONTROL Start as soon as possible]**.

   * Puede reiniciar el flujo de trabajo de destino mediante el icono correspondiente de la barra de herramientas. Este comando puede resultar útil si el icono **[!UICONTROL Start]** no está disponible, por ejemplo cuando el flujo de trabajo de destino está detenido. En este caso, haga clic en el icono **[!UICONTROL Restart]** para anticipar el reinicio. El servidor tiene en cuenta la solicitud, como muestra su estado: **[!UICONTROL Restart requested]**.

* Detener o pausar

   * Los iconos de la barra de herramientas permiten detener o pausar un flujo de trabajo de objetivos en curso.

     Al hacer clic en **[!UICONTROL Pause]**, las operaciones en curso **[!UICONTROL are not]** no se pausan, pero no se inicia ninguna otra actividad hasta el siguiente reinicio.

     ![](assets/pause.png)

     El servidor tiene en cuenta el comando, como muestra su estado: **[!UICONTROL Pause requested]**.

     También puede pausar un flujo de trabajo de objetivos automáticamente cuando su ejecución alcanza una actividad determinada. Para ello, haga clic con el botón derecho en la actividad desde la que desea pausar el flujo de trabajo de objetivos y seleccione **[!UICONTROL Enable but do not execute]**.

     ![](assets/donotexecute.png)

     Esta configuración se muestra mediante un icono especial.

     ![](assets/pause_activity.png)

     >[!NOTE]
     >
     >Esta opción es útil durante el diseño avanzado de campañas y las fases de prueba.

     Haga clic en **[!UICONTROL Start]** para reanudar la ejecución.

   * Haga clic en el icono **[!UICONTROL Stop]** para detener la ejecución en curso.

     ![](assets/stop.png)

     El servidor tiene en cuenta el comando, como muestra su estado: **[!UICONTROL Stop requested]**.

  También puede detener automáticamente un flujo de trabajo de objetivos cuando la ejecución alcance una actividad. Para ello, haga clic con el botón derecho en la actividad desde la que desea detener el flujo de trabajo de objetivos y seleccione **[!UICONTROL Do not activate]**.

  ![](assets/donotactivate.png)

  Esta configuración se muestra mediante un icono especial.

  ![](assets/unactivation.png)


  >[!NOTE]
  >
  >Esta opción es útil durante el diseño avanzado de campañas y las fases de prueba.

* Interrupción incondicional

  En Explorer, seleccione **[!UICONTROL Administration > Production > Object created automatically > Campaign workflows]** para acceder y utilizar cada flujo de trabajo de campaña.

  Puede detener el flujo de trabajo de forma incondicional haciendo clic en el icono **[!UICONTROL Actions]** y seleccionando Interrupción **[!UICONTROL Unconditional]**. Esta acción termina el flujo de trabajo de la campaña.

  ![](assets/stop_unconditional.png)

  >[!CAUTION]
  >
  >La parada incondicional está restringida a los usuarios administradores.

## Adición de un grupo de control {#add-a-control-group}

Un grupo de control es una población que no recibe la entrega; se utiliza para rastrear el comportamiento tras la entrega y el impacto de la campaña estableciendo una comparación con el comportamiento de la población de destino que recibió la entrega.

El grupo de control se puede extraer del objetivo principal o provenir de un grupo o consulta específicos.

>[!CAUTION]
>
>No se pueden utilizar grupos de control al cargar la población de destinatarios desde un archivo externo.

### Activación del grupo de control para una campaña {#activate-the-control-group-for-a-campaign}

Puede definir un grupo de control en el nivel de la campaña, en cuyo caso se aplica el grupo de control a cada entrega de la campaña correspondiente.

1. Edite la campaña en cuestión y haga clic en la pestaña **[!UICONTROL Edit]** .
1. Haga clic **[!UICONTROL Advanced campaign parameters...]**.

   ![](assets/enable-control-group.png)

1. Seleccione la opción **[!UICONTROL Enable and edit control group configuration]**.
1. Haga clic en **[!UICONTROL Edit...]** para configurar el grupo de control.

   ![](assets/edit-control-group.png)

El procedimiento completo se detalla en [esta sección](#extract-the-control-group-from-the-main-target). Obtenga más información sobre los grupos de control en [esta sección](#add-a-population).

### Activación del grupo de control para una entrega {#activate-the-control-group-for-a-delivery}

Puede definir un grupo de control al nivel de la entrega, en cuyo caso se aplica el grupo de control a cada entrega de la campaña correspondiente.

De manera predeterminada, la configuración del grupo de control definida al nivel de campaña se aplica a todas las entregas de dicha campaña. Sin embargo, puede adaptar el grupo de control para una entrega individual.

>[!NOTE]
>
>Si ha definido un grupo de control para una campaña y lo configura para una entrega relacionada con esta campaña, solo se aplica el grupo de control definido para la entrega.

1. Edite la entrega en cuestión y, a continuación, haga clic en el vínculo **[!UICONTROL To]**.
1. Haga clic en la pestaña **[!UICONTROL Control group]** y seleccione **[!UICONTROL Enable and edit control group configuration]**.

   ![](assets/enable-control-group-for-a-delivery.png)

1. Haga clic en **[!UICONTROL Edit...]** para configurar el grupo de control.

El procedimiento completo se detalla en [esta sección](#extract-the-control-group-from-the-main-target).

### Uso de una nueva población como grupo de control {#add-a-population}

Puede utilizar una población específica para el grupo de control. En ese caso, seleccione la lista que desea utilizar como grupo de control en el campo relacionado.

Esta población puede proceder de una lista de destinatarios o puede definirla mediante una consulta específica.

![](assets/new-population-as-control-group.png)

>[!NOTE]
>
>El editor de consultas de Adobe Campaign se muestra en [esta sección](../../v8/start/query-editor.md).

### Extracción del grupo de control a partir del objetivo principal {#extract-the-control-group-from-the-main-target}

También puede extraer destinatarios del objetivo principal de la entrega. En este caso, los destinatarios se toman del objetivo de las acciones de envío afectadas por esta configuración. Esta extracción puede ser aleatoria o puede ser el resultado de la ordenación de los destinatarios.

![](assets/extract-control-group-from-target.png)

Para extraer un grupo de control, habilite el grupo de control para la campaña o entrega y seleccione una de las siguientes opciones: **[!UICONTROL Activate random sampling]** o **[!UICONTROL Keep only the first records after sorting]**.

* Utilice la opción **[!UICONTROL Activate random sampling]** para aplicar muestreo aleatorio a los destinatarios en la población principal. Si establece el umbral en 100, el grupo de control se compone de 100 destinatarios seleccionados aleatoriamente desde la población de destino. El muestreo aleatorio depende del motor de la base de datos.
* Utilice la opción **[!UICONTROL Keep only the first records after sorting]** para definir una limitación basada en uno o más órdenes de clasificación. Si selecciona el campo **[!UICONTROL Age]** como criterio de clasificación y, a continuación, define 100 como umbral, el grupo de control se compone de los 100 destinatarios más jóvenes. Por ejemplo, podría resultar interesante definir un grupo de control que incluya destinatarios que realizan pocas compras o destinatarios que realizan compras frecuentes y comparar su comportamiento con el de los destinatarios contactados.

Haga clic en **[!UICONTROL Next]** para definir el orden de clasificación (si es necesario) y seleccione el modo de limitación de destinatarios.

![](assets/limit-control-group.png)

Esta configuración equivale a una actividad **[!UICONTROL Split]** del flujo de trabajo, lo que permite desglosar el objetivo en subconjuntos. El grupo de control es uno de estos subconjuntos.


### Tutorial en vídeo {#create-email-video}

En este vídeo se explica cómo añadir un grupo de control a una campaña.

>[!VIDEO](https://video.tv.adobe.com/v/335606?quality=12)

Puede encontrar disponibles más vídeos de procedimientos para Campaign [aquí](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
