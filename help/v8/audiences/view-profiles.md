---
title: Ver perfiles existentes en Campaign
description: Obtenga información sobre cómo acceder a los datos de contacto en Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: b5574ba2d9fa520b701f7af4e34862304b825a66
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 6%

---

# Ver perfiles existentes{#view-profiles}

Navegar a **[!UICONTROL Profiles and targets]** para acceder a los destinatarios almacenados en la base de datos de Adobe Campaign.

Desde esta página, puede [crear nuevo destinatario](create-profiles.md), edite un destinatario existente y acceda a sus detalles de perfil.

![](assets/profiles-and-targets.png)

Para realizar manipulaciones de perfiles más avanzadas, acceda al árbol de Campaign desde el **[!UICONTROL Explorer]** en la página de inicio de Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>La pantalla integrada de Destinatario se define a través de un esquema XML y su formulario asociado. El esquema XML se almacena en el **[!UICONTROL Administration > Configuration > Data schemas]** del árbol del explorador de Adobe Campaign. Solo los usuarios expertos pueden realizar cambios en estos esquemas.
>

## Editar un perfil{#edit-a-profiles}

Seleccione un perfil para mostrar los detalles en una nueva pestaña.

![](assets/edit-a-profile.png)

Los datos concernientes a los perfiles se agrupan en pestañas. Estas pestañas y su contenido dependen de la configuración específica y de los paquetes instalados.

Para un destinatario integrado típico, puede acceder a las siguientes pestañas:

* **[!UICONTROL General]**, para todos los datos de perfil generales. En particular, contiene los apellidos, el nombre, la dirección de correo electrónico, el formato de correo electrónico, etc.

  Esta pestaña también almacena las variables **exclusión** indicador para el perfil: cuando la variable **[!UICONTROL No longer contact (by any channel)]** Una vez seleccionada la opción, el perfil se encuentra en la lista de bloqueados de la. Esta información se añade a los datos de contacto si el destinatario hace clic, por ejemplo, en un vínculo de baja en un boletín informativo. Este destinatario ya no se puede dirigir a ningún canal (correo electrónico, correo postal, etc.). Para obtener más información, consulte [esta página](../send/quarantines.md).

* **Información de contacto**, que contiene la dirección de correo postal del perfil seleccionado.

  Puede comprobar en esta pantalla el índice de calidad de la dirección y cuántos errores contiene la dirección. Esta información la utiliza directamente el proveedor de correo postal, según el número de errores encontrados durante las entregas anteriores y no se puede cambiar manualmente.

* **Otros**, para campos específicos que se pueden personalizar y rellenar según sus necesidades.

  Utilice el **[!UICONTROL Field properties…]** menú contextual para cambiar los nombres de los campos y definir su formato.

  ![](assets/other-tab-field-properties.png)

  Introduzca la nueva configuración como se muestra a continuación:

  ![](assets/change-field-properties.png)

  Compruebe la actualización en la interfaz de usuario:

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >Los cambios se aplican a todos los destinatarios.
  >


* **Suscripciones**, para todas las suscripciones activas a servicios. Utilice el **Historial** para acceder a los detalles de las suscripciones y las bajas de suscripción de este contacto.

  ![](assets/subscription-tab.png)

  Más información sobre las Suscripciones [en esta sección](../start/subscriptions.md).

* **Envíos**, para todos los registros de envío del perfil seleccionado. Utilice esta pestaña para acceder al historial de marketing del contacto: etiquetas, fechas y estado de todas las acciones de entrega dirigidas al perfil a través de todos los canales.


* **Seguimiento**, para todos los registros de seguimiento del perfil seleccionado. Esta información se utiliza para rastrear el comportamiento del perfil que sigue a las entregas. Esta pestaña muestra el total acumulado de todas las direcciones URL rastreadas en las entregas. La lista se puede configurar y normalmente contiene la dirección URL, la fecha y la hora en que se hizo clic, y el documento que contiene la dirección URL

  Más información sobre el Seguimiento [en esta sección](../start/tracking.md).


## Perfiles activos {#active-profiles}

Un perfil activo es un perfil con el que el cliente ha intentado comunicarse durante los últimos 12 meses a través de cualquier canal. Las métricas de licencia se basan en perfiles activos. Obtenga más información en [Descripción del producto de Adobe Campaign](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

>[!CAUTION]
>
>* Un perfil al que se destinan varios envíos se cuenta solo una vez.
>
>* Los perfiles segmentados en el contexto del marketing social en X (anteriormente conocido como Twitter) no se tienen en cuenta como perfiles activos.

Puede monitorizar el número de perfiles activos en su instancia directamente desde el Panel de control de Campaign de Campaign. Para obtener más información, consulte [documentación del Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=es){target="_blank"}.
