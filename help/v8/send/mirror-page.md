---
title: Añadir un vínculo a la página espejo
description: Aprenda a añadir y administrar el vínculo a la página espejo
feature: Email
role: User
level: Beginner
source-git-commit: d8ceefe1dd56aecb810878d99395ac900f889c2e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Vínculo a la página espejo{#mirror-page}

## Acerca de la página espejo{#about-mirror-page}

La página espejo es una versión en línea de su correo electrónico.

Aunque la mayoría de los clientes de correo electrónico procesan imágenes sin problemas, algunos ajustes preestablecidos pueden evitar mostrar imágenes por motivos de seguridad. Los usuarios pueden navegar a la página espejo de un correo electrónico, por ejemplo, si están experimentando problemas de renderización o imágenes rotas al intentar verlo en su bandeja de entrada. También se recomienda proporcionar una versión en línea por motivos de accesibilidad o para fomentar el uso compartido en redes sociales.

La página espejo generada por Adobe Campaign contiene todos los datos de personalización.

![](assets/mirror-page-link.png)


## Añadir un vínculo a la página espejo{#link-to-mirror-page}

Se recomienda insertar un vínculo a la página espejo. Este enlace puede ser, por ejemplo, &quot;Ver este correo electrónico en tu navegador&quot; o &quot;Leer esto en línea&quot;. A menudo se encuentra en el encabezado o pie de página del correo electrónico.

En Adobe Campaign, puede insertar un vínculo a la página espejo en el contenido del correo electrónico mediante la variable **bloque personalizado**. El **Vínculo a página espejo** el bloque personalizado inserta el siguiente código en el contenido del correo electrónico: `<%@ include view='MirrorPage' %>`.

<!--For more on personalization blocks insertion, refer to [Personalization blocks](personalization-blocks.md).-->

## Generación de páginas espejo{#mirror-page-generation}

De forma predeterminada, Adobe Campaign genera automáticamente la página espejo si el contenido del correo electrónico no está vacío y si contiene un vínculo a la página espejo (también conocido como vínculo espejo).

Puede controlar el modo de generación de la página espejo del correo electrónico. Las opciones están disponibles en las propiedades de envío. Para acceder a estas opciones:

1. Vaya a la **[!UICONTROL Validity]** de las propiedades de correo electrónico.
1. En el **Administración de páginas espejo** , marque **[!UICONTROL Mode]** lista desplegable.

![](assets/mirror-page-generation.png)

Además del modo predeterminado, están disponibles las siguientes opciones:

* **[!UICONTROL Force the generation of the mirror page]**: utilice este modo para generar la página espejo aunque no haya ningún vínculo a la página espejo insertado en la entrega.
* **[!UICONTROL Do not generate the mirror page]**: utilice este modo para evitar generar una página espejo, incluso si el vínculo está presente en la entrega.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: utilice esta opción para habilitar el acceso al contenido de la página espejo, con datos de personalización, en la ventana del &quot;log&quot; de envío. Para acceder a esta página espejo: una vez realizado el envío, ábralo y busque su **[!UICONTROL Delivery]** pestaña . Seleccione un destinatario y haga clic en el botón **[!UICONTROL Display the mirror page for this message...]** vínculo. La página espejo se muestra en una nueva pestaña.

