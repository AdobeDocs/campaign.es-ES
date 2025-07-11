---
title: Ver perfiles existentes en Campaign
description: Obtenga información sobre cómo acceder a los datos de contacto en Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 4%

---

# Ver perfiles existentes{#view-profiles}

Vaya a **[!UICONTROL Profiles and targets]** para acceder a los destinatarios almacenados en la base de datos de Adobe Campaign.

Desde esta página, puede [crear destinatario nuevo](create-profiles.md), editar un destinatario existente y acceder a sus detalles de perfil.

![](assets/profiles-and-targets.png)

Para realizar manipulaciones de perfiles más avanzadas, acceda al árbol de Campaign desde el vínculo **[!UICONTROL Explorer]** de la página principal de Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>La pantalla integrada de Destinatario se define a través de un esquema XML y su formulario asociado. El esquema XML se almacena en el nodo **[!UICONTROL Administration > Configuration > Data schemas]** del árbol del explorador de Adobe Campaign. Solo los usuarios expertos pueden realizar cambios en estos esquemas.
>

## Editar un perfil{#edit-a-profiles}

Seleccione un perfil para mostrar los detalles en una nueva pestaña.

![](assets/edit-a-profile.png)

Los datos concernientes a los perfiles se agrupan en pestañas. Estas pestañas y su contenido dependen de la configuración específica y de los paquetes instalados.

Para un destinatario integrado típico, puede acceder a las siguientes pestañas:

* **[!UICONTROL General]**, para todos los datos de perfil generales. En particular, contiene los apellidos, el nombre, la dirección de correo electrónico, el formato de correo electrónico, etc.

  Esta pestaña también almacena el indicador **opt-out** para el perfil: cuando se selecciona la opción **[!UICONTROL No longer contact (by any channel)]**, el perfil se encuentra en lista de bloqueados de la. Esta información se añade a los datos de contacto si el destinatario hace clic, por ejemplo, en un vínculo de baja en un boletín informativo. Este destinatario ya no se puede dirigir a ningún canal (correo electrónico, correo postal, etc.). Para obtener más información, consulte [esta página](../send/quarantines.md).

* **Información de contacto**, que contiene la dirección de correo postal del perfil seleccionado.

  Puede comprobar en esta pantalla el índice de calidad de la dirección y cuántos errores contiene la dirección. Esta información la utiliza directamente el proveedor de correo postal, según el número de errores encontrados durante las entregas anteriores y no se puede cambiar manualmente.

* **Otro**, para campos específicos que se pueden personalizar y rellenar según sus necesidades.

  Utilice el menú contextual **[!UICONTROL Field properties…]** para cambiar los nombres de los campos y definir su formato.

  ![](assets/other-tab-field-properties.png)

  Introduzca la nueva configuración como se muestra a continuación:

  ![](assets/change-field-properties.png)

  Compruebe la actualización en la interfaz de usuario:

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >Los cambios se aplican a todos los destinatarios.
  >


* **Suscripciones**, para todas las suscripciones activas a los servicios. Use la ficha **Historial** para obtener acceso a los detalles de suscripciones y bajas de este contacto.

  ![](assets/subscription-tab.png)

  Obtenga más información acerca de las suscripciones [en esta sección](../start/subscriptions.md).

* **Envíos**, para todos los registros de envío del perfil seleccionado. Utilice esta pestaña para acceder al historial de marketing del contacto: etiquetas, fechas y estado de todas las acciones de entrega dirigidas al perfil a través de todos los canales.


* **Seguimiento**, para todos los registros de seguimiento del perfil seleccionado. Esta información se utiliza para rastrear el comportamiento del perfil que sigue a las entregas. Esta pestaña muestra el total acumulado de todas las direcciones URL rastreadas en las entregas. La lista se puede configurar y normalmente contiene la dirección URL, la fecha y la hora en que se hizo clic, y el documento que contiene la dirección URL

  Obtenga más información acerca del seguimiento [en esta sección](../start/tracking.md).
