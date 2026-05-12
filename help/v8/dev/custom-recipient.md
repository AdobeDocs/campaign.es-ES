---
title: Cambio de la tabla de destinatarios predeterminada
description: Aprenda a utilizar una tabla de destinatarios personalizada
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
TQID: https://experienceleague.adobe.com/W67Z2xVEBDpju5xlL2WiE5ZTzvrFmhuByMvfPb4x6nM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 149
ht-degree: 3%

---

# Usar una tabla de destinatarios personalizada{#gs-ac-custom-recipient}

Adobe Campaign incluye una tabla de perfil integrada: **nmsRecipient**. Esta tabla tiene una serie de campos predefinidos y tablas que se pueden ampliar fácilmente. Obtenga más información acerca de esta tabla en [esta página](datamodel.md#ootb-profiles).

La extensión de tabla integrada ofrece flexibilidad, pero no permite eliminar algunos campos o vínculos que no se utilicen. Como consecuencia, el uso de una tabla de destinatarios personalizada puede ser una buena opción cuando el modelo de datos difiere drásticamente de la estructura de tablas de destinatarios integrada de Campaign o si tiene un gran número de perfiles.  Sin embargo, este método requiere ciertas precauciones a la hora de implementarlo.

Aprenda a configurar la instancia para que utilice una tabla de destinatarios personalizada en la [documentación de Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target="_blank"}.