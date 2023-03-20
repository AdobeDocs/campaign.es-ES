---
title: Personalización del contenido
description: Obtenga información sobre cómo personalizar el contenido del mensaje
feature: Personalization
role: User
level: Beginner
source-git-commit: 4885f15c71d2be27dc32a239fb22abc3a96503c7
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 29%

---

# Personalización del contenido {#personalize-content}

Para sacar el máximo partido a cada campaña de marketing, Adobe Campaign le ofrece una forma de ofrecer contenido personalizado que hable con los clientes a su nivel. En función de los datos de perfil, las capacidades de personalización para crear una experiencia personalizada para diferentes grupos e individuos: puede adaptar los mensajes a cada destinatario específico aprovechando los datos y la información que tiene sobre ellos. Puede ser su nombre, intereses, dónde viven, qué compraron y mucho más.

Adobe Campaign simplifica la personalización: puede mostrar diferentes tipos de contenido personalizados para cada destinatario con un solo [plantilla de correo electrónico](create-templates.md). En los mensajes transaccionales, como los correos electrónicos de confirmación de compra o abandono del carro de compras, incluya información de listas de productos para cada individuo dentro de una sola plantilla de correo electrónico.


## Estrategias de personalización {#personalization-strategy}

Utilice Campaign para crear contenido dinámico y enviar mensajes personalizados. Las funcionalidades de personalización se pueden combinar para mejorar sus mensajes y crear una experiencia de usuario personalizada.

Puede personalizar el contenido del mensaje:

* Inserción dinámica **campos personalizados**

   Los campos personalizados se utilizan para la personalización de primer nivel de los mensajes. Puede seleccionar cualquier campo disponible en la base de datos desde el editor de personalización. Para una entrega, se puede seleccionar cualquier campo relacionado con el destinatario, el mensaje o la entrega. Estos atributos de personalización se pueden insertar en la línea de asunto o en el cuerpo de los mensajes. [Más información](personalization-fields.md).

   La siguiente sintaxis inserta la ciudad del destinatario en el contenido: &lt;%= recipient.location.city %>.

* Inserción predefinida **bloques de contenido**

   Campaign viene con un conjunto de bloques personalizados que contienen una renderización específica que puede insertar en los envíos. Por ejemplo, puede añadir un logotipo, un mensaje de saludo o un vínculo a la página espejo del mensaje. Los bloques de contenido están disponibles desde una entrada dedicada en el editor de personalización. [Más información](personalization-blocks.md).

* Crear **contenido condicional**

   Configure contenido condicional para añadir personalización dinámica en función del perfil del destinatario, por ejemplo. Los bloques de texto o las imágenes se insertan cuando una condición concreta es verdadera. [Más información](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Seguridad y recomendaciones{#perso-guardrails}

### Tiempo de espera de personalización{#perso-timeout}

Para mejorar la protección de la entrega, puede establecer un período de espera para la fase de personalización.

En la pestaña **[!UICONTROL Delivery]** de **[!UICONTROL Delivery properties]**, seleccione un valor máximo en segundos para la opción **[!UICONTROL Maximum personalization run time]**.

Durante la vista previa o la entrega, si la fase de personalización supera el tiempo máximo establecido en este campo, el proceso se anula con un mensaje de error y la entrega falla.

El valor predeterminado es 5 segundos.

Si establece esta opción en 0, no va a haber límite de tiempo para la fase de personalización.


### Variables internas{#internal-variables}

Las siguientes variables son variables internas que pueden utilizarse para la personalización pero que no deben modificarse: **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **proposition**.


## Tutorial en vídeo {#personalization-video}

Descubra los distintos tipos de contenido dinámico, y aprenda a crear y aplicar bloques de personalización y afirmaciones condicionales a un envío.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)