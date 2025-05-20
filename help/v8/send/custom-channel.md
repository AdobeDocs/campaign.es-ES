---
title: Introducción a los canales externos personalizados
description: Obtenga información sobre cómo crear y enviar envíos de canales externos personalizados con Adobe Campaign Web
role: User
level: Beginner, Intermediate
source-git-commit: 4ba419c52d6804e4f25f88990c226081ef0a06e6
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# Introducción a los canales externos personalizados {#gs-custom-channel}

Adobe Campaign le permite crear canales externos personalizados integrados con terceros. A continuación, puede orquestar y ejecutar envíos basados en estos canales.

La creación y la entrega de envíos se pueden realizar tanto en la consola del cliente como en la interfaz de usuario web. Sin embargo, el canal externo personalizado solo se realiza en la consola del cliente.

Para obtener información sobre cómo crear y realizar un envío basado en un canal externo personalizado, consulte esta [página](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html).

Estos son los pasos para crear un nuevo canal personalizado externo en la consola del cliente:

1. Configure el esquema [más información](#configure-schema)
1. Crear una nueva cuenta externa, [leer más](#create-ext-account)
1. Crear una nueva plantilla de envíos, [leer más](#create-template)

## Configuración del esquema{#configure-schema}

En primer lugar, se debe configurar el esquema para añadir el nuevo canal a la lista de canales disponibles.

1. En el explorador de Campaign, seleccione **Administración** > **Configuración** > **Esquemas de datos**.

1. Cree una extensión de esquema para ampliar la enumeración messageType con el nuevo canal.

   Por ejemplo:

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## Cree una nueva cuenta externa{#create-ext-account}

A continuación, debe crear una nueva cuenta externa de enrutamiento.

1. En el explorador de Campaign, seleccione **Administración** > **Plataforma** > **Cuentas externas**.

1. Cree una nueva cuenta externa.

1. Seleccione el canal y cambie el modo de envío a **Externo**.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Creación de una nueva plantilla de envíos{#create-template}

Ahora, vamos a crear la nueva plantilla asociada al nuevo canal.

1. En el explorador de Campaign, seleccione **Recursos** > **Plantillas** > **Plantillas de envío**.

1. Cree una nueva plantilla.

1. Haga clic en **Propiedades** y seleccione la carpeta y el enrutamiento correctos.

   ![](assets/cus-template.png){zoomable="yes"}

El nuevo canal ya está disponible. Puede crear y ejecutar envíos basados en este canal.


