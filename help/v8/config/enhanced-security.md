---
title: Complemento de seguridad mejorada
description: Introducción al complemento de seguridad mejorada de Campaign
feature: Configuration
role: Developer
level: Experienced
hide: true
hidefromtoc: true
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: f9b064dffa0f8792e8653760cb2ac44cfdf43848
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 1%

---

# Complemento de seguridad mejorada {#enhanced-security}

Para que la conexión de red sea más segura y proporcionar una seguridad mejorada para los recursos, [!DNL Adobe Campaign] ofrece un nuevo **Seguridad mejorada** complemento de.

Este complemento incluye dos características del ecosistema:

* [Integración segura de CMK](#secure-cmk-integration)

* [Túnel VPN seguro](#secure-vpn-tunneling)

Estas funciones se detallan a continuación.

## Integración segura de CMK {#secure-cmk-integration}

El **Integración segura de clave gestionada por el cliente (CMK)** permite cifrar la instancia y los datos utilizando su propia clave a través de la cuenta de Amazon Web Service (AWS).

Las claves administradas por el cliente son claves del Servicio de administración de claves (KMS) de su cuenta de AWS que crea, posee y administra. Tiene control total sobre estas claves KMS y las utiliza para cifrar y descifrar datos. Al responsabilizarse de la generación y administración de claves de cifrado, esta capacidad le permite tener más control sobre ellas, incluida la revocación de una clave.

>[!CAUTION]
>
>En caso de que revoque una clave, debe tener en cuenta los impactos. [Más información](#cmk-callouts)

Para habilitar la integración de CMK con Campaign, siga los pasos a continuación:

1. Conéctese a su [Amazon Web Service (AWS)](https://aws.amazon.com/){target="_blank"} cuenta.

1. Genere una clave con rotación automática al utilizar el servicio de administración de claves de AWS (KMS). [Descubra cómo](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Aplique la directiva que le proporcionó el Adobe en su cuenta de AWS para conceder acceso a sus recursos. [Más información](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Comparta su [Nombre del recurso de Amazon (clave ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} con [!DNL Adobe Campaign]. Para ello, póngase en contacto con su representante de Adobe. <!--or Adobe transition manager?-->

1. Cree y pruebe las reglas de Amazon EventBridge para habilitar la supervisión de las claves por Adobe &#x200B; [Más información](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.

## Túnel VPN seguro {#secure-vpn-tunneling}

El **Túnel de red privada virtual (VPN) segura** es una VPN de sitio a sitio que proporciona acceso seguro a sus datos en tránsito a través de una red privada, desde sus instalaciones a la [!DNL Adobe Campaign] ejemplo.

<!--As it connects two networks together, it is a site-to-site VPN.-->

Para garantizar la alta disponibilidad (HA), utiliza dos túneles para evitar cualquier interrupción en caso de que se produzca un problema en un túnel.

Se admiten tres casos de uso:

* Acceso de datos federado (FDA) a través de VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* Inicio de sesión de instancia a través de VPN desde un cliente grande

* Acceso SFTP de instancia a través de VPN

>[!CAUTION]
>
>Solo son compatibles las bases de datos locales y los dispositivos VPN compatibles con AWS. [Más información](#vpn-callouts)

Para garantizar el uso correcto de esta función, siga las directrices a continuación:

* Configure su VPN lateral en función de la configuración de VPN del lado del Adobe.

* Mantenga ambos túneles listos para la alta disponibilidad.

* Monitorice su túnel lateral.

* Debe ser el iniciador del túnel y alinearse para reiniciar la conexión si el túnel se cae.

* Configure un mecanismo de reintento en su extremo en caso de que se produzcan errores de conexión.

## Mecanismos de protección {#callouts}

A continuación se enumeran algunas protecciones y limitaciones relacionadas con las funciones de seguridad mejoradas.

* Asegúrese de que todos los casos de uso de integración de CMK seguro/túnel de VPN seguro funcionen.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* El Adobe supervisará:

   * La disponibilidad de la instancia y continúe con las alertas si la clave no está disponible.

   * Los túneles VPN y continúe con las alertas en caso de que surja algún problema.

### Protecciones de integración de CMK seguras {#cmk-callouts}

* Adobe no proporciona una cuenta de AWS. Debe tener su propia cuenta de AWS y configurarla para generar y compartir su clave con Adobe.

* Solo [Servicio de administración de claves AWS](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} Se admiten las claves (KMS). No se pueden utilizar claves generadas por el cliente fuera de KMS&#x200B;

* Habrá cierto tiempo de inactividad durante la primera configuración. palo de golfLa duración del tiempo de inactividad dependerá del tamaño de la base de datos.

* Como es el propietario y mantiene la clave, debe ponerse en contacto con el Adobe en caso de que se produzca algún cambio en la clave&#x200B;

* Puede auditar la clave mediante [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} y revocarlo si es necesario&#x200B;

* En caso de que revoque, deshabilite o elimine la clave, los recursos cifrados y la instancia dejarán de ser accesibles hasta que revierta la acción correspondiente.

  >[!CAUTION]
  >
  >Si deshabilita la clave y no revierte esta acción en un plazo de 7 días, la base de datos solo se puede recuperar de la copia de seguridad.
  >
  >Si elimina la clave y no revierte esta acción en un plazo de 30 días, todos los datos se eliminarán de forma permanente y se perderán&#x200B;

### Protecciones de túnel VPN seguras {#vpn-callouts}

* Actualmente, solo se admiten bases de datos locales, como<!--Richa to check the list with PM-->:

   * MySQL
   * Netezza 
   * Oracle 
   * SAP HANA 
   * SQL Server 
   * Sybase 
   * Teradata 
   * Hadoop a través de HiveSQL

* Solo se admiten dispositivos VPN compatibles con AWS. Hay una lista de dispositivos compatibles disponibles en [esta página](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* No se admite la conectividad VPN con terceros o proveedores externos.

* No se incluyen las VPN adicionales administradas por el Adobe a bases de datos privadas de Cloud.
