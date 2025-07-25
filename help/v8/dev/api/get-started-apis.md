---
title: Introducción a las API de REST de Campaign
description: Cree integraciones y construya su propio ecosistema interconectando Campaign con un panel tecnológico.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: c74669a0ccdabe735eb905b7e8c1634140a7ea0b
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 47%

---

# Introducción a las API de REST de Campaign {#get-started-apis}

>[!AVAILABILITY]
>
>Esta capacidad solo está disponible bajo demanda, para todos los entornos de FDA de Campaign. Está **no** disponible para implementaciones de FDAC de Campaign. Para obtener acceso, póngase en contacto con su representante de Adobe.

>[!CAUTION]
>
>Antes de realizar llamadas API, compruebe las limitaciones de escala correspondientes a su contrato de licencia. Para obtener más información, consulte [esta página](https://helpx.adobe.com/es/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

Las API de REST de Campaign están destinadas a permitirle **crear integraciones** para Adobe Campaign y **construir su propio ecosistema** al interconectar Adobe Campaign con el panel de tecnologías que utiliza.

Con las API de REST de Adobe Campaign, puede acceder a las siguientes funcionalidades:

<table><tr>
 <td valign="top"><a href="retrieving-profiles.md"><img width="60px" alt="condiciones" src="assets/icon_profile.svg"/></a><p><a href="retrieving-profiles.md">Perfiles</a></p></td>
<td valign="top"><a href="creating-a-service.md"><img width="60px" alt="condiciones" src="assets/icon_services.svg"/></a><p><a href="creating-a-service.md">Servicios y suscripciones</a></p></td>
<td valign="top"><a href="interacting-with-custom-resources.md"><img width="60px" alt="condiciones" src="assets/icon_customresources.svg"/></a><p><a href="interacting-with-custom-resources.md">Recursos personalizados</a></p></td>
<td valign="top"><a href="controlling-a-workflow.md"><img width="60px" alt="condiciones" src="assets/icon_workflows.svg"/></a><p><a href="controlling-a-workflow.md">Flujos de trabajo</a></p></td>
<td valign="top"><a href="managing-transactional-messages.md"><img width="60px" alt="condiciones" src="assets/icon_transactionalmessage.svg"/></a><p><a href="managing-transactional-messages.md">Mensajes transaccionales</a></p></td>
</tr></table>

Para utilizar las API de REST de Campaign, necesita una cuenta de Adobe I/O. Este es un primer paso obligatorio para avanzar y descubrir las características de la API.
Para obtener más información, consulte [esta sección](setting-up-api-access.md).

Las API que proporcionamos utilizan **conceptos estándar** con una interfaz REST y cargas JSON.

En esta documentación se describen detalladamente todos los extremos con las nociones generales que debe conocer para manipular la API, la referencia completa de la API, los ejemplos de código y las guías de inicio rápido. Todos los ejemplos funcionan con Postman, pero no dude en usar su cliente REST favorito.

Si algo falta o le parece incorrecto, pregunte a la [comunidad](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community?profile.language=es).
