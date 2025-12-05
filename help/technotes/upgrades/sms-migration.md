---
title: Cambio al nuevo conector SMS v2
description: Aprenda a pasar al nuevo conector de SMS v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 30ab5a10f17baddfc455dc406a4f31f058ea05ba
workflow-type: tm+mt
source-wordcount: '222'
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
