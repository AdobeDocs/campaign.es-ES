---
title: Creación de perfiles de prueba en Campaign
description: Obtenga información sobre cómo crear y administrar perfiles de prueba en Adobe Campaign
feature: Audiences, Profiles, Seed Address, Proofs
role: User
level: Beginner
exl-id: 878b5963-100c-4dd7-97a0-c59a62c493b1
TQID: https://experienceleague.adobe.com/nyvDFDlFE4SS0MQrYlynmBvDcOQHL8U6Bed606p6mpE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 982
ht-degree: 56%

---

# Creación y administración de perfiles de prueba {#create-test-profiles}

## ¿Qué es una dirección semilla? {#gs-seeds}

Los perfiles de prueba se crean como direcciones semilla. Se utilizan para dirigirse a los destinatarios que no coinciden con los criterios de destino definidos. Las direcciones semilla permiten previsualizar y probar la personalización y la renderización antes de realizar la entrega mediante la entrega de pruebas.

Las direcciones semilla tienen las siguientes ventajas:

* Sustitución aleatoria de campos con datos tomados de perfiles de destinatarios: esto permite introducir únicamente la dirección de correo electrónico, por ejemplo, en la sección de la dirección semilla; además, permite que Campaign rellene automáticamente los demás campos de formulario del perfil. Obtenga más información en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=en){target="_blank"}.
* Al utilizar un flujo de trabajo con funciones de gestión de datos, los datos adicionales procesados en los envíos se pueden introducir en el ámbito de la dirección semilla para forzar los valores, esto evita la sustitución de valores aleatorios.
* Las direcciones sembradas se excluyen automáticamente de los informes en las siguientes estadísticas de envío: **[!UICONTROL Clicks]**, **[!UICONTROL Opens]**, **[!UICONTROL Unsubscriptions]**.

Las direcciones semilla se añaden al destino de las entregas mediante su importación o su creación directamente en la entrega o la campaña.

>[!NOTE]
>
>Las direcciones semilla no se crean en la tabla de destinatarios sino en una tabla independiente. Si se amplía la lista de distribución con nuevos datos, debe ampliar la lista de direcciones semilla con los mismos datos. De lo contrario, los campos ampliados no tienen en cuenta las direcciones semilla.
>
>Se presenta un ejemplo de cómo extender la tabla de direcciones semilla en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

## Creación de direcciones semilla

Las direcciones semilla no se administran a través de perfiles y destinos estándar, sino en un nodo específico del explorador de Adobe Campaign: **[!UICONTROL Resources > Campaign management > Seed addresses]**. Se pueden crear subcarpetas para organizar las direcciones semilla.

Adobe Campaign también permite crear plantillas de las direcciones semilla que se importan a los envíos o campañas, adaptándolas a las necesidades específicas de los envíos o campañas correspondientes. Consulte [Creación de plantillas de direcciones semilla](#creating-seed-address-templates).

### Definición de direcciones {#defining-addresses}

Para crear direcciones semilla, siga estos pasos:

1. Haga clic en el botón **[!UICONTROL New]** situado encima de las direcciones semilla.
1. Introduzca los datos relacionados con la dirección en los campos correspondientes de la pestaña **[!UICONTROL Recipient]**. Los campos disponibles corresponden a los datos fundamentales del perfil de los destinatarios del envío (tabla nms:recipient): nombre, apellido, correo electrónico, etc.

   >[!NOTE]
   >
   >La etiqueta de la dirección se rellena automáticamente con el apellido y el nombre definidos.
   >
   >No es necesario introducir todos los campos de cada pestaña al crear una dirección semilla. Los elementos de personalización que faltan se introducen de forma aleatoria durante el análisis de envío.

1. En la ficha **[!UICONTROL Address fields]**, introduzca los valores que desea insertar en los registros de envío durante la fase de análisis, en la tabla **[!UICONTROL nms:broadLog]**.

1. En la pestaña **[!UICONTROL Additional data]**, introduzca los datos de personalización utilizados para los envíos creados en los flujos de trabajo de gestión de datos y a los que desea asignar un valor específico.

   Asegúrese de que se hayan definido datos de destino adicionales con un alias que comience por &#39;@&#39; en la actividad de flujo de trabajo **[!UICONTROL Enrichment]**. De lo contrario, no podrá usarlos correctamente con sus direcciones semilla en la actividad de envío.

### Creación de plantillas de direcciones semilla {#creating-seed-address-templates}

Puede crear plantillas de direcciones que se pueden importar y modificar para cada entrega. El proceso es el mismo que al definir una nueva dirección semilla. La única diferencia es que las direcciones semilla deben almacenarse en una carpeta de tipo “plantilla”.

### Direcciones semilla para envíos de correo directo {#direct-mail-seed-addresses}

Para [envíos de correo postal](../send/direct-mail.md), las direcciones semilla se agregan durante la extracción y se mezclan en el documento de salida.

En las entregas por correo directo, el formato del archivo de extracción debe cumplir con las siguientes limitaciones:

* No se debe utilizar la opción **[!UICONTROL Handle groupings (GROUP BY+HAVING)]**.

* Si se extraen colecciones de datos, estos campos deben tener un valor vacío para las direcciones semilla, a menos que se seleccione la opción **[!UICONTROL Single row (expert user)]**.

## Adición de direcciones semilla en una entrega{#seed-addresses-in-a-delivery}

Para añadir direcciones semilla específicas a una entrega, haga clic en el vínculo **[!UICONTROL To]** y después seleccione la pestaña **[!UICONTROL Seed addresses]**.

Hay tres modos de inserción posibles:

1. Introduzca direcciones semilla únicas.  Para ello, haga clic en el botón **[!UICONTROL Add]** y defina el contenido de los campos de dirección. Repita este proceso con cada dirección.

1. Importe [plantillas de direcciones semilla](#creating-seed-address-template) y adáptelas para adaptarlas a sus necesidades. Para ello, haga clic en el enlace **[!UICONTROL Import seed templates...]** y seleccione la carpeta que contiene las plantillas de dirección.

   Si es necesario, una vez añadidas, se puede hacer doble clic en ellas o hacer clic en el botón **[!UICONTROL Detail...]** para adaptar el contenido de cada dirección.

1. Cree una condición para seleccionar dinámicamente las direcciones de control que desea insertar. Para ello, haga clic en el enlace **[!UICONTROL Edit the dynamic condition...]** e introduzca los parámetros de selección de las direcciones semilla. Por ejemplo, puede incluir todas las direcciones semilla que contenga una carpeta específica o las pertenecientes a un departamento específico de su organización.

   Se presenta un ejemplo de esto en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

Para las entregas, también se puede personalizar la forma en que se insertan las direcciones en los archivos de extracción. De forma predeterminada, se insertan en el orden de clasificación del archivo de salida, pero se puede elegir insertarlos al final o al principio del archivo o aleatoriamente entre los receptores del destino principal.

## Añadir direcciones semilla en una campaña {#seed-addresses-in-a-campaign}

Para añadir direcciones semilla a un destinatario para una campaña, seleccione la operación y haga clic en la pestaña **[!UICONTROL Edit]**.

Haga clic en el vínculo **[!UICONTROL Advanced campaign settings...]** y luego en la ficha **[!UICONTROL Seed addresses]**. Las direcciones semilla insertadas desde la campaña se añaden al objetivo de cada entrega de la campaña.

## Direcciones semilla y tabla personalizada {#using-an-external-recipient-table}

Si la lista de distribución es una tabla externa, debe realizar ajustes adicionales. Se debe ampliar el esquema **[!UICONTROL nms:seedmember]**. Se añade una pestaña a las direcciones semilla para definir los campos adecuados

En este caso, para añadir direcciones semilla al envío, introduzca los campos adecuados directamente en la pestaña correspondiente o importe las plantillas de dirección.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->
