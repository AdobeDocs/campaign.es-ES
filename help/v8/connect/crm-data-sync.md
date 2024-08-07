---
title: Sincronización de datos de conectores CRM
description: Administrar datos entre Campaign y su CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin
level: Beginner
exl-id: 2a7ae88e-d47f-416b-84cd-986ab9be6aef
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 56%

---

# Sincronización de datos entre Campaign y CRM {#data-synchronization}

La actividad de flujo de trabajo **CRM Connector** administra la sincronización de datos entre Adobe Campaign y su CRM.

Por ejemplo, para importar los datos de Microsoft Dynamics en Adobe Campaign, cree el siguiente tipo de flujo de trabajo:

![](assets/ms-dyn-wf.png)

Este flujo de trabajo importa los contactos a través de Microsoft Dynamics, los sincroniza con los datos de Adobe Campaign existentes, elimina los contactos duplicados y actualiza la base de datos de Adobe Campaign.

Debe configurarse la actividad **[!UICONTROL CRM Connector]** para sincronizar los datos.

![](assets/crm-connector-ms-dyn.png)

Con esta actividad puede:

* Importar desde CRM: [Más información](#importing-from-the-crm)
* Exportar a CRM: [Más información](#exporting-to-the-crm)
* Importar objetos eliminados en CRM: [Más información](#importing-objects-deleted-in-the-crm)
* Eliminar objetos en CRM: [Más información](#deleting-objects-in-the-crm)

![](assets/crm-remote-op.png)

Seleccione la cuenta externa que coincide con el CRM con el que desea configurar la sincronización y, a continuación, seleccione el objeto que desea sincronizar: cuentas, oportunidades, posibles clientes, contactos, etc.

![](assets/crm-remote-obj.png)

La configuración de esta actividad depende del proceso que se realice. A continuación se describen varias configuraciones.

## Importación desde CRM {#importing-from-the-crm}

Para importar datos del CRM a Adobe Campaign, debe crear el siguiente tipo de flujo de trabajo:

![](assets/crm-wf-import.png)

1. Seleccione una operación **[!UICONTROL Import from the CRM]**.
1. En la lista desplegable **[!UICONTROL Remote object]**, seleccione el objeto que desea importar. Este objeto coincide con una de las tablas creadas en Adobe Campaign durante la configuración del conector.
1. En la sección **[!UICONTROL Remote fields]**, introduzca los campos que desea importar.

   Para agregar un campo, haga clic en el botón **[!UICONTROL Add]** en la barra de herramientas y, a continuación, haga clic en el icono **[!UICONTROL Edit expression]**.

   Si es necesario, cambie el formato de los datos mediante la lista desplegable de las **[!UICONTROL Conversion]** columnas. Los tipos de conversión posibles se encuentran detallados en [esta sección](#data-format).

   >[!CAUTION]
   >
   >El identificador del registro en CRM es obligatorio para enlazar objetos en CRM y en Adobe Campaign. Se añade automáticamente cuando se aprueba el cuadro.
   >
   >La fecha de modificación del servidor CRM también es obligatoria para las importaciones de datos incrementales.

1. Puede filtrar los datos para importarlos según sus necesidades. Para ello, haga clic en el vínculo **[!UICONTROL Edit the filter...]**.

   En el siguiente ejemplo, Adobe Campaign solo importa contactos para los que se haya registrado alguna actividad desde el 1 de noviembre de 2021.

   ![](assets/crm-task-import-filter.png)

   >[!CAUTION]
   >
   >Las limitaciones relacionadas con los modos de filtrado de datos se detallan en [esta sección](#filtering-data).

1. Seleccione la opción **[!UICONTROL Use automatic index...]** para administrar automáticamente la sincronización de objetos incrementales entre su CRM y Adobe Campaign, según la fecha y la última modificación.

   Para obtener más información, consulte [esta sección](#variable-management).

### Administración de variables {#variable-management}

Active la opción **[!UICONTROL Automatic index]** para recopilar solamente los objetos modificados desde la última importación.

![](assets/use-auto-index.png)

La fecha de la última sincronización se almacena de forma predeterminada en una opción especificada en la ventana de configuración, por defecto: **LASTIMPORT_&lt;%=instance.internalName%>_&lt;%=activityName%>**.

>[!NOTE]
>
>Esta nota solo se aplica a la actividad genérica **[!UICONTROL CRM Connector]**. Para otras actividades CRM, el proceso es automático.
>
>Esta opción debe crearse manualmente y rellenarse en **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. Debe ser una opción de texto y su valor debe coincidir con el formato siguiente: **`yyyy/MM/dd hh:mm:ss`**
> 
>Debe actualizar manualmente esta opción para una importación posterior.

Puede especificar el campo remoto CRM que desea tener en cuenta para identificar los cambios más recientes.

De forma predeterminada, se utilizan los campos siguientes (en el orden especificado):

* Para Microsoft Dynamics: **modificado**,
* Para Salesforce.com: **LastModifiedDate**, **SystemModstamp**.

La activación de la opción **[!UICONTROL Automatic index]** genera tres variables que se pueden utilizar en el flujo de trabajo de sincronización a través de una actividad de tipo **[!UICONTROL JavaScript code]**. Estas actividades son:

* **vars.crmOptionName**: nombre de la opción que contiene la última fecha de importación.
* **vars.crmStartImport**: fecha de inicio (incluida) de la última importación de datos.
* **vars.crmEndDate**: fecha de finalización (excluida) de la última importación de datos.

  >[!NOTE]
  >
  >Estas fechas se muestran en el siguiente formato: **`yyyy/MM/dd hh:mm:ss`**.

### Filtrado de datos {#filtering-data}

Para garantizar una operación eficaz con los distintos CRM, es necesario crear filtros con las siguientes reglas:

* Cada nivel de filtrado solo puede utilizar un tipo de operador.
* No se admite el operador AND NOT.
* Las comparaciones solo pueden tener como resultado valores nulos (“está vacío”/“no está vacío”) o números. Esto significa que el valor (columna derecha) se evalúa y el resultado de esta evaluación debe ser un número. Por lo tanto, no se admiten comparaciones de tipo JOIN.
* El valor contenido en la columna derecha se evalúa en JavaScript.
* No se admiten comparaciones JOIN.
* La expresión de la columna de la izquierda debe ser un campo. No puede ser una combinación de varias expresiones, un número, etc.

### Ordenar por {#order-by}

En Microsoft Dynamics y Salesforce.com, puede ordenar los campos remotos para que se importen en orden de subida o de bajada.

Para ello, haga clic en el vínculo **[!UICONTROL Order by]** y añada las columnas a la lista.

El orden de las columnas de la lista es el orden de clasificación:

![](assets/crm-import-order.png)

### Identificación de registro {#record-identification}

En lugar de importar elementos incluidos (y posiblemente filtrados) en su CRM, puede utilizar una población calculada con anterioridad en el flujo de trabajo.

Para ello, seleccione la opción **[!UICONTROL Use the population calculated upstream]** y especifique el campo que contiene el identificador remoto.

Entonces, seleccione los campos de la población entrante que desea importar, como se muestra a continuación:

![](assets/use-population-calc-upstream.png)

## Exportación a CRM {#exporting-to-the-crm}

Exporte datos de Adobe Campaign a su CRM para copiar todo su contenido en la base de datos de CRM.

Para exportar datos a su CRM, cree el siguiente tipo de flujo de trabajo:

![](assets/crm-export-diagram.png)

1. Seleccione una operación **[!UICONTROL Export to CRM]**.
1. Vaya a la lista desplegable **[!UICONTROL Remote object]** y seleccione el objeto que desea exportar. Este objeto coincide con una de las tablas creadas en Adobe Campaign durante la configuración del conector.

   >[!CAUTION]
   >
   >La función de exportación de la actividad **[!UICONTROL CRM Connector]** puede insertar o actualizar campos en su CRM. Para habilitar las actualizaciones de campo en CRM, especifique la clave principal de la tabla remota. Si falta la clave, se insertan los datos en lugar de actualizarse.

1. Si necesita realizar exportaciones más rápidas, marque la opción **[!UICONTROL Export in Batches]**.

   ![](assets/crm-export-batch.png)

1. En la sección **[!UICONTROL Mapping]**, haga clic en **[!UICONTROL New]** para especificar los campos que se exportarán y su asignación en CRM.

   Para agregar un campo, haga clic en el botón **[!UICONTROL Add]** en la barra de herramientas y, a continuación, haga clic en el icono **[!UICONTROL Edit expression]**.

   >[!NOTE]
   >
   >Si no se define ninguna coincidencia para un campo, los valores no se pueden actualizar: se insertan directamente en el CRM.

   Si es necesario, cambie el formato de los datos mediante la lista desplegable de las **[!UICONTROL Conversion]** columnas. Los tipos de conversión posibles se encuentran detallados en [esta sección](#data-format).

   >[!NOTE]
   >
   >La lista de registros que se van a exportar y el resultado de la exportación se guardan en un archivo temporal que permanece accesible hasta que el flujo de trabajo termina o se reinicia. Esto le permite iniciar el proceso con seguridad en caso de errores.

## Configuraciones adicionales {#additional-configurations}

### Formato de datos {#data-format}

Puede convertir el formato de los datos sobre la marcha al importarlos desde o hacia su CRM.

Para ello, seleccione la conversión que se aplica en la columna correspondiente.

![](assets/crm-task-import.png)

El modo **[!UICONTROL Default]** aplica la conversión automática de datos, que en la mayoría de los casos es igual a una copia o pegado de los datos. Sin embargo, se aplica la administración de zona horaria.

Otras conversiones posibles son:

* **[!UICONTROL Date only]**: elimina los campos de tipo Fecha + Hora.
* **[!UICONTROL Without time offset]**: cancela la administración de zona horaria aplicada en el modo predeterminado.
* **[!UICONTROL Copy/Paste]**: utiliza datos sin procesar como cadenas (sin conversión).

### Error de procesamiento {#error-processing}

Dentro del marco de las importaciones o exportaciones de datos, puede aplicar un proceso específico a errores y rechazos. Para ello, en la pestaña **[!UICONTROL Behavior]** , seleccione la opción **[!UICONTROL Keep the rejections in a file]** y **[!UICONTROL Process errors]**.

![](assets/crm-export-options.png)

Estas opciones añaden las transiciones de salida relacionadas.

![](assets/crm-export-transitions.png)

A continuación, inserte las actividades relevantes para procesar datos. Por ejemplo, agregue una actividad **Wait** y programe reintentos para detectar errores.

La transición de salida **[!UICONTROL Reject]** permite acceder al esquema de salida que contiene las columnas específicas de los mensajes de error y los códigos. Para Salesforce.com, esta columna es **errorSymbol** (símbolo de error, distinto del código de error), **errorMessage** (descripción del contexto del error).

## Importación de objetos eliminados en CRM {#importing-objects-deleted-in-the-crm}

Puede importar objetos eliminados en su CRM a Adobe Campaign.

1. Seleccione una operación **[!UICONTROL Import objects deleted in the CRM]**.
1. Ir a la lista desplegable **[!UICONTROL Remote object]** y seleccionar el objeto afectado en el proceso. Este objeto coincide con una de las tablas creadas en Adobe Campaign durante la configuración del conector.
1. Especifique el período de eliminación a tener en cuenta en los campos **[!UICONTROL Start date]** y **[!UICONTROL End date]** (se incluyen las fechas).

   >[!CAUTION]
   >
   >El periodo de eliminación debe coincidir con las limitaciones específicas de CRM. Por ejemplo, para Salesforce.com, los elementos eliminados hace más de 30 días no se pueden recuperar.

## Eliminación de objetos en CRM {#deleting-objects-in-the-crm}

Para eliminar objetos en CRM, especifique la clave principal de los elementos remotos que desea eliminar.

La pestaña **[!UICONTROL Behavior]** permite activar el procesamiento de los rechazos. Esta opción genera una segunda transición de salida para la actividad **[!UICONTROL CRM connector]**. Para obtener más información, consulte [Error de procesamiento](#error-processing).
