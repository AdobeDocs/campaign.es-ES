---
title: Envío de correos directos con Adobe Campaign
description: Introducción al correo directo en Campaign
feature: Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 64%

---

# Creación de envíos de correo directo

Las entregas de correo postal permiten generar un archivo de extracción que contenga datos sobre la población objetivo. A continuación, puede compartir este archivo con el proveedor que enviará los mensajes a las poblaciones objetivo.

Los pasos para generar el archivo son los siguientes:

1. [Creación del envío](#creating-a-direct-mail-delivery)
1. [Definición del público](#defining-the-direct-mail-audience)
1. [Definición del contenido del archivo](#defining-the-direct-mail-content)
1. [Validación del envío](#validating)
1. [Inicio de la entrega](#start-delivery)

## Creación del envío{#creating-a-direct-mail-delivery}

Cree una entrega de correo directo basado en la plantilla. Puede duplicar y configurar la plantilla integrada **[!UICONTROL Deliver by direct mail (paper)]**.

Para crear una nueva envío de correo directo, siga los pasos a continuación:

>[!NOTE]
>
>En [esta sección](../start/create-message.md) se exponen conceptos globales sobre la creación de envíos.

1. Cree un nuevo envío, por ejemplo, desde el panel de control Envío.
1. Seleccione la plantilla de envío **Enviar por correo directo (papel)**.

   ![](assets/direct_mail.png)

1. Identifique su entrega con una etiqueta, un código y una descripción. Para obtener más información, consulte [esta sección](../start/create-message.md#create-the-delivery).
1. Haga clic en **Continuar** para confirmar esta información y mostrar la ventana de configuración de mensajes.

## Definición del público{#defining-the-direct-mail-audience}

Los perfiles de destinatario deben contener al menos sus nombres y direcciones postales.

Las direcciones postales son campos calculados. Una dirección puede contener de forma predeterminada hasta seis líneas: la primera contiene el nombre y los apellidos, las líneas siguientes contienen la dirección postal (calle, etc.) y la última línea contiene el código postal y el municipio o ciudad. La definición del campo postalAddress calculado predeterminado se puede revisar en el esquema nms:recipient.

Se considera que una dirección está completa si el nombre, el campo de código postal y el campo de municipio o ciudad no están vacíos. Los destinatarios con direcciones incompletas se excluirán de los envíos de correo directo.

Obtenga más información en [esta sección](../start/create-message.md#target-population).

## Definición del contenido del archivo{#defining-the-direct-mail-content}

Utilice el asistente de extracción para definir la información (columnas) que se exportarán en el archivo de salida.

El nombre del archivo que contiene los datos extraídos se define en el campo **[!UICONTROL File]**. El botón situado a la derecha del campo permite utilizar campos personalizados para crear el nombre del archivo.

De forma predeterminada, el archivo de extracción se crea y se almacena en el servidor. Puede guardarlo en el equipo. Para ello, marque la **[!UICONTROL Download the generated file after the analysis of the delivery]**. En este caso, es necesario indicar la ruta de acceso al directorio de almacenamiento local así como al nombre de archivo.

![](assets/s_ncs_user_mail_delivery_local_file.png)

Para una entrega de correo directo, el contenido de la extracción se define en el vínculo **[!UICONTROL Edit the extraction file format...]**.

![](assets/s_ncs_user_mail_delivery_format_link.png)

Este vínculo le permite acceder al asistente de extracción y definir la información (columnas) que se va a exportar en el archivo de salida.

![](assets/s_ncs_user_mail_delivery_format_wz.png)

Puede insertar una URL personalizada en el archivo de extracción. Para obtener más información, consulte la [documentación](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/publishing-a-web-form.html?lang=es){target="_blank"} de Adobe Campaign Classic.

>[!NOTE]
>
>Este asistente incluye los pasos del asistente de exportación detallados en Adobe Campaign Classic [documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-export-jobs.html?lang=es){target="_blank"}.

## Validación del envío{#validating}

Compruebe el resultado del análisis y el contenido del archivo de salida.

En el contexto de una campaña de marketing, en la fecha de extracción se crea el archivo de extracción. Puede ver el contenido del archivo extraído, aprobarlo o cambiar el formato y volver a iniciar la extracción si es necesario. Una vez aprobado el archivo, puede enviar el correo electrónico de notificación al enrutador. Obtenga más información en [esta página](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=es){target="_blank"}.

Los conceptos globales al validar una entrega se presentan en [esta sección](../start/create-message.md#validate-the-delivery).

El archivo de salida de una entrega de correo directo se genera durante el análisis de la entrega. El contenido del archivo depende de las columnas de salida seleccionadas (consulte este [archivo de sección](#defining-the-direct-mail-content)).

>[!NOTE]
>
>La fase de análisis se detalla en esta [sección](delivery-analysis.md).

El archivo se genera durante la fase de análisis; sin embargo, la información sobre los destinatarios (es decir, “logs” de envío) no se actualiza. Así se puede cancelar este trabajo sin correr ningún riesgo.

Compruebe el resultado del análisis y el contenido del archivo de salida antes de hacer clic en **[!UICONTROL Confirm delivery]**. Un mensaje de confirmación permite iniciar la entrega.

La confirmación de la entrega inicia la extracción de datos en el archivo especificado.

![](assets/s_ncs_user_postal_del_send_confirm_postal.png)

A continuación, puede cerrar el asistente y ver los registros de envío a través de la pestaña **[!UICONTROL Delivery]**, a la que se puede acceder a través de los detalles de envío.

Se puede configurar el modo de recuperación de “logs” de envío desde la pestaña **[!UICONTROL Analysis]** de las propiedades de envío.

Existen dos modos:

* **[!UICONTROL Messages are considered sent after validation]** (modo predeterminado): en este modo de función, todos los broadlogs se actualizan cuando el operador confirma la entrega (su estado pasa de “Envío pendiente” a “Enviado”) y la entrega se establece automáticamente como **[!UICONTROL Finished]**.
* **[!UICONTROL A file of results determines the messages that are sent and those that have failed]**: este modo permite actualizar los broadlogs a través de un archivo externo enviado por el proveedor de servicios. En este caso, se debe utilizar un flujo de trabajo que procese esta información para actualizar el estado del broadlog.

  >[!NOTE]
  >
  >En este caso, el usuario debe cambiar también el estado a **[!UICONTROL Finished]** en cuanto se actualicen los broadlogs.

## Inicio de la entrega{#start-delivery}

Una vez validado el archivo de extracción, haga clic en **Confirmar entrega**; un mensaje de confirmación le permite iniciar la entrega.

La confirmación inicia la extracción de datos en el archivo especificado.

En el contexto de una campaña de marketing, cuando se han concedido todas las aprobaciones, los archivos de extracción se crean mediante un flujo de trabajo especial que, en una configuración predeterminada, se inicia automáticamente cuando una entrega de correo directo está pendiente de extracción. Obtenga más información en [esta sección](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=es){target="_blank"}.
