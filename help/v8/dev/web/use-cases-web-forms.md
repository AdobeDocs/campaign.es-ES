---
product: campaign
title: 'Casos de uso: Formularios web'
description: 'Casos de uso: Formularios web'
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 7aa4646d-1325-47c2-b553-6fe375c48973
TQID: 'https://experienceleague.adobe.com/Zw-cfoQrq1PAe-swZ7gvMNyTb4ciCMF2kdT7fN2zLsg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 57%
---
# Casos de uso: Formularios web{#use-cases-web-forms}



## Creación de un formulario de suscripción con doble inclusión {#create-a-subscription--form-with-double-opt-in}

Al ofrecer servicios de información, es necesario que los destinatarios se suscriban para recibir todas las comunicaciones vinculadas. Para evitar comunicaciones incorrectas y asegurarse de que el destinatario se haya suscrito intencionadamente, se recomienda enviar una solicitud de confirmación de suscripción para crear una inclusión doble. La suscripción solo es efectiva una vez que el usuario hace clic en el vínculo incluido en el mensaje de confirmación.

Este ejemplo se basa en el siguiente supuesto:

1. Creación de un formulario de suscripción a un boletín informativo en un sitio web que contiene una casilla de verificación para suscribirse a un servicio temporal. Este servicio permite enviar mensajes de confirmación de suscripción.
1. Creación de la entrega de confirmación de suscripción con una plantilla de envío vinculada al formulario web. Contiene el vínculo de confirmación que llama al formulario para la suscripción al boletín informativo y muestra un mensaje de aprobación de la suscripción.

### Paso 1: Creación de servicios de información {#step-1---creating-information-services}

1. Cree el servicio de suscripción al boletín informativo que desea ofrecer a los destinatarios. Para obtener más información sobre la creación de boletines informativos, consulte [esta sección](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/about-services-and-subscriptions){target="_blank"}.

   ![Cuadro de diálogo de servicio para el servicio de boletín semanal con los campos Etiqueta, Nombre interno, Escribir correo electrónico y Modo de boletín.](assets/s_ncs_admin_survey_double-opt-in_sample_1.png)

1. Cree un segundo servicio de información, un servicio temporal vinculado a una plantilla de envío que se encargue de enviar mensajes de confirmación de suscripción.

   ![Panel de servicio temporal (temp_service) que muestra el correo electrónico de tipo, la newsletter de modo y su carpeta.](assets/s_ncs_admin_survey_double-opt-in_sample_1c.png)

### Paso 2: Creación de mensajes de confirmación {#step-2---creating-confirmation-messages}

Los mensajes de confirmación se envían a través de una plantilla de envíos dedicada en el nivel de servicio temporal.

1. En **[!UICONTROL Explorer]**, seleccione **[!UICONTROL Resources > Templates > Delivery templates]**
1. Cree una plantilla de envío para enviar los mensajes de confirmación de suscripción.
1. En **[!UICONTROL To]**, haga clic en el botón **[!UICONTROL Email parameters]** para asociar la plantilla de envío con la asignación de destino de suscripciones en lugar de con los destinatarios.

   ![Cuadro de diálogo Seleccionar destino en la plantilla de envío con la asignación de destino Suscripciones (nms:subscription) seleccionada.](assets/s_ncs_admin_survey_double-opt-in_sample_1d.png)

1. Debido a que los destinatarios de este envío no han confirmado su aprobación, aún se encuentran en la lista de bloqueados de la base de datos. Para que reciban esta comunicación, debe autorizar las entregas basadas en esta plantilla para dirigirse a los destinatarios en la lista de bloqueados de la.

   Para ello, haga clic en la pestaña **[!UICONTROL Exclusions]**.

1. Haga clic en el vínculo **[!UICONTROL Edit...]** y desmarque la opción **[!UICONTROL Exclude recipients who no longer want to be contacted]**.

   <!-- ![](assets/s_ncs_admin_survey_double-opt-in_sample_4d.png)-->

   >[!IMPORTANT]
   >
   >Esta opción solo puede desactivarse en este tipo de contexto.

1. Personalice la entrega e inserte el vínculo de confirmación en el contenido del mensaje. Este vínculo permite acceder al formulario web para registrar la confirmación de suscripción.

   ![Correo electrónico de confirmación en el editor de envíos con un campo de personalización de nombre y un vínculo Haga clic aquí.](assets/s_ncs_admin_survey_double-opt-in_sample_1b.png)

1. Con el DCE, vincule la dirección URL al formulario web. Dado que el formulario web aún no se ha creado, reemplace el valor en cuanto lo cree.

   ![Panel de vínculos de hipertexto con el campo de aplicación Web, aún vacío, para el vínculo Haga clic aquí en el correo electrónico de confirmación.](assets/s_ncs_admin_survey_double-opt-in_sample_3.png)

1. Por último, vincule esta plantilla al servicio temporal creado anteriormente.

   ![Pestaña Modificar servicio temporal con la entrega de confirmación seleccionada en el campo Suscripción.](assets/s_ncs_admin_survey_double-opt-in_sample_3c.png)

### Paso 3: Creación del formulario de suscripción {#step-3---creating-the-subscription-form}

El formulario web permite la suscripción del destinatario y la confirmación de la suscripción.

El flujo de trabajo del formulario web incluye las siguientes actividades:

![Flujo de trabajo de formulario web: precargando, probando y enviando por correo electrónico los posibles clientes vacíos a Lista de bloqueados de script, suscripción, almacenamiento, fin.](assets/s_ncs_admin_survey_double-opt-in_sample_4c.png)

Para realizar esto, siga los pasos a continuación:

1. Cree un formulario web y seleccione la plantilla **[!UICONTROL Newsletter subscription (subNewsletter)]**.

   ![Nuevo cuadro de diálogo de aplicación web con la plantilla de suscripción al boletín informativo (subNewsletter) seleccionada.](assets/s_ncs_admin_survey_double-opt-in_sample_5a.png)

1. En la pestaña **[!UICONTROL Edit]**, se debe configurar el flujo de trabajo existente, ya que el objetivo es añadir un mensaje de confirmación a los destinatarios que deseen suscribirse.

   Para ello, haga doble clic en la casilla **[!UICONTROL Preloading]** y configúrela de la siguiente manera:

   ![Cuadro de diálogo de actividad de precarga con datos de carga automática a los que se hace referencia en el formulario y Omitir precarga si no se ha seleccionado ningún ID.](assets/s_ncs_admin_survey_double-opt-in_sample_5b.png)

   Esto significa que si el usuario accede a este formulario mediante el vínculo del mensaje de confirmación, se carga su información de perfil. Si accede al formulario web a través de una página del sitio web, no se carga ninguna información.

1. Añada una actividad **[!UICONTROL Test]** al flujo de trabajo.

   ![Flujo de trabajo de formulario web con una actividad de prueba que se ramifica en el correo electrónico vacío a Suscripción, Almacenamiento y Finalización.](assets/s_ncs_admin_survey_double-opt-in_sample_6e.png)

   La actividad **[!UICONTROL Test]** puede involucrar al correo electrónico del destinatario. En este caso, configúrelo de la siguiente manera:

   ![El editor de la rama de actividad de prueba con la condición @email no está vacío.](assets/s_ncs_admin_survey_double-opt-in_sample_6d.png)

1. Añada dos actividades **[!UICONTROL Script]** al flujo de trabajo.

   ![Flujo de trabajo de formulario web con una actividad de secuencia de comandos en cada rama de la actividad de prueba.](assets/s_ncs_admin_survey_double-opt-in_sample_6f.png)

   La primera actividad **[!UICONTROL Script]** agregará destinatarios en la lista de bloqueados de la hasta que hayan confirmado su suscripción al boletín informativo. El contenido debe ser el siguiente:

   ```javascript
   ctx.recipient.@blackList=1
   ```

   ![Actividad de Lista de bloqueados de script que contiene el script ctx.recipient.@blackList=1.](assets/s_ncs_admin_survey_double-opt-in_sample_6bbis.png)

   La segunda actividad **[!UICONTROL Script]** autoriza las entregas a los usuarios y los suscribe al boletín informativo. Las dos últimas líneas de la secuencia de comandos permiten transferir los destinatarios de la carpeta temporal a otra carpeta y reconciliarlos con perfiles existentes en cuanto confirmen la suscripción.

   ```javascript
   ctx.recipient.@blackList=0
   nms.subscription.Subscribe("INTERNAL_NAME_OF_THE_NEWSLETTER", ctx.recipient, false)
   ctx.recipient.folder = <folder name="nmsRootRecipient"/>
   nms.subscription.Unsubscribe("TEMP", ctx.recipient)
   ```

   >[!NOTE]
   >
   >La partición **[!UICONTROL Temp]** también se puede eliminar de forma regular mediante un flujo de trabajo.

   ![Segunda actividad de script que contiene las líneas de script de cancelación de bloqueo, suscripción, carpeta y cancelación de suscripción.](assets/s_ncs_admin_survey_double-opt-in_sample_6b.png)

1. Haga doble clic en la actividad **[!UICONTROL Subscription]** para personalizar el formulario de suscripción y relacionar una casilla de verificación con el servicio temporal creado anteriormente.

   ![Editor de páginas con la casilla de verificación de consentimiento vinculada al servicio temporal en el campo Servicio.](assets/s_ncs_admin_survey_double-opt-in_sample_5c.png)

1. Configure la actividad **[!UICONTROL Storage]** para guardar la información introducida en la página del formulario.

   Esta actividad permite crear perfiles de destinatario en una carpeta provisional específica para separarlos de los perfiles de la base de datos a los que se pueden enviar comunicaciones.

   ![Cuadro de diálogo de actividad de almacenamiento con la carpeta Temp establecida como carpeta de creación.](assets/s_ncs_admin_survey_double-opt-in_sample_5g.png)

   >[!NOTE]
   >
   >No se debe definir ninguna opción de reconciliación.

1. Añada dos actividades **[!UICONTROL End]** para mostrar un mensaje para el usuario.

   La segunda casilla **[!UICONTROL End]** muestra el mensaje de confirmación una vez que se haya completado la suscripción.

   ![Finalizar cuadro de diálogo de actividad con el mensaje Se ha completado su suscripción. Pronto recibirá nuestra newsletter.](assets/s_ncs_admin_survey_double-opt-in_sample_5h.png)

1. Una vez creado y configurado el formulario web, se puede hacer referencia a él en la plantilla de envíos para enviar mensajes de confirmación.

   ![Envío de confirmación con el vínculo Haga clic aquí que señala a la aplicación web de inclusión doble de suscripción al boletín informativo.](assets/s_ncs_admin_survey_double-opt-in_sample_7b.png)

### Paso 4: Publicación y prueba del formulario {#step-4---publishing-and-testing-the-form}

Ahora se puede publicar el formulario para que los usuarios puedan acceder a él.

![Panel de aplicación web con el botón Publicar y el mensaje que debe publicarse para tener acceso en línea.](assets/s_ncs_admin_survey_double-opt-in_sample_8b.png)

La suscripción al boletín informativo implica los pasos siguientes:

1. El usuario del sitio web inicia sesión en la página de suscripción y aprueba el formulario.

   ![Formulario de suscripción a la newsletter en un explorador con nombre y correo electrónico completados, casilla de consentimiento activada y botón Suscribirme.](assets/s_ncs_admin_survey_double-opt-in_sample_8c.png)

   Reciben una notificación a través de un mensaje en el explorador en el que se ha tenido en cuenta su solicitud.

   ![La página de finalización del explorador indica que la solicitud se ha registrado y seguirá un mensaje.](assets/s_ncs_admin_survey_double-opt-in_sample_8d.png)

   El usuario se añade a la base de datos de Adobe Campaign en la carpeta **[!UICONTROL Temp]** y su perfil se añade a la lista de bloqueados hasta que confirme su suscripción con el correo electrónico.

   ![Carpeta de destinatarios temporales con el nuevo perfil seleccionado y Ya no se puede contactar (por ningún canal) seleccionado.](assets/s_ncs_admin_survey_double-opt-in_sample_8f.png)

1. Se les envía un mensaje de confirmación que incluye un vínculo para aprobar su suscripción.

   ![Correo electrónico de confirmación de suscripción con un vínculo Haga clic aquí para confirmar la suscripción al boletín informativo.](assets/s_ncs_admin_survey_double-opt-in_sample_8e.png)

1. Al hacer clic en este vínculo, la página de aprobación se muestra en el explorador.

   ![ página de navegador titulada ¡Felicitaciones! confirmando que la suscripción está activa.](assets/s_ncs_admin_survey_double-opt-in_sample_8.png)

   En Adobe Campaign se actualiza el perfil de usuario:

   * ya no están en lista de bloqueados,
   * están suscritos al servicio informativo.

     ![Se ha actualizado el perfil de destinatario con No se ha eliminado el contacto y la suscripción al boletín informativo aparece en la lista.](assets/s_ncs_admin_survey_double-opt-in_sample_9.png)

## Visualización de distintas opciones en función de los valores seleccionados {#displaying-different-options-depending-on-the-selected-values}

En el ejemplo siguiente, se solicita al usuario que seleccione un tipo de vehículo. Puede mostrar las categorías de vehículo disponibles según el tipo seleccionado. Esto significa que los elementos que se muestran en la columna derecha dependen de la selección del usuario:

![Página de selección de automóvil con una lista desplegable de tipo de automóvil establecida en Seleccionar.](assets/s_ncs_admin_survey_condition_sample0.png)

* Cuando el usuario selecciona “vehículo privado”, se ofrecen las opciones “compacto” y “monovolumen”.

  ![Página de selección de automóvil con automóvil personal seleccionado, que muestra las opciones Estándar y Compacta.](assets/s_ncs_admin_survey_condition_sample2.png)

* Cuando el usuario selecciona “vehículo comercial”, se muestra una selección en una lista desplegable:

  ![Página de selección de vehículos con el camión en movimiento seleccionado y una lista desplegable de tipos de vehículos de la clase.](assets/s_ncs_admin_survey_condition_sample1.png)

En este ejemplo, el tipo de vehículo no se almacena en la base de datos. La lista desplegable se configura de la siguiente manera:

![Tipo de propiedades de cuadro combinado de coche con los valores Seleccionar, Coche personal y Camión móvil.](assets/s_ncs_admin_survey_condition_config1.png)

Esta información se almacena en una variable local.

La visualización condicional de la columna derecha se configura en los contenedores:

![Cuadro de diálogo de almacenamiento con la opción Variable seleccionada para el campo Tipo de vehículo.](assets/s_ncs_admin_survey_condition_config1bis.png)

* Visibilidad condicional de campos para un vehículo privado:

  ![Condición de visibilidad en el contenedor de automóvil personal: tipo de automóvil igual a automóvil personal.](assets/s_ncs_admin_survey_condition_config2.png)

* Visibilidad condicional de campos para un vehículo comercial:

  ![Condición de visibilidad en el contenedor de camión/furgoneta: tipo de vehículo igual al camión en movimiento.](assets/s_ncs_admin_survey_condition_config3.png)
