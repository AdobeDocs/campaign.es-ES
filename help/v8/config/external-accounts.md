---
solution: Campaign
product: Adobe Campaign
title: Cuentas externas de Campaign
description: Cuentas externas de Campaign
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: 3f63fa1f599252311e2539aa35d4917c03e079b4
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 16%

---

# Configuración de las cuentas externas

Adobe Campaign viene con un conjunto de cuentas externas predefinidas. Para configurar conexiones con sistemas externos, puede crear nuevas cuentas externas.

Los procesos técnicos utilizan las cuentas externas como flujos de trabajo técnicos o flujos de trabajo de campaña. Por ejemplo, al configurar una transferencia de archivos en un flujo de trabajo o un intercambio de datos con cualquier otra aplicación (Adobe Target, Experience Manager, etc.), debe seleccionar una cuenta externa.


>[!CAUTION]
>
>La cuenta externa de enrutamiento de envío de correo electrónico interna no debe estar habilitada en Campaign v8.


:arrow_upper_right: Obtenga información sobre cómo crear y configurar cuentas externas en [Campaign Classic documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts.html)

Una cuenta externa específica administra la conexión entre la base de datos local de Campaign y la base de datos de Cloud ([!DNL Snowflake]).

: globo_voz: Como usuario de Cloud Services administrados, la cuenta externa [!DNL Snowflake] está configurada para su instancia por Adobe.
