---
solution: Campaign v8
product: Adobe Campaign
title: Trabajo con Campaign y Adobe Analytics
description: Aprenda a trabajar con Campaign y Adobe Analytics
feature: Información general
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 556cd7727c7c2bf0158d59d71ae0131b4c1013ee
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 43%

---

# Trabajo con Campaign y Adobe Analytics


## Conector de Adobe Analytics

Puede configurar los conectores de Adobe Analytics para integrar Campaign y Analytics.

El conector de Adobe Analytics permite que Adobe Campaign y Adobe Analytics interactúen mediante el complemento **Conectores de Web Analytics**. Esta integración comparte datos de Analytics en Campaign como segmentos relacionados con el comportamiento del usuario tras un correo electrónico. Por el contrario, envía indicadores y atributos de las campañas de correo electrónico que envía Adobe Campaign a Adobe Analytics: conector de datos.

Con Adobe Analytics Connector, Adobe Campaign puede medir la audiencia de Internet (Web Analytics). Gracias a estas integraciones, Adobe Campaign puede recuperar los datos del comportamiento del visitante para uno o más sitios después de una campaña de marketing y (después del análisis) ejecutar nuevas campañas con la intención de convertirlos en compradores. Por el contrario, las herramientas de Web Analytics permiten que Adobe Campaign reenvíe indicadores y atributos de campaña a sus plataformas.

Los campos de acción de cada herramienta son los siguientes:

* **Adobe Analytics**

   * marca las campañas de email iniciadas con Adobe Campaign
   * guarda el comportamiento del destinatario en el sitio visitado después de hacer clic en el email de la campaña, en forma de segmentos. Los segmentos están relacionados con productos abandonados (vistos pero no añadidos al carro ni comprados), compras o abandonos del carro de compras.

* **Adobe Campaign**

   * envía los indicadores y atributos de campaña al conector, que a su vez los reenvía a la herramienta Web Analytics
   * recupera y analiza segmentos
   * activa una campaña de remarketing

Obtenga más información sobre Adobe Campaign y Adobe Analytics en [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)

: globo_voz:  Como usuario de Cloud Services administrados, [póngase en contacto con Adobe](../start/campaign-faq.md#support) para integrar Adobe Analytics Data Connector con Campaign.


## Activadores de Experience Cloud

Puede utilizar Déclencheur de Experience Cloud para conectar datos entre Adobe Campaign y Adobe Analytics mediante la canalización. La canalización recupera las acciones o déclencheur del usuario desde el sitio web. El abandono del carro de compras es un ejemplo de activador. Los activadores se procesan en Adobe Campaign para enviar correos electrónicos en tiempo casi real.

Obtenga más información sobre Adobe Campaign y los Déclencheur de Experience Cloud en [esta página](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en).

: globo_voz:  Como usuario de Cloud Services administrados, [póngase en contacto con el Adobe](../start/campaign-faq.md#support) para implementar los déclencheur de Experience Cloud con Campaign.
