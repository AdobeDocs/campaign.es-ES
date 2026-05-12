---
title: Introducción a las API de REST de Campaign
description: Cree integraciones y construya su propio ecosistema interconectando Campaign con un panel tecnológico.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
TQID: https://experienceleague.adobe.com/RRDY-7SFGUwxHk34LLhRHaFN-0U4A9NQfNvLPXO8GM8
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 58%

---

# Introducción a las API de REST de Campaign {#get-started-apis}

Las API de REST de Campaign están destinadas a permitirle **crear integraciones** para Adobe Campaign y **construir su propio ecosistema** al interconectar Adobe Campaign con el panel de tecnologías que utiliza.

>[!AVAILABILITY]
>
>* Esta funcionalidad solo está disponible bajo demanda para todos los [entornos de FDA de Campaign](../../architecture/fda-deployment.md). Está **no** disponible para [implementaciones empresariales (FDAC)](../../architecture/enterprise-deployment.md). Para obtener acceso, póngase en contacto con su representante de Adobe.
>
>* Antes de realizar llamadas API, compruebe las limitaciones de escala correspondientes a su contrato de licencia. Para obtener más información, consulte la [Descripción del producto de Adobe Campaign v8](https://helpx.adobe.com/es/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.


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

