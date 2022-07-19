---
product: campaign
title: Introducción al marketing distribuido
description: Introducción al marketing distribuido
feature: Distributed Marketing
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 100%

---

# Introducción al marketing distribuido{#about-distributed-marketing}



Adobe Campaign ofrece una aplicación de **marketing distribuido** para implementar campañas cooperativas entre entidades centrales (sede central, departamentos de marketing, etc.) y entidades locales (puntos de ventas, agencias regionales, etc.). Esta cooperación se basa en un espacio de trabajo compartido denominado **[!UICONTROL list of campaign packages]**, donde las entidades locales pueden encontrar plantillas de campañas creadas de forma centralizada y diferentes instancias.

La entidad central proporciona campañas que entidades locales pueden utilizar. Las campañas se materializan mediante paquetes que corresponden a campañas locales o de colaboración. Para utilizar una campaña, la entidad local debe pedirla y se debe aprobar la solicitud.

>[!CAUTION]
>
>El módulo de Distributed Marketing es una opción de **Campaign.** Compruebe el acuerdo de licencia.

## Terminología {#terminology}

* **Entidades centrales**

   Las entidades centrales están formadas por operadores de marketing responsables de especificar comunicaciones y ayudar a las entidades locales a ejecutar su campaña de marketing.

   El módulo de Distributed Marketing permite que la entidad central:

   * configure paquetes de campañas de marketing para entidades locales,
   * aumente el grado de autonomía de las entidades locales respecto a la elección de la comunicación para clientes o posibles clientes, así como su segmentación, contenido, etc.
   * administre y controle los costes,
   * gestione una red de agencias.

* **Entidades locales**

   Las entidades locales pueden ser agencias, tiendas o grupos de operadores locales específicos (directores de país o región, administradores de marcas, etc.).

   Distributed Marketing permite que las entidades locales tengan más autonomía al optimizar los costes de ejecución.

* **Localización**

   La localización es la capacidad de una entidad local para modificar los destinatarios y el contenido de una campaña. El nivel de localización posible depende del tipo de campaña y de su implementación.

* **Lista de paquetes de campañas**

   La lista de paquetes de campañas contiene las campañas disponibles para las entidades locales.

* **Paquete de campañas**

   Plantilla (o instancia de campaña) creada por una entidad central y disponible para un conjunto de entidades locales.

* **Campaña local**

   Una campaña local es una instancia creada a partir de una plantilla a la que se hace referencia en la lista de **[!UICONTROL campaign packages]** con una **programación de ejecución determinada**. Su objetivo es utilizar una comunicación local mediante una plantilla de campaña configurada por la entidad central.

   El grado de autonomía de la entidad local depende de la implementación utilizada.

   Consulte [Creación de una campaña local](creating-a-local-campaign.md).

* **Campaña de colaboración**

   Una campaña de colaboración es aquella que pueden utilizar las entidades locales y cuya **programación de ejecución** queda a cargo de la entidad central. El contenido es el mismo para cada entidad local pero se comparten los costes. Para participar, las entidades locales deben suscribirse a la campaña de colaboración.

   * **[!UICONTROL Collaborative campaign (by form)]**: recomendado para campañas que impliquen hasta 300 entidades locales. La entidad local puede escribir los parámetros predefinidos para la personalización del contenido y los objetivos en un formulario web. El formulario puede ser un formulario de Adobe Campaign o un formulario externo (cliente de extranet). Un administrador funcional puede definir y configurar el formulario basado en una plantilla de formulario definida por el integrador. Para solicitar la campaña, la entidad local solo necesita tener acceso a la web.
   * **[!UICONTROL Collaborative campaign (by campaign)]**: recomendado para campañas destinadas a decenas de entidades locales. Este tipo de campaña crea campañas secundarias para cada entidad local. Una vez que la entidad central aprueba la **[!UICONTROL collaborative campaign (by campaign)]**, la campaña está disponible para la entidad local, que puede modificarla. La ejecución se realiza automáticamente entre las campañas principales y secundarias. La entidad local debe tener acceso a una instancia para solicitar una campaña y participar en ella.
   * **[!UICONTROL Collaborative campaign (by target approval)]**: recomendado para campañas destinadas a miles de entidades locales. La entidad local recibe una lista de contactos predefinida por la entidad central. La entidad local decide si se deben o no conservar ciertos contactos según el contenido de la campaña, a través de un formulario web. Las entidades locales se obtienen de la lista de contactos seleccionados. Para participar en la campaña, la entidad local solo necesita tener acceso a la web.
   * **[!UICONTROL Collaborative campaign (simple)]**: este modo garantiza la compatibilidad con los procesos de ejecución específicos de versiones anteriores.

   Consulte [Creación de una campaña de colaboración](creating-a-collaborative-campaign.md).

**Solicitud de paquetes de campaña**

Si una entidad local se registra para una campaña, esto se convierte en un pedido que reagrupa toda la información relativa a la localización de la campaña.

## Espacio de trabajo {#workspace}

Se puede acceder a la lista de paquetes de campañas desde la pestaña **Campañas**: haga clic en el vínculo **[!UICONTROL Campaign packages]**.

![](assets/mkg_dist_home_local_op.png)

Esta ventana permite que todos los operadores locales vean las campañas disponibles para su organismo local.

En el caso de las agencias centrales, esta ventana muestra todos los paquetes disponibles en la lista de paquetes de campañas e incluye vínculos adicionales para editar la lista.

## Operadores y entidades {#operators-and-entities}

Comience especificando los operadores de entidad central y local a través de la carpeta **[!UICONTROL Access management]**.

![](assets/s_advuser_mkg_dist_tree.png)

### Operadores {#operators}

Necesita crear operadores locales y centrales.

Los operadores centrales deben pertenecer al grupo de operadores **[!UICONTROL Central management]** o tener el nombre **[!UICONTROL CENTRAL]** adecuado.

Los operadores locales deben pertenecer al grupo de operadores **[!UICONTROL Local management]** o tener el nombre **[!UICONTROL LOCAL]** adecuado. También deben estar vinculados a su entidad local.

![](assets/s_advuser_mkg_dist_local_create.png)

### Entidades organizativas {#organizational-entities}

Para crear una entidad organizativa, haga clic en **[!UICONTROL Administration > Access management > Organizational entities]** y seleccione el icono **[!UICONTROL New]** situado encima de la lista de entidades.

![](assets/s_advuser_mkg_dist_local_list.png)

Cada entidad organizativa contiene información de identificación (etiqueta, nombre interno, información de contacto, etc.) y grupos involucrados en el proceso de aprobación. Se definen en la sección **[!UICONTROL Notifications and approvals]** ubicada en la pestaña **[!UICONTROL General]**.

* Defina un grupo de notificación de paquetes: los operadores de este grupo recibirán una notificación cada vez que se añada un nuevo paquete a la lista de paquetes de campañas y cada vez que una campaña esté disponible.
* Seleccione el grupo de revisores de la aprobación de solicitudes; es decir, aquellos que se encarguen de aprobar las campañas ordenadas por la entidad local.
* Finalmente, seleccione el grupo de revisores de la aprobación de la campaña local (objetivo, contenido, presupuesto, etc.). Este grupo puede añadirse a la solicitud de una campaña, según la plantilla.

>[!NOTE]
>
>El proceso de aprobación se presenta en la sección [Proceso de aprobación](creating-a-local-campaign.md#approval-process).

## Implementación {#implementation}

La entidad central es la encargada de crear y publicar las campañas de Distributed Marketing. Las entidades locales y centrales pueden utilizarlas según sea necesario.

El procedimiento de implementación depende del tipo de paquete de campaña utilizado y de los niveles de delegación de entidades locales.

### Tareas integradoras {#integrator-side}

1. Cree entidades locales.
1. Vincule los destinatarios con los operadores que administran las entidades locales.

   ![](assets/mkg_dist_local_entity_association.png)

1. Especifique derechos y reglas de navegación para entidades locales
1. Especifique el conjunto de campos necesarios para la localización de la campaña:

   * definición de objetivos y tamaño máximo,
   * definición de contenido,
   * programación de ejecución (fecha de contacto y fecha de extracción), **solo para operadores locales**,
   * extensión de un esquema de solicitud con todos los campos adicionales necesarios.

1. Creación de un formulario web (Adobe o extranet) que le permita mostrar los parámetros de la localización, evaluar el objetivo y el presupuesto, así como previsualizar el contenido y aprobar el pedido.

   Para **las campañas colaborativas (por aprobación de objetivo)**, cree la tabla donde se guardarán las aprobaciones de cada entidad local.

### Tareas funcionales de administrador {#functional-administrator-side}

Estos pasos deben llevarse a cabo al crear cada campaña.

1. Actualice el formulario con los campos utilizados para la localización de campañas.
1. Cree una instancia a partir de una plantilla de campaña adecuada (campaña de colaboración) o duplique la plantilla de campaña (campaña local).
1. Configure la campaña con los campos de localización y la referencia de formulario.
1. Publique la campaña.

### Tareas del operador local {#local-operator-side}

Estos pasos deben llevarse a cabo para cada campaña.

1. Una vez que reciba la notificación de la disponibilidad del paquete de campañas, especifique la ubicación de la campaña (opcional).
1. Evalúe el objetivo, el presupuesto, etc.
1. Previsualice el contenido de la campaña.
1. Solicite la campaña.
