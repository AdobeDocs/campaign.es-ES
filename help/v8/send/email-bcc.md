---
title: Envíe una copia de sus mensajes a una dirección de CCO
description: Obtenga información sobre cómo activar el CCO del correo electrónico en Adobe Campaign
feature: Email
role: User
level: Beginner
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# Envíe una copia de sus mensajes a una dirección de CCO {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## Acerca del CCO de correo electrónico {#gs-bcc}

Puede configurar Adobe Campaign para que conserve una copia de los correos electrónicos enviados desde su plataforma. Esta opción le permite enviar mensajes a una dirección de correo electrónico específica de CCO (copia oculta), desde la que se pueden procesar y archivar mediante un sistema externo.
Adobe Campaign no administra los archivos archivados. Los archivos .eml correspondientes a los correos electrónicos enviados se pueden transferir a un servidor remoto, como un servidor de correo electrónico SMTP.

El destino de archivado es la dirección de correo electrónico CCO que elija, que permanece invisible para los destinatarios de la entrega. Una vez definida la dirección de correo electrónico de CCO, debe activar la opción dedicada en [plantilla de envíos](create-templates.md) nivel.

>[!NOTE]
>
>Como usuario de Managed Cloud Service, [Adobe de contacto](../start/campaign-faq.md#support){target="_blank"} para comunicar la dirección de correo electrónico CCO que se utilizará para el archivado.

>[!CAUTION]
>
>Por motivos de privacidad, los correos electrónicos CCO deben procesarse mediante un sistema de archivado capaz de almacenar información de identificación personal (PII) de forma segura.


## Activar CCO de correo electrónico {#enable-bcc}

Para habilitar CCO para un elemento específico [plantilla de envíos](create-templates.md), siga los pasos a continuación:

1. Desde el explorador de Campaign, vaya a la carpeta de plantillas de envío. De forma predeterminada, las plantillas de envío se almacenan en la variable **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** carpeta.
1. Edite la plantilla de envío para actualizarla con CCO.
1. Haga clic en el botón **[!UICONTROL Properties]**.
1. Desde el **[!UICONTROL Delivery]** pestaña, marque la **[!UICONTROL Email BCC]** opción.

   ![](assets/email-bcc.png)

1. Haga clic en **[!UICONTROL Ok]** para confirmar.

Se enviará una copia de todos los mensajes enviados para cada envío en función de esta plantilla a la dirección de CCO de correo electrónico que se haya configurado para su plataforma.

## Protecciones y recomendaciones {#recommendations-bcc}

Al utilizar CCO del correo electrónico con Adobe Campaign, se aplican las siguientes protecciones y recomendaciones:

* Solo puede utilizar una dirección de correo electrónico CCO.

* Asegúrese de que la dirección de CCO tenga suficiente capacidad de recepción para archivar todos los correos electrónicos enviados.

* Correo electrónico CCO <!--with Enhanced MTA--> envía a la dirección de correo electrónico CCO antes de enviar a los destinatarios, lo que puede dar como resultado que se envíen mensajes CCO aunque los envíos originales puedan haber rebotado. Para obtener más información sobre las devoluciones, consulte [Comprensión de errores de entrega](delivery-failures.md).

* Los correos electrónicos enviados a la dirección de CCO no se deben abrir ni hacer clic en ellos, ya que estas actividades se tienen en cuenta en la **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, puede provocar errores de cálculo.

<!--Only successfully sent emails are taken in account, bounces are not.-->
