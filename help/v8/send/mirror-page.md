---
title: Añadir un vínculo a la página espejo
description: Aprenda a añadir y administrar el vínculo a la página espejo
feature: Email
role: User
level: Beginner
exl-id: 7bf3937c-484d-4404-8a9b-de7a10f5455a
source-git-commit: b333db04dd10cc28956959a446f6567e2a89b2d4
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 56%

---

# Vínculo a la página espejo {#mirror-page}

## Acerca de la página espejo {#about-mirror-page}

La página espejo es una versión en línea de su correo electrónico.

Aunque la mayoría de los clientes de correo electrónico procesan las imágenes sin problemas, algunos ajustes preestablecidos pueden evitar mostrar las imágenes por motivos de seguridad. Los usuarios pueden navegar a la página espejo de un correo electrónico, por ejemplo, si están experimentando problemas de renderización o imágenes rotas al intentar verlo en su bandeja de entrada. También se recomienda proporcionar una versión en línea por motivos de accesibilidad o para fomentar el uso compartido en redes sociales.

La página espejo generada por Adobe Campaign contiene todos los datos de personalización.

![ejemplo de vínculo espejo](assets/mirror-page-link.png){width="600" align="left"}

## Añadir un vínculo a la página espejo {#link-to-mirror-page}

Se recomienda insertar un vínculo a la página espejo. Este vínculo puede ser, por ejemplo, “Ver este correo electrónico en su navegador” o “Leer esto en línea”. A menudo se encuentra en el encabezado o pie de página del correo electrónico.

En Adobe Campaign, puede insertar un vínculo a la página espejo en el contenido del correo electrónico mediante el **bloque de personalización** específico. El bloque de personalización integrado **Vínculo a página espejo** inserta el siguiente código en el contenido del correo electrónico: `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="800" align="left"}


Para obtener más información sobre cómo insertar bloques de contenido personalizado, consulte [Bloques de personalización](personalization-blocks.md).

## Administrar la generación de páginas espejo {#mirror-page-generation}

De forma predeterminada, Adobe Campaign genera automáticamente la página espejo si el contenido del correo electrónico no está vacío y si contiene un vínculo a la página espejo (también conocido como vínculo espejo).

Puede controlar el modo de generación de la página espejo del correo electrónico. Las opciones están disponibles en las propiedades del envío. Para acceder a estas opciones:

1. Vaya a la pestaña **[!UICONTROL Validity]** de las propiedades de correo electrónico.
1. En la sección **Administración de páginas espejo**, marque la lista desplegable **[!UICONTROL Mode]**.

![](assets/mirror-page-generation.png){width="800" align="left"}

Además del modo predeterminado, están disponibles las siguientes opciones:

* **[!UICONTROL Force the generation of the mirror page]**: utilice este modo para generar la página espejo aunque no se inserte ningún vínculo a la página espejo en la entrega.
* **[!UICONTROL Do not generate the mirror page]**: utilice este modo para evitar generar una página espejo, aunque el vínculo esté presente en la entrega.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: cuando el vínculo de la página espejo no esté presente en el contenido del correo electrónico, utilice esta opción para habilitar el acceso al contenido de la página espejo, en la ventana del registro de envíos, como se detalla a continuación.

## Buscar un destinatario en la página espejo {#mirror-page-access}

Puede acceder al contenido de la página espejo de un destinatario específico de una entrega, con datos de personalización.

Para acceder a esta página espejo:

1. Una vez entregado el envío, ábralo y navegue hasta su pestaña **[!UICONTROL Delivery]**.

1. Seleccione un destinatario y haga clic en el vínculo **[!UICONTROL Display the mirror page for this message...]**.

   ![](assets/mirror-page-display.png){width="800" align="left"}

   La página espejo se muestra en una pantalla dedicada, con datos de personalización para el destinatario seleccionado.
