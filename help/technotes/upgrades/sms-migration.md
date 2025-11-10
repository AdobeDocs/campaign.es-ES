---
title: Cambio al nuevo conector SMS v2
description: Aprenda a pasar al nuevo conector de SMS v2
feature: Technote
role: Admin
hide: true
hidefromtoc: true
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 784c74aaff23dbf1f35c6e8153f90610048e1c07
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Cambio al nuevo conector SMS v2

Este documento describe el procedimiento y las consideraciones clave al migrar del conector SMS basado en MTA al nuevo **conector de proceso SMS dedicado** en Adobe Campaign v8.

## Por qué cambiar al conector v2

El proceso de SMS dedicado introduce compatibilidad con el modo de transceptor SMPP, reduce el recuento de conexiones y mejora la eficacia de los recursos, a la vez que sigue admitiendo configuraciones de transmisores/receptores si es necesario. Ofrece una estabilidad significativamente mayor, con una recuperación más rápida de errores, conexiones persistentes y sin dependencia en los archivos locales ni en la comunicación entre procesos. También se mejora el rendimiento, con una menor latencia, un mayor rendimiento y un microagrupamiento inteligente para equilibrar la velocidad y la fiabilidad. Además, el aislamiento del proceso de SMS simplifica la resolución de problemas y minimiza el impacto en canales múltiples. Estas mejoras hacen que el conector dedicado sea una solución más sólida y escalable para la entrega de SMS.

## Diferencias entre los conectores v1 y v2

El conector SMS específico de Adobe Campaign v8 introduce varios cambios de arquitectura en comparación con el conector basado en MTA. Una diferencia clave es el uso predeterminado del modo de transceptor SMPP, que reduce el número de conexiones combinando las funciones de envío y recepción. Si el proveedor no admite este modo, aún es posible utilizar conexiones independientes de transmisores y receptores. A diferencia del conector de MTA, la activación de respuestas automáticas no afecta al recuento de conexiones y todas las conexiones del receptor pueden gestionar cualquier tipo de mensaje entrante.

El recuento de conexiones ahora se calcula con una fórmula diferente:

```
Total connections = SMS sending threads * Number of MTA child connections. 
```

El parámetro sendingThreads, definido en serverConf, tiene el valor predeterminado 1 y, por lo general, debe permanecer sin cambios a menos que se optimice específicamente para obtener un alto rendimiento. Dado que un solo proceso gestiona todo el tráfico de SMS, la administración del paralelismo a través de estos parámetros se vuelve crítica para controlar la carga y el comportamiento del sistema.

La ventana de envío se comporta de manera similar al conector de MTA, pero tiene un impacto aún mayor en el rendimiento en el modo dedicado. Las ventanas de envío más grandes reducen las IOPS de la base de datos y mejoran el rendimiento. Campaign puede gestionar de forma eficaz ventanas de más de 1000 mensajes, siempre que el proveedor lo admita y el caso de uso permita un pequeño margen de pérdida o duplicación de mensajes en caso de problemas de conexión. En el lado del proveedor, configurar una ventana de envío SR más grande también puede mejorar significativamente el rendimiento del informe de envío.

Por último, mientras que la gestión de mensajes MO (móvil original) permanece sin cambios funcionales, se ha actualizado el código subyacente. El rendimiento por conexión sigue estando limitado del mismo modo, pero el conector dedicado permite un envío de ráfaga mucho más rápido. Sin embargo, sin límites de rendimiento, el envío de alta velocidad puede saturar los recursos del proveedor o del sistema, lo que recomienda establecer límites explícitos de rendimiento de MT en la configuración de cuenta externa.

## Procedimiento de cambio

Para garantizar un cambio suave al proceso de SMS dedicado, es mejor realizar la operación durante un tráfico de SMS bajo o nulo. Algunos mensajes almacenados en el búfer pueden perderse o dejarse en un estado no válido si los búferes de MTA no se vacían por completo. También es normal perder algunos SR durante una semana después del cambio, debido a un tiempo de SR impredecible. El no seguir estas precauciones puede provocar la pérdida o duplicación de mensajes, a pesar de las protecciones integradas.

Ambos conectores SMS utilizan formatos diferentes para el procesamiento de SR (informe de estado). Aunque ambos dependen de la tabla `NmsProviderMsgId`, interactúan con ella de forma diferente. Por lo tanto, para cambiar de conector es necesario borrar toda la tabla para evitar conflictos o datos huérfanos. Existen varias formas de realizar esta limpieza. A continuación se muestran las consultas SQL que puede utilizar:

```
TRUNCATE TABLE NmsProviderMsgId;
TRUNCATE TABLE NmsProviderMsgStatus;
```

### Pasos

1. Revisar la configuración de `serverConf` (`sms > mta2`).
1. Pausar el flujo de trabajo de preparación de mensajes en tiempo real (si corresponde).
1. Pausar todos los envíos SMS.
1. Deshabilite la cuenta externa de SMS.
1. Detenga y reinicie los procesos de MTA y SMS.
1. Asegúrese de que no haya conexiones SMPP activas. Si está presente, asegúrese de que todos los envíos estén en pausa.
1. Borrar el contenido de las tablas `NmsProviderMsgId` y `NmsProviderMsgStatus` de la base de datos.
1. En la cuenta externa:
   * Active la casilla &quot;Proceso dedicado&quot;
   * Ajustar otras configuraciones: conexiones secundarias MTA, rendimiento MT, ventana de envío
1. Vuelva a habilitar la cuenta externa y guarde los cambios.
1. Reanudar envíos de SMS.
1. Compruebe que los servicios SMS funcionan normalmente.

>[!NOTE]
>
>Monitorice los registros secundarios de SMS, MTA y MTA para detectar errores o problemas.
>
>Guarde la configuración anterior de la cuenta externa para revertirla.

### Procedimiento de reversión

Es posible volver al conector MTA siguiendo los mismos pasos utilizados durante el cambio inicial, en el mismo orden. Esto incluye detener o pausar todos los envíos SMS y restaurar la configuración original de la cuenta externa.

1. Si la instancia utiliza envíos en tiempo real, ponga en pausa el flujo de trabajo técnico responsable de preparar esos mensajes.
1. Pausar todos los envíos SMS.
1. Deshabilite la cuenta externa de SMS.
1. Detenga y reinicie los procesos de MTA y SMS.
1. Asegúrese de que ninguna conexión SMPP permanezca activa; si lo hace, compruebe que todas las entregas estén correctamente en pausa.
1. Borrar las tablas `NmsProviderMsgId` y `NmsProviderMsgStatus` de la base de datos.
1. En la cuenta externa:
   * Desmarque la opción &quot;proceso dedicado&quot; en la cuenta externa.
   * Restaure todas las configuraciones de cuenta externa anteriores: conexiones secundarias MTA, rendimiento MT, ventana de envío
1. Vuelva a habilitar y guarde la cuenta externa.
1. Reanudar todos los envíos SMS.
1. Finalmente, confirme que los servicios SMS funcionan normalmente.
