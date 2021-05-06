---
solution: Campaign Classic
product: campaign
title: Trabajo con Campaign y Adobe Analytics
description: Aprenda a trabajar con Campaign y Adobe Analytics
feature: Información general
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 48%

---

# Trabajo con Campaign y Adobe Analytics

## Activadores de Experience Cloud

Puede utilizar Déclencheur de Experience Cloud para conectar datos entre Adobe Campaign y Adobe Analytics mediante la canalización. La canalización recupera las acciones o déclencheur de los usuarios desde el sitio web. El abandono del carro de compras es un ejemplo de activador. Los activadores se procesan en Adobe Campaign para enviar correos electrónicos en tiempo casi real.

: globo_voz: Como usuario de Cloud Services administrados, [póngase en contacto con el Adobe](../start/support.md#support) para implementar los déclencheur de Experience Cloud con Campaign.

## Conectores de datos de Adobe Analytics

PARA ACTUALIZAR CON LA NUEVA INTEGRACIÓN

También puede configurar Adobe Analytics Data Connectors para integrar Campaign y Analytics.

Conectores de datos (anteriormente conocido como Adobe Genesis) permite que Adobe Campaign y Adobe Analytics interactúen mediante el paquete **Conectores de Web Analytics** . Esta integración comparte datos de Analytics en Campaign como segmentos relacionados con el comportamiento del usuario tras un correo electrónico. Por el contrario, envía indicadores y atributos de las campañas de correo electrónico que envía Adobe Campaign a Adobe Analytics: conector de datos.

Gracias a estas integraciones, Adobe Campaign puede recuperar los datos del comportamiento del visitante para uno o más sitios después de una campaña de marketing y (después del análisis) ejecutar nuevas campañas con la intención de convertirlos en compradores. Por el contrario, las herramientas de Web Analytics permiten que Adobe Campaign reenvíe indicadores y atributos de campaña a sus plataformas.

Los campos de acción de cada herramienta son los siguientes:

* Adobe Analytics:

   * marca las campañas de email iniciadas con Adobe Campaign
   * guarda el comportamiento del destinatario en el sitio visitado después de hacer clic en el email de la campaña, en forma de segmentos. Los segmentos están relacionados con productos abandonados (vistos pero no añadidos al carro ni comprados), compras o abandonos del carro de compras.

* Adobe Campaign:

   * envía los indicadores y atributos de campaña al conector, que a su vez los reenvía a la herramienta Web Analytics
   * recupera y analiza segmentos
   * activa una campaña de remarketing

CONSULTE https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes

: globo_voz: Como usuario de Cloud Services administrados, [póngase en contacto con Adobe](../start/support.md#support) para integrar Adobe Analytics Data Connector con Campaign.

