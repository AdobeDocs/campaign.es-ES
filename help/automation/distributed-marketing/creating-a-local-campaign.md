---
product: campaign
title: Creación de una campaña local
description: Creación de una campaña local
feature: Distributed Marketing
version: Campaign v8, Campaign Classic v7
role: User
exl-id: b46530b5-cb81-40d7-b596-c7685359782a
TQID: https://experienceleague.adobe.com/hxeStkXhnSKoLew2gYv3nIDeoRjwgTYINF83w70aFxo
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: cdc2fbe67fe123c895c8d3d71daffe022ba5c030
workflow-type: tm+mt
source-wordcount: '2232'
ht-degree: 64%
---
# Creación de una campaña local{#creating-a-local-campaign}



Una campaña local es una instancia creada a partir de una plantilla a la que se hace referencia en la lista de **[!UICONTROL campaign packages]** con una **programación de ejecución determinada**. Su objetivo es utilizar una comunicación local mediante una plantilla de campaña configurada por la entidad central. Las principales fases para implementar una operación local son las siguientes:

**Para la entidad central**

1. Creación de una plantilla de campaña local.
1. Creación de un paquete de campaña a partir de una plantilla.
1. Publicación de un paquete de campaña.
1. Aprobación de solicitudes.

**Para la entidad local.**

1. Solicitud de la campaña.
1. Ejecución de campañas.

## Creación de una plantilla de campaña local {#creating-a-local-campaign-template}

Para crear un paquete de campañas, primero debe crear la **plantilla de campaña** a través del nodo **[!UICONTROL Resources > Templates]**.

Para crear una nueva plantilla local, duplique la plantilla predeterminada **[!UICONTROL Local campaign (opLocal)]**.

![Lista de plantillas de campaña con el menú contextual Local campaign (opLocal) y la opción Duplicate resaltada](assets/mkg_dist_local_op_creation.png)

Asigne un nombre a la plantilla de campaña y complete los campos disponibles.

![Nuevo cuadro de diálogo de campaña de marketing con los campos Etiqueta, Naturaleza, Tipo de operación, Canal principal, Duración y Descripción](assets/mkg_dist_local_op_creation1.png)

En la ventana de la campaña, haga clic en la pestaña **[!UICONTROL Edit]** y luego en el enlace **[!UICONTROL Advanced campaign parameters...]**.

![Pestaña Campaign Edit con el vínculo Advanced campaign parameters de la sección Properties](assets/mkt_distr_4.png)

### Interfaz web {#web-interface}

En la pestaña **Marketing distribuido**, puede elegir el tipo de interfaz web y especificar los valores y parámetros predeterminados que introducir cuando una entidad local realiza una solicitud.

La interfaz web corresponde a un formulario que la entidad local rellena al solicitar la campaña.

Seleccione el tipo de interfaz web que se aplicará a las campañas creadas a partir de la plantilla:

![Configuración avanzada Ficha de marketing distribuido con lista de tipos de interfaz web: preestablecida, por resumen, por formulario, por formulario externo](assets/mkt_distr_1.png)

Hay cuatro tipos de interfaces web disponibles:

* **[!UICONTROL By brief]**: la entidad local debe proporcionar una descripción de las configuraciones de campaña. Una vez aprobada la solicitud, la entidad central se configura y ejecuta la campaña en su totalidad.

  ![Página web de pedidos de campaña para por una breve interfaz con campos de Segmentación y Descripción de contenido y el botón Validar](assets/mkt_distr_6.png)

* **[!UICONTROL By form]**: la entidad local tiene acceso a un formulario web en el que, según la plantilla utilizada, pueden editar el contenido, el objetivo, su tamaño máximo, así como la creación y extracción de fechas utilizando campos de personalización. La entidad local puede evaluar el destinatario y obtener una vista previa del contenido desde este formulario web.

  ![Formulario web de solicitud de campaña con fecha de contacto, canal preferido, segmento de edad, imagen, campos de mensaje y vínculos de evaluación](assets/mkt_distr_8.png)

  El formulario ofrecido se especifica en una aplicación web que debe estar seleccionada de la lista desplegable del campo **[!UICONTROL web Interface]** en el vínculo **[!UICONTROL Advanced campaign parameters...]** de la plantilla. Consulte [Creación de una campaña local (por formulario) &#x200B;](examples.md#creating-a-local-campaign--by-form-).

  >[!NOTE]
  >
  >La aplicación web utilizada es un ejemplo. Debe crear una aplicación web específica para poder utilizar un formulario.

  ![Configuración avanzada de la interfaz web que enumera aplicaciones web como la personalización de pedidos de Campaign](assets/mkt_distr_7.png)

* **[!UICONTROL By external form]**: la entidad local tiene acceso a los parámetros de campaña en su extranet (no en Adobe Campaign). Estos parámetros son idénticos a los de una campaña local (por formulario) o **local campaign (by form)**.
* **[!UICONTROL Pre-set]**: la entidad local solicita la campaña utilizando el formulario predeterminado sin localizarlo.

  ![Formulario de pedido de campaña con los campos Inicio, Fin, Asignado a, Revisor 1 y 2 y Descripción, y un botón Validar](assets/mkt_distr_5.png)

### Valores predeterminados {#default-values}


Seleccione los **[!UICONTROL Default values]** que desea completar en las entidades locales. Por ejemplo:

* fechas de contacto y extracción,
* características de objetivo (segmento de edad, etc.).

![Configuración avanzada Tabla de valores predeterminados con valores de canal preferido, fecha de contacto y cantidad solicitada](assets/mkg_dist_local_op_creation2.png)

Complete los campos **[!UICONTROL Parent marketing program]** y **[!UICONTROL Charge]**.

![Configuración avanzada con los campos Parent marketing program y Charge resaltados debajo de la tabla Valores predeterminados](assets/mkg_dist_local_op_creation3.png)

### Aprobaciones {#approvals}

Desde el vínculo **[!UICONTROL Advanced parameters for campaign entry]**, puede especificar el número máximo de revisores.

![Parámetros avanzados para el cuadro de diálogo de entrada de campaña con los campos Número de revisores y Número de documentos](assets/s_advuser_mkg_dist_add_valid_op1.png)

La entidad local deberá introducir los revisores cuando se solicite la campaña.

![Formulario de pedido de campaña con los campos Inicio, Fin, Asignado a, Revisor 1 y 2 y Descripción, y un botón Validar](assets/mkt_distr_5.png)

Si no desea asignar nombres a los revisores de una campaña, escriba 0.

### Documentos {#documents}

Puede permitir que los operadores de la entidad local vinculen documentos (archivos de texto, hojas de cálculo, imágenes, descripciones de campaña, etc.) a la campaña local al crear el pedido. El enlace **[!UICONTROL Advanced parameters for campaign entry...]** permite restringir el número de documentos. Para ello, simplemente introduzca el número máximo permitido en el campo **[!UICONTROL Number of documents]**.

![Número de documentos establecido en 2, número máximo de documentos definidos al crear el pedido](assets/s_advuser_mkg_dist_local_docs.png)

Al solicitar un paquete de campaña, el formulario sugiere vincular tantos documentos como se indica en el campo correspondiente de la plantilla.

![Formulario web de solicitud de campaña con los campos de carga de archivos Documento 1 y Documento 2, además de los campos de revisor y presupuesto](assets/s_advuser_mkg_dist_add_docs.png)

Si no desea mostrar un campo de carga de documento, escriba **[!UICONTROL 0]** en el campo **[!UICONTROL Number of documents]**.

>[!NOTE]
>
>El **[!UICONTROL Advanced parameters for campaign entry]** se puede desactivar marcando **[!UICONTROL Do not display the page used to enter the campaign parameters]**.

![Configuración avanzada con No mostrar la página utilizada para introducir la opción de parámetros de campaña activada](assets/s_advuser_mkg_dist_disable_op_parameters.png)

### Flujo de trabajo {#workflow}

En la pestaña **[!UICONTROL Targeting and workflows]**, cree el flujo de trabajo de campaña que recopila los **[!UICONTROL Default values]** especificados en **[!UICONTROL Advanced campaign parameters...]** y crea los envíos.

![Ficha Targeting and workflows con un flujo de trabajo predeterminado: query, Split, Email delivery y Deliver by direct mail](assets/mkg_dist_local_op_creation4b.png)

Haga doble clic en la actividad **[!UICONTROL Query]** para configurarla según el **[!UICONTROL Default values]** especificado.

![Actividad de consulta con el vínculo Editar consulta que abre un filtro en el que el segmento Edad es igual al segmento Edad del pedido actual](assets/mkt_dist_local_campaign_localize_query.png)

### Entrega {#delivery}

En la pestaña **[!UICONTROL Audit]**, haga clic en el icono **[!UICONTROL Detail...]** para ver el **[!UICONTROL Scheduling]** del envío seleccionado.

![Lista de envíos de la pestaña Auditoría con el botón Detalle al abrir una entrega cuyo icono Programación esté resaltado](assets/mkg_dist_local_op_creation4c.png)

El icono **[!UICONTROL Scheduling]** permite configurar la fecha de contacto y ejecución de la entrega.

![Cuadro de diálogo de programación con la opción Programar envío seleccionada y el cálculo de la fecha de contacto se basa en campos adicionales](assets/mkg_dist_local_op_creation4d.png)

Si es necesario, configure el tamaño máximo de la entrega:

![Cuadro de diálogo de configuración de exclusión con el campo Limitar envío a, abierto desde la pestaña Seleccionar exclusiones de destino](assets/mkg_dist_local_op_creation4e.png)

Localice el código HTML de la entrega. Por ejemplo, en **[!UICONTROL Delivery > Current order > Additional fields]**, utilice el campo **[!UICONTROL Age segment]** para localizar la entrega de acuerdo con la edad del objetivo.

![Cuadro de diálogo de selección de campos que muestra el campo de datos adicionales de código de segmento, insertado mediante Mensaje y otros](assets/mkt_dist_local_campaign_localize_html.png)

Guarde la plantilla de campaña. Ahora puede usarlo desde la vista **[!UICONTROL Campaign packages]** en la pestaña **[!UICONTROL Campaigns]**, haciendo clic en el botón **[!UICONTROL Create]**.

![Vista de paquetes de campañas con el botón Crear al abrir el cuadro de diálogo Paquete de campañas con plantilla y campaña de referencia](assets/mkt_distr_9.png)

>[!NOTE]
>
>Las plantillas de campaña y su configuración general se detallan en [Plantillas de campaña de marketing](../campaigns/marketing-campaign-templates.md).

## Creación del paquete de campaña {#creating-the-campaign-package}

Para que la plantilla de campaña esté disponible para las entidades locales, debe añadirla a la lista. Para ello, la agencia central necesita crear un nuevo paquete.

Siga estos pasos:

1. En la sección **[!UICONTROL Navigation]** de la página de **Campañas**, haga clic en el enlace **[!UICONTROL Campaign packages]**.
1. Haga clic en el botón **[!UICONTROL Create]**.

   ![Cuadro de diálogo del paquete de campaña con los campos Plantilla, Campaña de referencia, Etiqueta, Carpeta y Programación de ejecución](assets/mkg_dist_add_an_entry.png)

1. La sección encima de la ventana permite seleccionar la plantilla de paquete de campaña especificada [anteriormente](#creating-a-local-campaign-template).

   De forma predeterminada, la plantilla **[!UICONTROL New local campaign package (localEmpty)]** se utiliza para campañas locales.

1. Especifique la etiqueta, la carpeta y el programa de ejecución para el paquete de campaña.

### Fechas {#dates}

Las fechas de inicio y finalización definen el periodo de visibilidad de la campaña en la lista de paquetes de campañas.

La fecha de disponibilidad es la fecha en que la campaña estará disponible para las entidades locales (para que las soliciten).

>[!CAUTION]
>
>Si una entidad local no reserva la campaña antes de la fecha límite, no podrá utilizarla.

Esta información se encuentra en el mensaje de notificación enviado a las agencias locales, como se muestra a continuación:

![Nuevo correo electrónico de notificación de entrada al catálogo con el vínculo de solicitud de la campaña, la programación del paquete y la fecha de disponibilidad de la campaña](assets/s_advuser_mkg_dist_local_notif.png)

### Público {#audience}

Para una campaña local, la entidad central puede especificar las entidades locales involucradas en la comprobación de **[!UICONTROL Limit the package to a set of local entities]**.

![Cuadro de diálogo del paquete de campaña con la opción Limit the package to a set of local entities resaltada](assets/s_advuser_mkg_dist_create_mutual_entry3.png)

### Ajustes adicionales {#additional-settings}

Una vez guardado el paquete, la entidad central puede editarla desde la pestaña **[!UICONTROL Edit]**.

![Sección General de la pestaña Editar del paquete de campaña con el vínculo Parámetros de aprobación, Opciones de pedido y Programación de ejecución](assets/mkg_dist_edit_kit.png)

Desde la pestaña **[!UICONTROL General]**, la entidad central puede:

* configurar el revisor de paquetes de campañas desde el enlace **[!UICONTROL Approval parameters...]**,
* revisar la programación de ejecución,
* añadir o eliminar entidades locales.

>[!NOTE]
>
>De manera predeterminada, cada entidad puede solicitar una **campaña local** solo una vez.
>   
>Marque la opción **[!UICONTROL Enable multiple creation]** para permitir que se creen varias campañas locales en el paquete de campañas.

![Pestaña Editar paquete de campaña con la opción Habilitar creación múltiple activada y la lista de entidades locales](assets/mkg_dist_local_op_multi_crea.png)

### Notificaciones {#notifications}

Cuando una campaña está disponible o cuando se llega a la fecha límite de registro, se envía un mensaje a los operadores del grupo de notificación local. Para obtener más información, consulte [Entidades organizativas](about-distributed-marketing.md#organizational-entities).

## Solicitud de una campaña {#ordering-a-campaign}

Las entidades locales pueden acceder a los paquetes de campañas una vez que se han aprobado y ha comenzado su periodo de implementación. Las entidades locales reciben un correo electrónico que le informa de que hay un nuevo paquete de campaña disponible (en cuanto se alcanza su fecha de disponibilidad).

>[!NOTE]
>
>Si se especificaron entidades locales al crear el paquete de campaña, estas serán las únicas que recibirán una notificación. Si no se especifica ninguna entidad local, todas las entidades locales recibirán una notificación.

![Hay disponible un mensaje de correo electrónico que notifica un nuevo paquete, con los detalles del vínculo de la campaña y la programación del paquete](assets/mkg_dist_local_op_notification.png)

Para utilizar una campaña proporcionada por la entidad central, la entidad local debe solicitarla.

Para solicitar una campaña:

1. En el mensaje de notificación, haga clic en **[!UICONTROL Order campaign]** o en el botón correspondiente de Adobe Campaign.

   Introduzca su ID y contraseña para solicitar la campaña. La interfaz está formada por un conjunto de páginas definidas en una aplicación web.

1. Introduzca la información necesaria en la primera página (etiqueta de orden y comentario) y haga clic en **[!UICONTROL Next]**.

   ![Página web de pedidos de campaña con campos de número de pedido, entidad local, etiqueta de pedido y comentario de pedido y botón Siguiente](assets/mkg_dist_subscribe_step1.png)

1. Complete los parámetros disponibles y apruebe la solicitud.

1. Se envía una notificación al administrador de la entidad organizativa a la que pertenece la entidad local para aprobar la solicitud.

   ![Solicitar la página web de aprobación con las opciones Aceptar y Rechazar, el campo Comentario y el botón Aprobación](assets/mkg_dist_subscribe_step3.png)

1. La información se devuelve a las entidades local y central. Aunque las entidades locales solo pueden ver sus propias solicitudes, la entidad central puede ver todas las solicitudes de cualquier entidad local, como se muestra a continuación:

   ![La pestaña Pedidos del paquete de campaña enumera cuatro pedidos de ventas de verano con las fechas de inicio, finalización y estado disponible](assets/mkg_dist_subscribe_central_view.png)

   Los operadores pueden mostrar detalles de la solicitud:

   ![Se ha abierto el panel de pedidos desde la lista Pedidos con el estado, el paquete de campaña, la entidad local y los detalles de campaña](assets/mkg_dist_local_op_catalog_detail_1.png)

   La pestaña **[!UICONTROL Edit]** contiene información introducida por la entidad local al solicitar la campaña.

   ![Ficha Modificar pedido con etiqueta, entidad organizativa, estado y el comentario introducido por la entidad local](assets/mkg_dist_local_op_catalog_detail_1b.png)

1. La entidad central debe aprobar la solicitud.

   ![Panel de pedidos con estado de aprobación pendiente y el botón Aprobar suscripción](assets/mkg_dist_local_op_catalog_detail_3.png)

   Para obtener más información, consulte la sección [Proceso de aprobación](#approval-process).

1. El operador local recibe una notificación cuando la campaña está disponible: la disponibilidad de la campaña puede encontrarse en la lista de paquetes de campañas en la pestaña **Campaign**. La campaña entonces se puede utilizar. Para obtener más información, consulte [Acceso a campañas](accessing-campaigns.md).

   La opción **[!UICONTROL Start targeting with order approval]** permite que la entidad local ejecute la campaña en cuanto se apruebe la solicitud.

   ![Lista de paquetes de campaña en la ficha Campañas con un paquete local publicado disponible para su uso](assets/mkg_dist_local_op_catalog_use.png)

## Aprobación de una solicitud {#approving-an-order}

Para confirmar una solicitud de campaña, la entidad central debe aprobarla.

La vista general de **[!UICONTROL Campaign orders]**, a la que se accede a través de la pestaña **Campañas**, permite ver el estado de las solicitudes de campaña y aprobarlas.

>[!NOTE]
>
>Las entidades locales pueden realizar cambios en la solicitud hasta que se apruebe.

### Proceso de aprobación {#approval-process}

#### Notificación por correo electrónico {#email-notification}

Cuando una entidad local solicita una campaña, sus revisores reciben notificaciones por correo electrónico, como se muestra a continuación:

![Aprobación del correo electrónico de solicitud de campaña con vínculo de aceptación o rechazo, detalles del pedido y del paquete y plazos](assets/mkg_dist_valid_notif_email.png)

>[!NOTE]
>
>Para saber cómo seleccionar revisores, consulte la sección [Revisores](#reviewers). Pueden aceptar o rechazar la solicitud.

![Solicitar página web de aprobación con la opción Aceptar seleccionada, un comentario y el botón Aprobación](assets/mkg_dist_command_valid_web.png)

#### Aprobación mediante la consola de cliente {#approving-via-the-adobe-campaign-console}

Las solicitudes también se pueden aprobar a través de la consola del cliente, en la descripción general de la solicitud de la campaña. Para aprobar una solicitud, selecciónela y haga clic en **[!UICONTROL Approve the order]**.

![Panel de pedidos en la consola con el botón Aprobar suscripción que abre el cuadro de diálogo Aceptar o rechazar aprobación](assets/mkg_dist_local_order_valid.png)

>[!NOTE]
>
>La campaña todavía se puede editar y volver a configurar hasta que se alcance la fecha de disponibilidad de la campaña. Las entidades locales también pueden rechazar la campaña haciendo clic en el botón **[!UICONTROL Cancel]**.

#### Creación de una campaña {#creating-a-campaign}

Una vez aprobada la solicitud de una campaña, la entidad local puede configurarla y ejecutarla.

![Lista de paquetes de campaña con los estados Aprobado, Rechazado y En proceso de edición; se está haciendo clic en el vínculo de campaña](assets/mkg_dist_mutual_op_created.png)

Para obtener más información, consulte [Acceso a campañas](accessing-campaigns.md).

### Rechazar una aprobación {#rejecting-an-approval}

El operador de aprobación puede rechazar una solicitud o un paquete de campaña.

![Cuadro de diálogo Acción en el paquete con la opción Rechazar seleccionada, un campo Comentario y el botón Aprobación](assets/mkg_dist_do_not_valid.png)

Si el revisor rechaza una solicitud, se envía la notificación correspondiente automáticamente a las respectivas entidades locales: muestra el comentario introducido por el operador que rechazó la aprobación.

La información se muestra en la lista de página de paquetes de campañas o en la página de solicitud de campañas. Si tienen acceso a la consola del cliente de Adobe Campaign, se informa a las entidades locales de este rechazo.

![Lista de paquetes de campaña con el distintivo de estado Rechazado resaltado en un paquete de campaña local](assets/mkg_dist_do_not_valid_view.png)

Pueden ver el comentario relacionado en la pestaña **[!UICONTROL Edit]** del paquete de campaña.

![Pestaña Auditoría de paquete de campaña con diario de aprobaciones que muestra una acción rechazada, con columna Comentario](assets/mkg_dist_do_not_valid_tab.png)

### Revisores {#reviewers}

Cada vez que se necesita una aprobación, los revisores reciben una notificación por correo electrónico.

Para cada entidad local, se seleccionan los revisores para la aprobación de solicitudes y campañas. Para obtener más información sobre la selección de revisores locales, consulte [Entidades organizativas](about-distributed-marketing.md#organizational-entities).

>[!NOTE]
>
>Para que esta selección sea posible, la aprobación de solicitudes no debe ser eficaz.

### Cancelación de una solicitud {#canceling-an-order}

La agencia central puede cancelar una solicitud utilizando el botón **[!UICONTROL Delete]** situado en el panel de control de solicitudes.

![Panel del paquete de campaña con el menú Acciones en un pedido y la opción Eliminar resaltada](assets/mkg_dist_local_op_cancel.png)

Esto cancela la campaña en la vista **[!UICONTROL Campaign orders]**.
