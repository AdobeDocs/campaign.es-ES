---
title: Prácticas recomendadas de envíos
description: Conozca las prácticas recomendadas al diseñar y enviar entregas con Adobe Campaign
feature: Email, Push, SMS, Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: cb6094eb-0010-4c62-9589-3b52fd60c2c2
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '2936'
ht-degree: 66%

---

# Prácticas recomendadas de envíos {#delivery-best-practices}

Lea las siguientes prácticas recomendadas con las funciones de envío de Campaign.

## Optimización de las envíos {#optimize-delivery}

Antes de empezar a crear envíos, puede realizar varias acciones para proteger y optimizar el proceso de envío de forma ascendente. En la siguiente sección se describen las prácticas recomendadas y los procedimientos recomendados para una configuración óptima de Adobe Campaign.

### Rendimiento de la plataforma

Varios factores pueden afectar directamente al rendimiento del servidor y ralentizar la plataforma de Campaign:

* Número y tipo de [elementos de personalización](../send/personalize.md): la personalización en correos electrónicos extrae datos de la base de datos para cada destinatario. en el caso de muchos elementos de personalización, la cantidad de datos necesarios para preparar la entrega es mayor. Esto puede ralentizar la plataforma. Obtenga más información acerca de las protecciones de personalización en [esta sección](../send/personalize.md#perso-guardrails).

* Carga del servidor: Cuando el servidor de marketing gestiona muchas tareas diferentes al mismo tiempo, puede ralentizar el rendimiento. El servidor de marketing debe coordinar todos los datos entrantes y salientes de todos los envíos para garantizar que los datos sean correctos y oportunos.
Para evitarlo, coordine la programación de las entregas con los demás miembros de su equipo para garantizar el mejor rendimiento.

* Ejecución del flujo de trabajo: La monitorización de sus flujos de trabajo es esencial para evitar problemas de rendimiento de la plataforma. Siga las directrices enumeradas [en este documento](../../automation/workflow/workflow-best-practices.md#execution-and-performance).

* Conéctese a sus [funciones de Panel de control de Campaign de Campaign](https://experienceleague.adobe.com/en/docs/control-panel/using/discover-control-panel/key-features){target="_blank"} para monitorizar su plataforma mediante las funciones de [supervisión del rendimiento](https://experienceleague.adobe.com/en/docs/control-panel/using/performance-monitoring/about-performance-monitoring){target="_blank"}.

#### Administración de cuarentena {#quarantine-management}

Le conviene mantener buenos procesos de gestión de cuarentenas.

Al comenzar a enviar correos electrónicos en una nueva plataforma, puede utilizar una lista de direcciones que no esté totalmente confirmada. Si realiza envíos a direcciones no válidas o a direcciones honeypot (bandejas de entrada creadas únicamente para engañar a remitentes de correo electrónico no deseado), la reputación de su plataforma comenzará a reducirse. Unos procesos de administración de cuarentena adecuados ayudan a mantener la calidad de la dirección, evitar la lista de bloqueados de los proveedores de acceso a internet, y reducir la tasa de errores para acelerar los envíos y el rendimiento.


Obtenga más información sobre cómo iniciar una nueva plataforma en la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/ac-starting-new-platform){target="_blank"}.

Las recomendaciones técnicas se enumeran en [esta sección](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations){target="_blank"}.


+++ **Lea algunas prácticas recomendadas**

* Si tiene una lista de direcciones no válidas, Adobe recomienda importarlas a la tabla de cuarentenas, a través de **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** > **[!UICONTROL Non deliverables and addresses]**.

* Los destinatarios cuyas direcciones están en cuarentena se excluyen de forma predeterminada durante el análisis de envío: no están segmentados. Esto acelera las entregas, ya que la tasa de error afecta significativamente a la velocidad de entrega. Una dirección de correo electrónico se puede poner en cuarentena, por ejemplo, cuando la bandeja de entrada está llena o si la dirección no existe.
Adobe Campaign administra las direcciones erróneas según el tipo de error devuelto. [Más información sobre las cuarentenas](../send/quarantines.md)

* Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como correo no deseado si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, la cuarentena le permite evitar ser incluido en la lista de bloqueados de bloqueados por estos proveedores.

+++



### Mecanismo de inclusión doble {#double-opt-in}

Para evitar el envío de mensajes a direcciones no válidas, limitar las comunicaciones incorrectas y mejorar la reputación del remitente, Adobe recomienda implementar un mecanismo de inclusión doble para la confirmación posterior a la suscripción. Esto ayuda a garantizar la suscripción intencionada de un destinatario.

## Uso de plantillas {#use-templates}

Las plantillas de envíos ofrecen una mayor eficiencia al proporcionar escenarios listos para usar para los tipos de actividades más comunes. Con las plantillas, los especialistas en marketing pueden implementar nuevas campañas con una personalización mínima en un período de tiempo más corto. [Más información sobre las plantillas de envío](../send/create-templates.md).

### Subdominios y marca {#subdomains-and-branding}

Cuando se gestionan varias marcas en Adobe Campaign, Adobe recomienda tener un subdominio por marca. Por ejemplo, un banco puede tener varios subdominios correspondientes a cada una de sus agencias regionales. Si un banco posee el dominio bluebank.com, sus subdominios pueden ser @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, etc. Tener una plantilla de envíos para cada subdominio le permite utilizar los parámetros preconfigurados adecuados para cada una de sus marcas, lo que evita errores y le ahorra tiempo. Obtenga más información acerca de la marca de subdominios en la [documentación de Panel de control de Campaign de Campaign](https://experienceleague.adobe.com/en/docs/control-panel/using/subdomains-and-certificates/subdomains-branding){target="_blank"}.

### Configuración de direcciones {#configure-addresses}

Asegúrese de aplicar las siguientes directrices:

* La dirección del remitente es obligatoria para permitir que se envíe un correo electrónico. Algunos ISP (proveedores de servicios de Internet) comprueban la validez de la dirección del remitente antes de aceptar mensajes.
* Una dirección mal formada puede resultar en que el servidor receptor la rechace. Debe asegurarse de que se proporciona una dirección correcta.
* La dirección debe identificar explícitamente al remitente. El dominio debe ser propiedad del remitente y estar registrado en él.
* Adobe recomienda crear cuentas de correo electrónico que se correspondan con las direcciones especificadas para envíos y respuestas. Consulte con el administrador del sistema de mensajería.

+++ **Pasos para configurar direcciones en la interfaz de usuario de Campaign**

Para configurar direcciones en la interfaz de Campaign, siga los pasos a continuación:

1. En la [plantilla de envíos](../send/create-templates.md), haga clic en el vínculo **[!UICONTROL From]**. En la ventana **[!UICONTROL Email header parameters]**, introduzca la configuración.

1. En el campo **[!UICONTROL Sender address]**, asegúrese de que el dominio de dirección sea el mismo que el subdominio que delegó en Adobe. Puede cambiar la parte que precede a &#39;@&#39;, pero no la dirección de dominio.

1. En el campo **[!UICONTROL From]**, utilice un nombre fácilmente identificable por los destinatarios, como el nombre de su marca, para aumentar la velocidad de apertura de sus envíos. Para mejorar aún más la experiencia del destinatario, puede agregar el nombre de una persona como, por ejemplo, &quot;Emma de Megastore&quot;.

1. En los campos **[!UICONTROL Reply address text]**, la dirección del remitente se utiliza de forma predeterminada para las respuestas. Sin embargo, Adobe recomienda utilizar una dirección real existente, como el servicio de atención al cliente de su marca. En este caso, si un destinatario envía una respuesta, el servicio de atención al cliente podrá atenderla.

### Configuración de un grupo de control {#set-up-control-group}

Una vez entregado el envío, puede comparar el comportamiento de los destinatarios excluidos con el de los destinatarios que sí recibieron el envío. Puede medir la eficacia de sus campañas. Obtenga más información sobre los grupos de control [en esta sección](../../automation/campaigns/marketing-campaign-target.md#add-a-control-group).

### Uso de tipologías para aplicar filtros o reglas de control {#create-typologies}

Una tipología contiene reglas de comprobación que se aplican durante la fase de análisis antes de enviar un mensaje.

En la pestaña **[!UICONTROL Typology]** de las propiedades de la plantilla, puede seleccionar una tipología personalizada si es necesario.

Por ejemplo, para controlar mejor el tráfico saliente, puede definir qué direcciones IP se pueden utilizar definiendo una afinidad por subdominio y creando una tipología por afinidad. Las afinidades se definen en el archivo de configuración de la instancia. Póngase en contacto con el administrador de Adobe Campaign.

Para obtener más información sobre tipologías, consulte [esta sección](../../automation/campaign-opt/campaign-typologies.md).

## Optimizar el contenido {#optimize-content}

### Creación de contenido personalizado {#perso-content}

Para personalizar los mensajes, puede utilizar los datos de destinatarios almacenados en la base de datos o recopilados mediante seguimiento, páginas de aterrizaje, suscripciones, etc. Los conceptos básicos de la personalización se presentan en [esta sección](../send/personalize.md).

+++ **Lea algunas prácticas recomendadas**

* Compruebe la configuración de personalización: asegúrese de que el contenido del mensaje está diseñado correctamente para evitar errores, que pueden estar relacionados con la personalización. Una etiqueta personalizada de Adobe Campaign siempre tiene el siguiente formulario: `<%=table.field%>`. El uso incorrecto de parámetros en bloques de personalización puede ser un problema. Por ejemplo: las variables en JavaScript deben usarse de la siguiente manera:

  ``
  <%
  var brand = "xxx"
  %>
  ``

  Para obtener más información acerca de los bloques personalizados, consulte [esta sección](../send/personalization-blocks.md).

* Preparar datos de personalización: puede preparar datos de personalización en un flujo de trabajo para mejorar el análisis de preparación de envíos. Esto debe utilizarse especialmente si los datos de personalización proceden de una tabla externa a través del Acceso de datos federado (FDA). Esta opción se describe en [esta sección](../send/personalization-data.md#optimize-personalization)
+++

### Creación de contenido optimizado {#build-optimized-content}

Al crear sus correos electrónicos, aplique las prácticas recomendadas generales para el contenido del correo electrónico.

+++ **Lea algunas prácticas recomendadas**

* El correo electrónico debe tener un diseño sencillo

* Tenga en cuenta a los usuarios de dispositivos móviles

* Evite los correos electrónicos basados por completo en imágenes

* Utilice fuentes seguras para el correo electrónico

* Codifique caracteres especiales

+++


### Línea de asunto  {#subject-line-check}

Trabaje en la [línea de asunto](../send/personalization-fields.md#personalization-fields-uc) del correo electrónico para mejorar las tasas de apertura.


+++ **Lea algunas prácticas recomendadas**


* Evite los asuntos demasiado largos. Utilice un máximo de 50 caracteres

* Evite utilizar palabras de forma repetida, tales como “gratis” u “oferta”, que podrían considerarse como spam

* Evitar mayúsculas

* No utilice caracteres especiales como &quot;!&quot;, &quot;£&quot;, &quot;€&quot; o &quot;$&quot;

+++

### Página espejo {#mirror-page-check}

Incluya siempre un vínculo de página espejo. La posición preferida es la parte superior del correo electrónico. Obtenga más información acerca de la página espejo en [esta página](../send/mirror-page.md)

### Vínculo de cancelación de suscripción {#unsub-link-check}

El vínculo de cancelación de suscripción es esencial. Debe ser visible y válido, y el formulario debe ser funcional. De manera predeterminada, cuando se analiza el mensaje, una regla de tipología **[!UICONTROL Unsubscription link approval]** [integrada](../../automation/campaign-opt/control-rules.md) comprueba si se ha incluido un vínculo de no participación y genera una advertencia si falta.

Obtenga información sobre cómo insertar un vínculo de exclusión [en esta sección](../send/personalization-blocks.md).

+++ **Aplicar esta práctica recomendada**

Dado que siempre es posible cometer un error humano, compruebe que el vínculo de no participación funciona correctamente antes de cada envío. Por ejemplo, al enviar la prueba, asegúrese de que el vínculo sea válido, de que el formulario esté en línea y de que el campo `No longer contact this recipient ` se cambie a `Yes`.

+++

### Tamaño del correo electrónico {#email-size-check}

Para evitar problemas de rendimiento o de entrega, el tamaño máximo recomendado de un correo electrónico es de unos **35 KB**. Para comprobar el tamaño del mensaje, examine la ficha **[!UICONTROL Preview]** y elija un perfil de prueba. Una vez generado, el tamaño del mensaje se muestra en la esquina superior derecha.


+++ **Lea algunas prácticas recomendadas**

* Eliminar estilos redundantes o que no utilice

* Mover parte del contenido del correo electrónico a una página de aterrizaje

* Minimizar el código

Asegúrese de probar los cambios antes del envío final.

+++


### Longitud del SMS {#sms-length-check}

De forma predeterminada, el número de caracteres de un SMS cumple con los estándares del GSM (Sistema Global de Comunicaciones Móviles). Los mensajes SMS con codificación GSM están limitados a 160 caracteres, o a 153 caracteres por SMS en el caso de los mensajes enviados en varias partes.


+++ **Lea algunas prácticas recomendadas**

* Para mantener todos los caracteres en sus mensajes SMS tal como están, para no alterar nombres adecuados por ejemplo, no habilites la transliteración.

* Sin embargo, si sus mensajes SMS contienen muchos caracteres que no se tienen en cuenta en el estándar GSM, habilite la transliteración para limitar los costes de envío de mensajes. Obtenga más información [en esta sección](../send/sms/smpp-external-account.md#smpp-transliteration).

* Puede aplicar transliteraciones SMS, que consiste en reemplazar un carácter de un SMS por otro cuando el estándar GSM no tiene en cuenta ese carácter. Tenga en cuenta que la inserción de campos de personalización en el contenido del mensaje SMS puede introducir caracteres que no se tienen en cuenta con la codificación GSM. Como administrador de Campaign, puede habilitar la transliteración de caracteres marcando la casilla correspondiente en la pestaña de configuración del canal SMPP de la **[!UICONTROL External account]** correspondiente. [Más información](../send/sms/smpp-external-account.md#smpp-transliteration)

+++

### Prevención de envío de archivos adjuntos

Los archivos adjuntos son uno de los vectores más comunes de propagación de software malicioso, especialmente cuando se envían en lotes. Incluya un enlace seguro al documento en lugar de adjuntar el propio documento. Esto garantiza un nivel adicional de seguridad para evitar una redistribución no deseada y reduce considerablemente las posibilidades de que el mensaje se rechace en las puertas de enlace de correo electrónico entrantes por motivos de seguridad o tamaño del mensaje.

<!--
## Work on formatting {#formatting}

To avoid common formatting errors, check the following elements:

* Correct **date formatting**: Adobe Campaign provides date formatting functions for the JavaScript templates and XSL stylesheets. [Learn more](formatting.md#date-display)

* Usage of **authorized characters** in emails: the list of valid characters for email addresses is defined in the "XtkEmail_Characters" option. Learn how to access Campaign options [in this section](../../installation/using/configuring-campaign-options.md). To correctly handle special characters, Adobe Campaign needs to be installed in Unicode. 

* Configuration of **Email Authentication**: make sure that the email headers contain the DKIM signature. DKIM (Domain Keys Identified Mail) authentication allows the receiving email server to verify that a message was indeed sent by the person or entity it claims it was sent by, and whether the message content was altered in between the time it was originally sent (and DKIM "signed") and the time it was received. This standard typically uses the domain in the From or Sender header. For more on this, refer to the [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).-->

## Administración de imágenes {#manage-images}

Estas son algunas directrices específicas para optimizar imágenes para la campaña de marketing por correo electrónico.

### Prevención del bloqueo de imágenes {#image-blocking}

Algunos clientes de correo electrónico bloquean las imágenes de forma predeterminada y los usuarios pueden cambiar su configuración para bloquearlas y ahorrar en el uso de los datos.  Por lo tanto, si las imágenes no se descargan, se puede perder todo el mensaje.

+++ Para evitarlo, puede aplicar estas prácticas recomendadas

* Evite los correos electrónicos basados por completo en imágenes. Equilibre el contenido con la imagen y el texto.

* Si se debe incluir texto en una imagen, use texto alternativo y de título para que el mensaje tenga el efecto deseado. Establezca el formato de texto alternativo o de título para mejorar el aspecto del diseño.

* Evite el uso de imágenes de fondo, ya que algunos servicios de correo electrónico no las admiten.
+++

### Conversión de imágenes en interactivas {#responsive-images}

Intente que las imágenes sean interactivas y se puedan cambiar de tamaño para que sean visibles en todos los contextos y dispositivos. Tenga en cuenta que esto puede tener un impacto en los costes, ya que se tarda más en crear.

### Use referencias de imagen absoluta {#absolute-images}

Para que sean accesibles desde el exterior, las imágenes utilizadas en los mensajes de correo electrónico y recursos públicos vinculados a las campañas deben estar presentes en un servidor accesible de forma externa.

* Desde el asistente de envíos, puede importar una página HTML que contenga imágenes o insertar imágenes directamente utilizando el editor HTML mediante el icono **[!UICONTROL Image]**.

* Si las imágenes no se muestran, compruebe que estén disponibles en el servidor. Para ello, vaya a la pestaña **Source** de su envío. Busque las imágenes, y copie y pegue la dirección URL de cada imagen en un navegador web. Si no se muestran las imágenes, póngase en contacto con el administrador de TI o con el proveedor de terceros que proporcione el contenido de envío.

### Previsualización y prueba del mensaje {#preview-msg}

Adobe recomienda previsualizar el mensaje para comprobar su personalización y cómo verán los destinatarios su entrega.

En el asistente de envíos, la subpestaña **[!UICONTROL Preview]** permite ver el renderizado de cada contenido para un destinatario. Los campos personalizados y los elementos condicionales del contenido se sustituyen por la información correspondiente del perfil seleccionado. [Más información](../send/preview-and-proof.md).


<!--
*  An automatic anti-spam checking is performed during each preview. In the **[!UICONTROL Preview]** sub-tab, check [SpamAssassin](spamassassin.md) spam scoring.  Click **[!UICONTROL More...]** to find out more about the warning.  Before doing so, make sure SpamAssassin is correctly installed and configured on the Adobe Campaign application server. [Learn more](../../installation/using/configuring-spamassassin.md)
-->

## Definición de la audiencia correcta {#define-the-right-audience}

La población objetivo es clave: cree sus listas con cuidado, pruebe sus correos electrónicos con clientes de correo electrónico y dispositivos móviles populares, y asegúrese de que sus listas de correos electrónicos estén actualizadas (sin direcciones desconocidas u obsoletas). También puede enviar pruebas que ayuden a configurar un ciclo de validación completo. Puede obtener más información sobre los públicos en [esta sección](../audiences/gs-audiences.md).

### Selección de la audiencia de destino correcta {#target-the-right-audience}

Cuando tenga preparado el contenido, debe definir cuidadosamente quién recibirá el mensaje.

Para que su envío se realice correctamente, envíe el contenido personalizado más relevante a los destinatarios adecuados. Adobe Campaign le permite crear la población más adecuada: puede seleccionar destinatarios según su edad, ubicación, lo que compraron, si hicieron clic en un vínculo en un envío anterior, etc. Con Adobe Campaign, también puede definir perfiles, grupos de control y direcciones semilla de prueba para asegurarse de que el destinatario es correcto.

### Asignaciones de destino {#target-mappings}

En Campaign, de forma predeterminada, las plantillas de envíos tienen como destino **Destinatarios**. Adobe Campaign ofrece otros destinos de mapeo para las entregas, que puede cambiar según sus necesidades. Por ejemplo, puede enviar a visitantes cuyos perfiles se hayan recopilado a través de redes sociales o a visitantes suscritos a un servicio informativo.

Estas asignaciones se presentan [en esta sección](../audiences/target-mappings.md).

### Destinatarios externos {#external-recipients}

Puede enviar a destinatarios que estén almacenados en un archivo externo en lugar de guardarlos en la base de datos. Obtenga más información [en esta sección](create-message.md#select-external-recipients-selecting-external-recipients).

<!--
### Send to your subscribers {#send-to-subscribers}

To send messages to the subscribers of a newsletter, you can directly target the subscribers to the corresponding information service. Learn more [in this section](../audiences/).-->

### Destinatarios de prueba {#test-recipients-seed-addresses}

Para probar el envío, utilice pruebas antes de enviar al destinatario principal.

Asegúrese de seleccionar los destinatarios de prueba adecuados, ya que validan el formulario y el contenido del mensaje. Los pasos para definir los destinatarios de prueba se presentan [en esta sección](create-message.md#select-the-recipients-of-proof-messages-select-the-proof-target).


### Deduplicación de direcciones {#deduplicate-addresses}

Es importante evitar tener direcciones de correo electrónico duplicadas, ya que esto puede perjudicar al destinatario:

* El mismo mensaje se puede enviar más de una vez cuando se divide un destinatario.

* Si un destinatario cancela la suscripción después de recibir un mensaje, su perfil duplicado seguirá recibiendo mensajes futuros.

Las direcciones duplicadas protegen su reputación de envío y garantizan una buena gestión de cuarentena.

**Temas relacionados:**

* [Actividad de deduplicación](../../automation/workflow/deduplication.md).
* [Caso de uso: uso de la funcionalidad de combinación de la actividad de anulación de duplicación](../../automation/workflow/deduplication-merge.md).


## Realice todas las comprobaciones necesarias antes de enviar {#perform-all-checks}

Una vez que el mensaje esté listo, asegúrese de que su contenido se muestra correctamente en todos los dispositivos y no contiene ningún error, como una personalización incorrecta o vínculos rotos. Antes de enviar el mensaje, compruebe que los parámetros y la configuración se adecuan al envío.

Los pasos para validar un envío se presentan [en esta sección](../send/preview-and-proof.md).

<!--
### Inbox rendering {#inbox-and-email-rendering}

Inbox rendering enables you to preview your messages on major email clients, scan content and reputation, discover how recipients are reading messages.

**Tips**:

* You can view the sent message in the different contexts in which it may be received: webmail, message service, mobile, etc.

* Inbox rendering capabilities are crucial to identifying whether your email campaigns successfully make it past the filters of major ISPs (Internet Service Providers) and webmail services. Such tools send a pre-flight copy of an email to a network of test inboxes, so you can see how the message will display, or render, across these services. They may also include reports and code correction options that help you quickly identify and make fixes that improve deliverability.

Learn more [in this section](inbox-rendering.md).-->

### Mensajes de prueba {#proof-messages}

El envío de pruebas le permite comprobar el vínculo de no participación, la página espejo y cualquier otro vínculo, validar el mensaje, comprobar que se muestran las imágenes, detectar posibles errores, etc. También es posible que desee comprobar el diseño y el procesamiento en distintos dispositivos.

<!--
### Set up A/B testing deliveries {#a-b-testing-deliveries}

If you have several contents for an email delivery, you can use A/B testing to find out which version will have the biggest impact on the targeted population.

**Tips**:

* Send the different versions to some of your recipients

* Select the one with the highest success rate and send it to the rest of your target

Learn more [in this section](get-started-a-b-testing.md).-->

### Asegúrese de que el mensaje se haya enviado {#make-sure-your-message-is-delivered}

Finalmente, maximice sus posibilidades y aproveche la potencia de Adobe Campaign para garantizar que su mensaje se envía a los destinatarios relevantes.

#### Pase por un proceso de validación

Puede definir un proceso de validación completo, que incluye los operadores y grupos de Adobe Campaign, para validar el contenido del mensaje y el destinatario. Esto garantizará una monitorización y un control completos de los distintos procesos de la campaña: segmentación, contenido, presupuesto, extracción y envío de una prueba. Según sus permisos, los usuarios pueden recibir notificaciones, recibir pruebas y validar o rechazar el mensaje. Obtenga más información [en esta sección](../../automation/campaigns/marketing-campaign-approval.md).

#### Uso de oleadas

Puede aumentar progresivamente el volumen enviado mediante oleadas. Esto evitará que sus mensajes se marquen como correo no deseado o para limitar el número de mensajes por día. Mediante las oleadas puede dividir los envíos en varios lotes en lugar de enviar volúmenes altos de mensajes al mismo tiempo. Obtenga más información [en esta sección](../send/configure-and-send.md#sending-using-multiple-waves).

#### Priorización de mensajes

Puede configurar el orden de envío de sus envíos indicando el nivel de prioridad. Para ello:

1. Edite las propiedades del envío y seleccione la pestaña **[!UICONTROL Delivery]**.

1. Defina el nivel de prioridad del envío en una escala de **[!UICONTROL Very low]** a **[!UICONTROL Very high]**.

>[!NOTE]
>
>No es posible definir el orden de envío de mensajes desde un envío.

<!--
#### Setup IP Affinities

To better control the outbound SMTP traffic, you can manage affinities by defining which specific IP addresses can be used for each affinity. This lets you restrict the number of emails for specific deliveries towards machines or output addresses. For example, you can use one affinity per country or sub-domain. You can then create one typology per country and link each affinity to the corresponding typology.

You can:

* Define the IP affinities in the serverConf.xml configuration file. [Learn more](../../installation/using/configuring-campaign-server.md#managing-outbound-smtp-traffic-with-affinities)

* For each IPAffinity element, declare the IP addresses that can be used. [Learn more](../../installation/using/email-deliverability.md#list-of-ip-addresses-to-use)

* In the [typology](../../campaign-opt/using/about-campaign-typologies.md) of your choice, use the **[!UICONTROL Managing affinities with IP addresses]** field to link deliveries to the delivery server (MTA) which manages the said affinity. [Learn more](../../campaign-opt/using/applying-rules.md#control-outgoing-smtp-traffic).

* Once the email is sent, check the header to verify which IP address the delivery was sent from. Your email administrator should help you obtain the header information.

* For SMS deliveries, make sure that the SMS channel has a dedicated affinity limited to **one** application server container. [Learn more](../../installation/using/configure-delivery-settings.md#managing-outbound-smtp-traffic-with-affinities)

>[!NOTE]
>
>Most of these steps can only be performed by an expert user.-->

#### Uso de tipologías

Puede utilizar reglas de tipología para excluir parte del destinatario según criterios específicos. Esto garantiza que los mensajes enviados respondan de la mejor forma a las necesidades y expectativas de los clientes, de acuerdo con las políticas de comunicación de la compañía. Por ejemplo, puede filtrar los destinatarios menores de edad del objetivo de su boletín informativo. Obtenga más información [en este ejemplo](../../automation/campaign-opt/filtering-rules.md).


## Seguimiento y monitorización {#track-and-monitor}

¿Ha hecho clic en el botón **Enviar**? Veamos qué pasa. Una vez entregado el envío, Adobe Campaign le permite realizar un seguimiento de los mensajes enviados y descubrir cómo reaccionan sus destinatarios al envío. Esto le ayudará a mejorar los envíos futuros y a optimizar sus próximas campañas.

## Monitorización de las entregas {#monitoring-deliveries}

Para controlar sus campañas, debe asegurarse de que el mensaje se haya enviado a sus destinatarios.

Desde el panel de entregas de Campaign, puede comprobar los mensajes procesados y los registros de auditoría de entregas. También puede controlar el estado de los mensajes en los registros de envío.

[Obtenga más información acerca de la monitorización de entregas en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/track-and-monitor.html){target="_blank"}


## Seguimiento del comportamiento {#track-behaviour}

Para conocer mejor el comportamiento de sus destinatarios, puede rastrear cómo reaccionan a un envío: recepción, apertura, clics en vínculos, suscripciones, etc. En Campaign, esta información se muestra en la pestaña **Tracking** de los destinatarios a quienes se realizó la entrega y en la pestaña Tracking de la entrega.

El seguimiento de mensajes está activado de forma predeterminada. Para configurar direcciones URL, seleccione la opción Mostrar direcciones URL en la sección inferior del asistente de envíos. Por cada dirección URL del mensaje, puede elegir si desea activar el seguimiento.


[Obtenga más información acerca de las funcionalidades de seguimiento en la documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/tracking-messages/how-to-configure-tracked-links.html#sending-messages){target="_blank"}
