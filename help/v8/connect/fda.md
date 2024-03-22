---
title: Uso de bases de datos de Campaign y externas (FDA)
description: Obtenga información sobre cómo trabajar con bases de datos de Campaign y externas
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 36%

---

# Acceso de datos federado (FDA){#gs-fda}

Utilice el conector FDA (Acceso de datos federado) para conectar Campaign a uno o más **bases de datos externas** y procesar la información almacenada en ellos sin afectar a los datos de la base de datos de Campaign Cloud. A continuación, puede acceder a datos externos sin cambiar la estructura de los datos de Adobe Campaign.

>[!NOTE]
>
>* Las bases de datos compatibles para el acceso de datos federado se enumeran en la [Matriz de compatibilidad](../start/compatibility-matrix.md).
>
>* En el contexto de un [Implementación empresarial (FDAC)](../architecture/enterprise-deployment.md), hay una cuenta externa específica disponible para administrar la comunicación entre la base de datos local de Campaign y la base de datos en la nube de Snowflake. Esta cuenta externa está configurada por Adobe y **no debe** no se puede modificar.
>
>* Como usuario de Managed Cloud Service, [Adobe de contacto](../start/campaign-faq.md#support) para conectar las bases de datos externas con Campaign.


## Prácticas recomendadas y limitaciones

La opción FDA está sujeta a las limitaciones del sistema de base de datos de terceros que utiliza.

Además, tenga en cuenta las siguientes limitaciones y prácticas recomendadas:

* La opción FDA se realiza para manipular los datos en bases de datos externas en modo de lote en los flujos de trabajo. Para evitar problemas de rendimiento, no se recomienda utilizar el módulo FDA en el contexto de operaciones unitarias, como: personalización, interacción, mensajería en tiempo real, etc.

* Evite en la medida de lo posible las operaciones que requieran utilizar tanto Adobe Campaign como la base de datos externa. Para ello, puede hacer lo siguiente:

   * Exporte la base de datos de Adobe Campaign a la base de datos externa y ejecute las operaciones solo desde la base de datos externa antes de volver a importar los resultados en Adobe Campaign.

   * Recopile los datos de la base de datos externa de Adobe Campaign y ejecute las operaciones localmente.

  Si desea personalizar las entregas utilizando datos de la base de datos externa, recopile los datos para utilizarlos en un flujo de trabajo para que estén disponibles en una tabla temporal. A continuación, utilice los datos de la tabla temporal para personalizar su envío. Para ello, preprocese la personalización de mensajes en un flujo de trabajo dedicado utilizando **[!UICONTROL Prepare the personalization data with a workflow]** opción, disponible en el **[!UICONTROL Analysis]** de las propiedades de entrega. Durante el análisis de envío, esta opción crea y ejecuta automáticamente un flujo de trabajo que almacena todos los datos vinculados con el objetivo en una tabla temporal, incluidos los datos de tablas vinculadas en una base de datos externa.

  >[!CAUTION]
  >
  >Esta opción mejora significativamente el rendimiento al ejecutar el paso de personalización.


## Uso de datos externos en un flujo de trabajo

Campaign incluye varias actividades de flujo de trabajo que puede utilizar para interactuar con los datos de sus bases de datos externas:

* **Filtro en datos externos** - Utilice el **[!UICONTROL Query]** actividad para añadir datos externos y utilizarlos en las configuraciones de filtro definidas.

* **Creación de subconjuntos** - Utilice el **[!UICONTROL Split]** actividad para crear subconjuntos. Puede utilizar datos externos para definir los criterios de filtrado que deben utilizarse.

* **Cargar base de datos externa** : utilice los datos externos en la **[!UICONTROL Data loading (RDBMS)]** actividad.

* **Adición de información y vínculos** - Utilice el **[!UICONTROL Enrichment]** actividad para añadir datos adicionales a la tabla de trabajo del flujo de trabajo y vínculos a una tabla externa. En este contexto, puede utilizar datos de una base de datos externa.

También puede definir directamente una conexión con una base de datos externa desde todas las actividades de flujo de trabajo enumeradas anteriormente, para un uso temporal. En este caso, se trata de una base de datos externa local, que se utilizará únicamente dentro del flujo de trabajo actual.

>[!CAUTION]
>
>Este tipo de configuración solo debe utilizarse de forma temporal para recopilar datos. La configuración de cuenta externa debe ser la preferida para cualquier otro uso.

Por ejemplo, en la variable **[!UICONTROL Query]** actividad, puede definir una conexión temporal con una base de datos externa de la siguiente manera:

1. Abra la actividad y haga clic en **[!UICONTROL Add data...]**
1. Seleccione el **[!UICONTROL External data]** opciones
1. Seleccione el **[!UICONTROL Locally defining the data source]** opción
1. Seleccionar el motor de base de datos de objetivo en la lista desplegable. Introduzca el nombre del servidor y proporcione los parámetros de autenticación. Especificar también el nombre de la base de datos externa.
1. Seleccione la tabla donde se almacenan los datos. Puede introducir el nombre de la tabla directamente en el campo correspondiente o hacer clic en el icono de edición para acceder a la lista de las tablas de la base de datos.
1. Hacer clic en el botón **[!UICONTROL Add]** para definir uno o varios campos de reconciliación entre los datos de la base de datos externa y los datos de la base de datos de Adobe Campaign. Los iconos **[!UICONTROL Edit expression]** del **[!UICONTROL Remote field]** y el **[!UICONTROL Local field]** le proporcionan acceso a la lista de campos de cada una de las tablas.
1. Si es necesario, especifique una condición de filtrado y el modo de clasificación de datos.
1. Seleccione los datos adicionales que se recopilarán en la base de datos externa. Para ello, haga doble clic en los campos que desea añadir para mostrarlos en las **[!UICONTROL Output columns]**.
1. Hacer clic en **[!UICONTROL Finish]** para confirmar esta configuración.
