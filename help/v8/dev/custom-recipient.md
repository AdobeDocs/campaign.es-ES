---
title: Cambio de la tabla de destinatarios predeterminada
description: Aprenda a utilizar una tabla de destinatarios personalizada
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 3%

---

# Usar una tabla de destinatarios personalizada{#gs-ac-custom-recipient}

Adobe Campaign incluye una tabla de perfiles integrada: **nmsRecipient**. Esta tabla tiene una serie de campos predefinidos y tablas que se pueden ampliar fácilmente. Obtenga más información sobre esta tabla en [esta página](datamodel.md#ootb-profiles).

La extensión de tabla integrada ofrece flexibilidad, pero no permite eliminar algunos campos o vínculos que no se utilizan. Como consecuencia, el uso de una tabla de destinatarios personalizada puede ser una buena opción cuando el modelo de datos difiere drásticamente de la estructura de la tabla de destinatarios integrada en Campaign o si tiene un gran número de perfiles.  Sin embargo, este método requiere ciertas precauciones al implementarlo.

![](../assets/do-not-localize/book.png) Obtenga información sobre cómo configurar la instancia para que utilice una tabla de destinatarios personalizada en [Documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target=&quot;_blank&quot;}.