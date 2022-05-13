---
title: Understand Campaign Interaction architecture
description: Campaign Interaction Architecture basics
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7a710960-7e41-4462-bd5e-18e874aa46f8
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '1314'
ht-degree: 66%

---

# Understand Campaign Interaction environments and architecture

## Environments {#environments}

Para cada dimensión de segmentación existen dos entornos utilizados al gestionar las ofertas:

* **** The rules for each category, the offer spaces on which offers can be presented, and the pre-defined filters used to define an offer&#39;s eligibility are also defined in this environment.

   Las categorías también se pueden publicar manualmente en el entorno en línea.

   [](interaction-offer.md#approve-offers)

* **** During a call to the Offer engine, the engine will always use offers from the live environment.

Una oferta solo se implementa en los espacios de oferta seleccionados durante el proceso de aprobación. Por lo tanto, una oferta puede estar activa pero no puede utilizarse en un espacio de oferta que también esté activo.

## Inbound and outbound interactions {#interaction-types}

The Adobe Campaign Interaction module proposes two types of interactions:

* **** [Más información](interaction-present-offers.md)
* **** [Más información](interaction-send-offers.md)

******** Por lo general, las interacciones entrantes se realizan en modo unitario y las interacciones salientes se llevan a cabo en modo agrupado. [](../send/transactional.md)

As soon as an offer can or must be presented (according to the configurations carried out), the Offer engine plays the intermediary role: it automatically calculates the best possible offer for a contact among those available by combining data received about the contact and the different rules that can be applied as specified in the application.

![](assets/architecture_interaction2.png)

## Arquitectura distribuida

**** [](../architecture/architecture.md#transac-msg-archi)

* una o varias instancias de control dedicadas al canal saliente y que contienen la base de diseño de entorno y mercadotecnia.
* una o varias instancias de ejecución dedicadas al canal entrante

![](assets/interaction_powerbooster_schema.png)

Las instancias de control están dedicadas al canal entrante y contienen la versión en línea del catálogo. Cada instancia de ejecución es independiente y está dedicada a un segmento de contacto (por ejemplo, una instancia de ejecución por país). Calls to the Offer engine must be directly performed on the execution (one specific URL per execution instance). Como la sincronización entre instancias no es automática, las interacciones del mismo contacto deben enviarse a través de la misma instancia.

### Synchronization {#synchronization}

La sincronización de ofertas se lleva a cabo mediante paquetes. En instancias de ejecución, todos los objetos de catálogo están prefijados con el nombre de cuenta externo. Esto significa que se pueden admitir varias instancias de control (instancias de desarrollo y producción por ejemplo) en una misma instancia de ejecución.

>[!CAUTION]
>
>Use short and explicit internal names.

Las ofertas se implementan automáticamente y se publican en instancias de ejecución y control.

Las ofertas eliminadas en el entorno de diseño se desactivan en todas las instancias en línea. Las propuestas y ofertas obsoletas se eliminan automáticamente en todas las instancias después del periodo de depuración (especificado en el asistente de implementación de cada instancia) y de deslizamiento (especificado en las reglas de tipología de propuestas entrantes).

![](assets/interaction_powerbooster_schema2.png)

Se crea un flujo de trabajo para cada entorno y cuenta externa para la sincronización de propuestas. La frecuencia de sincronización se puede ajustar para cada entorno y cuenta externa.

You must be aware of the following synchronization mechanisms:

* Si se utiliza la función de reserva de un entorno anónimo a un entorno identificado, estos dos entornos deben estar en la misma instancia de ejecución.
* La sincronización entre varias instancias de ejecución no se realiza en tiempo real. Las interacciones del mismo contacto deben enviarse a la misma instancia. La instancia de control debe estar dedicada al canal saliente (sin tiempo real).
* La base de datos de mercadotecnia no se sincroniza automáticamente. Los datos de mercadotecnia utilizados en las ponderaciones y reglas de elegibilidad deben duplicarse en las instancias de ejecución. Este proceso no se considera estándar, se debe desarrollarlo durante el periodo de integración.
* La sincronización de propuestas se realiza exclusivamente mediante la conexión FDA.
* Si se utiliza interacción y centro de mensajes en la misma instancia, la sincronización se va a producir mediante el protocolo FDA en ambos casos.

### Configuración de paquetes {#packages-configuration}

Las extensiones de esquema directamente vinculadas a **interaction** (ofertas, propuestas, destinatarios, etc.) deben implementarse en las instancias de ejecución.

**** Two additional packages are available: one package for the control instances, and the other for each execution instance.

>[!NOTE]
>
>Al instalar el paquete, los campos de tipo **long** de la tabla **nms:proposition**, como el ID de la propuesta, se convierten en campos de tipo **int64.** [](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html?lang=en#mapping-the-types-of-adobe-campaign-dbms-data)

**[!UICONTROL Data purge]** En instancias de ejecución, este periodo debe corresponder a la profundidad histórica necesaria para las reglas de tipología (punto de deslizamiento) y para las reglas de idoneidad que se van a calcular.

En las instancias de control:

1. Create one external account per execution instance:

   ![](assets/interaction_powerbooster1.png)

   * Complete la etiqueta y añada un nombre interno corto y explícito.
   * Seleccione el **[!UICONTROL Execution instance]**.
   * Marque la opción **[!UICONTROL Enabled]**.
   * Complete los parámetros de conexión para la instancia de ejecución.
   * Cada instancia de ejecución debe estar vinculada a una ID. Esta ID se asigna al hacer clic en el botón **[!UICONTROL Initialize connection]**.
   * Compruebe el tipo de aplicación utilizada: **[!UICONTROL Message Center]**, **[!UICONTROL Interaction]** o ambas.
   * Introduzca la cuenta de FDA utilizada. Se debe crear un operador en las instancias de ejecución y debe tener los siguientes derechos de lectura y escritura en la base de datos de la instancia en cuestión:

      ```
      grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
      grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
      ```
   >[!NOTE]
   >
   >La dirección IP de la instancia de control debe estar autorizada en las instancias de ejecución.

1. Configure el entorno:

   ![](assets/interaction_powerbooster2.png)

   * Añada la lista de instancias de ejecución.
   * Para cada uno, especifique el periodo de sincronización y los criterios de filtro (por ejemplo, por país).

      >[!NOTE]
      >
      >Si aparece un error, se puede consultar los flujos de trabajo de sincronización y ofrecer notificaciones. Se pueden encontrar en los flujos de trabajo técnicos de la aplicación.

Si, por razones de optimización, solo parte de la base de datos de mercadotecnia se duplica en las instancias de ejecución, se puede especificar un esquema restringido vinculado al entorno para permitir que los usuarios solo utilicen los datos disponibles en las instancias de ejecución. Se puede crear una oferta mediante datos que no estén disponibles en instancias de ejecución. Para ello, se debe desactivar la regla en los demás canales limitando esta regla en el canal saliente (campo **[!UICONTROL Taken into account if]**).

![](assets/ita_filtering.png)

### Opciones de mantenimiento {#maintenance-options}

A continuación, se muestra una lista de opciones de mantenimiento disponibles en la instancia de control:

>[!CAUTION]
>
>Estas opciones solo deben utilizarse para casos de mantenimiento específicos.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: la última fecha en la que se sincronizó un entorno en una instancia determinada.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: la última fecha en que se sincronizaron propuestas de un esquema determinado desde una instancia a otra.
* **`NmsInteraction_MapWorkflowId`**: una opción que contiene la lista de todos los flujos de trabajo de sincronización generados.

La siguiente opción está disponible en instancias de ejecución:

**NmsExecutionInstanceId**: opción que contiene la ID de instancia.

### Instalación de paquetes {#packages-installation}

**** De forma predeterminada, la tabla de propuestas se encuentra en 64 bits después de instalar los paquetes.

>[!CAUTION]
>
>En función del volumen de las propuestas existentes en la instancia, esta operación puede tardar unos minutos.

* Si la instancia tiene pocas propuestas o ninguna, no es necesario realizar ninguna modificación manual de la tabla de propuestas. La modificación se realiza cuando se instalan los paquetes.
* Si la instancia tiene muchas propuestas, es mejor cambiar la estructura de la tabla de propuestas antes de instalar los paquetes de control y ejecutarlos. Se recomienda ejecutar las consultas durante un periodo de baja actividad.

>[!NOTE]
>
>Si se ha realizado configuraciones específicas en la tabla de propuestas, adapte las consultas según corresponda.


There are two methods:

****

```
CREATE TABLE NmsPropositionRcp_tmp AS SELECT * FROM nmspropositionrcp WHERE 0=1;
ALTER TABLE nmspropositionrcp_tmp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
INSERT INTO nmspropositionrcp_tmp SELECT * FROM nmspropositionrcp;
DROP TABLE nmspropositionrcp;
CREATE INDEX proposition_id ON NmsPropositionRcp (ipropositionid);
CREATE INDEX nmspropositionrcp_deliveryid ON NmsPropositionRcp (ideliveryid);
CREATE INDEX nmspropositionrcp_lastmodified ON NmsPropositionRcp (tslastmodified);
CREATE INDEX nmspropositionrcp_offerid ON NmsPropositionRcp (iofferid);
CREATE INDEX nmspropositionrcp_offerspaceid ON NmsPropositionRcp (iofferspaceid);
CREATE INDEX nmspropositionrcp_recipientidid ON NmsPropositionRcp (irecipientid);
ALTER TABLE nmspropositionrcp_tmp RENAME TO nmspropositionrcp;
```

**Modificar tabla**

```
ALTER TABLE nmspropositionrcp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
```
