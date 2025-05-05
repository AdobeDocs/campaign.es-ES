---
product: campaign
title: 'Nota técnica: Guía de rotación de credenciales'
description: 'Nota técnica de Adobe Campaign: Guía de rotación de credenciales'
hide: true
hidefromtoc: true
source-git-commit: 9d280a5c9d428a2795f2c893aad2d31ae2f122b9
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 1%

---

# Nota técnica: Guía de rotación de credenciales {#ac-customer-credentials}

Como cliente, es responsable de reemplazar sus credenciales con un nuevo conjunto periódicamente para mitigar el riesgo de compromiso.

## Credenciales de opciones de Adobe Campaign {#ac-options-credentials}

Desde el Explorador de Adobe Campaign, el nodo **Administration > Platform > Options** le permite realizar modificaciones en las opciones de Adobe Campaign. Si ha guardado algunas credenciales aquí, asegúrese de girarlas.

![](assets/technote-2.png)

## Credenciales de cuenta externa {#ac-accounts-credentials}

El nodo **Administration > Platform > External Accounts** permite realizar modificaciones en las cuentas externas de Adobe Campaign.

Gire todas las credenciales guardadas en las cuentas externas.

>[!CAUTION]
>
>**No** modifique las credenciales administradas de la Adobe. No se debe modificar ninguna cuenta externa que tenga `adobe` servidor relacionado.

![](assets/technote-1.png)

Para los operadores técnicos específicos `mc*` (por ejemplo: mc1, mc2, etc.) y `Interaction*` (por ejemplo: interaction1, interaction2, etc.), se puede seguir cualquiera de los dos métodos siguientes:

1. Adobe puede cambiar las credenciales de estos operadores y compartirlas con usted. Tenga en cuenta que todas las integraciones que utilizan estos operadores dejarán de funcionar hasta que las credenciales de estos operadores se actualicen de su lado.

1. El Adobe puede crear **nuevos** operadores correspondientes a cada operador existente y compartirlos con usted. El Adobe eliminará todas las ocurrencias de operadores antiguos después de cambiar a estos nuevos operadores.


## Clave privada/certificado de Mobile Services  {#ac-key-credentials}

Para la rotación de los servicios móviles relacionados con Private keys y Certificate, consulte los vínculos a continuación.

* Para Android, consulte [esta documentación](https://experienceleague.adobe.com/es/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}.
Vaya a la sección **Crear la aplicación móvil de Android > Configurar la versión de la API**.

* Para iOS, consulte [esta documentación](https://experienceleague.adobe.com/es/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}.
Vaya a la sección **Crear aplicación móvil de iOS->Modo de autenticación**.

## Claves GPG {#ac-gpg-credentials}

Para la rotación de claves GPG, se deben seguir los siguientes pasos:

1. Descifrar los datos existentes utilizando la clave existente. [Más información](https://experienceleague.adobe.com/es/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Cree un nuevo par de claves GPG. Obtenga más información acerca de la administración de claves GPG en [esta documentación](https://experienceleague.adobe.com/es/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Reemplace el uso de claves GPG existente en todos los flujos de trabajo con la clave recién creada.

1. Elimine la clave GPG existente.