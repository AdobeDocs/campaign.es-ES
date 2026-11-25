---
title: Filtros predefinidos de oferta de interacción de campaña
description: Obtenga información sobre cómo crear filtros predefinidos
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 092262c7-768c-4e86-9b2b-c52516f6a030
TQID: 'https://experienceleague.adobe.com/XWkWbgrMASz-9FfrXC23tTwiw54oQH5U4iWM9fa2FDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 26%
---
# Creación de filtros predefinidos{#creating-pre-defined-filters}

Cree filtros predefinidos para definir reglas de idoneidad para la población de destino que se pueda reutilizar fácilmente durante la creación de la oferta. Son específicos a cada entorno y toman en cuenta los parámetros de oferta.

>[!NOTE]
>
>La interfaz de usuario web de Adobe Campaign le ofrece una interfaz fácil de usar para administrar y personalizar sin esfuerzo los filtros predefinidos para satisfacer sus necesidades específicas. Debe crearla una sola vez y guardarla para usarla en el futuro. Para obtener más información sobre los filtros predefinidos para la interfaz de usuario web, consulte la [documentación de la interfaz de usuario web de Adobe Campaign](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/predefined-filters){target=_blank}.


Para crear un filtro predefinido, siga el siguiente proceso:

1. Vaya a la carpeta **[!UICONTROL Administration]** y seleccione **[!UICONTROL Pre-defined offer filters]**.

   ![Ofertas: árbol de diseño con el nodo de filtros de oferta predefinidos seleccionado en Administración](assets/offer_filter_create_005.png)

1. Haga clic en **[!UICONTROL New]**.

   ![Lista de filtros de oferta predefinidos con el botón Nuevo resaltado y un filtro de edad](assets/offer_filter_create_001.png)

1. Cambie la etiqueta para poder identificar el filtro más adelante.

   ![Cuadro de diálogo de filtro de aplicación con el campo Etiqueta establecido en Canal de correo electrónico](assets/offer_filter_create_002.png)

1. Seleccione el campo va a corresponder a la condición de filtrado.

   ![Seleccione un cuadro de diálogo de expresión con el campo Correo electrónico elegido entre los campos Destinatario](assets/offer_filter_create_003.png)

1. Seleccione un operador y un valor si es necesario y, luego, guarde la consulta.

   ![La condición de filtro de la expresión de correo electrónico con el operador establecido en no está vacía](assets/offer_filter_create_004.png)

1. Haga clic en **[!UICONTROL Preview]** para ver el resultado del filtro.

   ![Pestaña Vista previa del filtro de canal de correo electrónico que enumera los destinatarios que coinciden con el filtro](assets/offer_filter_create_006.png)
