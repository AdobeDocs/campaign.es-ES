---
title: Cambio al nuevo conector SMS v2
description: Aprenda a pasar al nuevo conector de SMS v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%
---
# Cambio al nuevo conector SMS v2

La versión 8 de Adobe Campaign presenta un nuevo **conector de proceso SMS dedicado** (v2), que ofrece un rendimiento y una fiabilidad mejorados en comparación con el conector de SMS basado en MTA heredado.

## Por qué cambiar al conector v2

El proceso de SMS dedicado introduce compatibilidad con el modo de transceptor SMPP, reduce el recuento de conexiones y mejora la eficacia de los recursos, a la vez que sigue admitiendo configuraciones de transmisores/receptores si es necesario. Ofrece una estabilidad significativamente mayor, con una recuperación más rápida de errores, conexiones persistentes y sin dependencia en los archivos locales ni en la comunicación entre procesos. También se mejora el rendimiento, con una menor latencia, un mayor rendimiento y un microagrupamiento inteligente para equilibrar la velocidad y la fiabilidad. Además, el aislamiento del proceso de SMS simplifica la resolución de problemas y minimiza el impacto en canales múltiples. Estas mejoras hacen que el conector dedicado sea una solución más sólida y escalable para la entrega de SMS.

## Configuración

Con Adobe Campaign Managed Cloud Services, la configuración del servidor y la migración del conector SMS se administran mediante Adobe. Este procedimiento técnico requiere acceso directo a los archivos de configuración del servidor y a las operaciones de la base de datos.

Si necesita migrar al nuevo conector SMS v2, póngase en contacto con su representante de Adobe o con el Servicio de atención al cliente de Adobe. Programarán y realizarán las actualizaciones necesarias para su instancia.

Para obtener más información sobre el canal SMS en Campaign v8, consulte la [documentación de SMS](../../v8/send/sms/sms.md).
