---
title: Conectores SMS
description: Obtenga información acerca de los conectores SMS en Adobe Campaign
feature: SMS
role: User, Admin
level: Intermediate
exl-id: 5ec3f172-22dc-458b-8688-9974009c985e
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%
---
# Acerca de los tipos de conectores SMS {#sms-connectors}

Adobe Campaign admite dos conectores SMS utilizados para enviar mensajes SMS a sus clientes:

* **Conector SMS heredado**: Primera versión del conector utilizado en Campaign v7 y versiones anteriores de Campaign v8. [Más información](#legacy-sms-connector)
* **Conector SMS v2**: disponible en GA a partir de la versión 8.9.1 de Campaign, este conector SMS dedicado de la versión 2 se ha modernizado para ofrecer un rendimiento y una fiabilidad mejorados. [Más información](#sms-connector-v2)

## Conector de SMS heredado {#legacy-sms-connector}

El conector SMS heredado es el conector SMS basado en MTA utilizado en versiones anteriores de Adobe Campaign. Este conector sigue siendo compatible con las implementaciones existentes, pero Adobe recomienda encarecidamente actualizar a la versión 8.9.1 o posterior para beneficiarse del rendimiento y la fiabilidad mejorados del conector v2.

Para obtener más información sobre cómo aprovechar el conector v2, consulte la sección [Activation](#activation).

Para obtener información detallada acerca de la configuración y el uso del conector SMS heredado, consulte la [documentación de Campaign Classic](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## Conector de SMS v2 {#sms-connector-v2}

Disponible en GA a partir de la versión 8.9.1, el conector v2 permite conexiones SMPP en modo transceptor, conexiones SMPP persistentes y garantiza una mejor compatibilidad. Hay disponible una cuenta externa de SMS dedicada para todas las implementaciones de SMS mediante el conector v2.

El conector v2 está habilitado de forma predeterminada para las nuevas instalaciones. Si ha actualizado desde una versión anterior utilizando el conector heredado, debe ponerse en contacto con su representante de Adobe para cambiar al conector v2. Consulte la sección [Activación](#activation).

Para aprender a utilizar el conector SMS v2 en Campaign v8, consulte la [documentación de SMS](sms.md).

>[!NOTE]
>
>El conector v2 también está disponible en las siguientes compilaciones con algunas restricciones:
>* 8.8.1: versión para todos los entornos de FDA de Campaign. No disponible para implementaciones de FDAC de Campaign.
>* 8.8.2: versión para todos los tipos de implementación, incluido FDAC. Publicado en disponibilidad limitada (LA).

## Activación {#activation}

### Por qué cambiar al conector v2 {#why-switch-v2}

El proceso de SMS dedicado introduce compatibilidad con el modo de transceptor SMPP, reduce el recuento de conexiones y mejora la eficacia de los recursos, a la vez que sigue admitiendo configuraciones de transmisores/receptores si es necesario. Ofrece una estabilidad significativamente mayor, con una recuperación más rápida de errores, conexiones persistentes y sin dependencia en los archivos locales ni en la comunicación entre procesos. También se mejora el rendimiento, con una menor latencia, un mayor rendimiento y un microagrupamiento inteligente para equilibrar la velocidad y la fiabilidad. Además, el aislamiento del proceso de SMS simplifica la resolución de problemas y minimiza el impacto en canales múltiples. Estas mejoras hacen que el conector dedicado sea una solución más sólida y escalable para la entrega de SMS.

### Configuración {#configuration}

Con Adobe Campaign Managed Cloud Services, la configuración del servidor y la migración del conector SMS se administran mediante Adobe. Este procedimiento técnico requiere acceso directo a los archivos de configuración del servidor y a las operaciones de la base de datos.

Para activar y empezar a utilizar el conector SMS v2, primero debe actualizar a la versión 8.9.1 o posterior. Póngase en contacto con su representante de Adobe o con el Servicio de atención al cliente de Adobe. Programarán y realizarán las actualizaciones necesarias para su instancia.
