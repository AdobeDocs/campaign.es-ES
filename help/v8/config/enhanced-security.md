---
title: Complemento de seguridad mejorada de Campaign
description: Introducción al complemento de seguridad mejorada de Campaign
feature: Configuration
role: Developer
level: Experienced
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
source-git-commit: 3f36d7c425dd5a9a13e1de7a77371b29a462dbea
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---


# Complemento de seguridad mejorada de Campaign {#enhanced-security}

Para hacer que la conexión de red sea más segura y proporcionar una seguridad mejorada para los recursos, [!DNL Adobe Campaign] ofrece un nuevo complemento de **seguridad mejorada**.

Este complemento incluye dos características del ecosistema:

* [Integración segura de clave gestionada por el cliente (CMK)](#secure-cmk-integration)

* [Túnel de red privada virtual (VPN) segura](#secure-vpn-tunneling)

Estas funciones se detallan a continuación.

En esta página se enumeran algunas protecciones y limitaciones relacionadas con las funciones de seguridad mejoradas. Además, debe asegurarse de que todos los casos de uso de integración de CMK segura/túnel de VPN seguro funcionen.

Una vez implementadas estas funciones, Adobe supervisa:

* La disponibilidad de la instancia y continúe con las alertas si la clave no está disponible.

* Los túneles VPN y continúe con las alertas en caso de que surja algún problema.

## Integración segura de claves gestionadas por el cliente {#secure-cmk-integration}

La **integración de clave administrada por el cliente segura (CMK)** le permite cifrar datos en reposo usando su propia clave a través de su cuenta de Amazon Web Service (AWS).

Las claves administradas por el cliente son claves del Servicio de administración de claves (KMS) de su cuenta de AWS que crea, posee y administra. Tiene control total sobre estas claves KMS y las utiliza para cifrar y descifrar datos. Al responsabilizarse de la generación y administración de claves de cifrado, esta capacidad le permite tener más control sobre ellas, incluida la revocación de una clave.

>[!CAUTION]
>
>En caso de que revoque una clave, debe tener en cuenta los impactos. [Más información](#cmk-callouts)

Para habilitar la integración de CMK con Campaign, siga los pasos a continuación:

1. Conéctese a su cuenta de [Amazon Web Service (AWS)](https://aws.amazon.com/){target="_blank"}.

1. Genere una clave con rotación automática al utilizar el servicio de administración de claves de AWS (KMS). [Más información](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Aplique la política proporcionada por Adobe a su cuenta de AWS para conceder acceso a sus recursos. [Más información](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Comparta su [nombre de recurso de Amazon (clave ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} con [!DNL Adobe Campaign]. Para ello, póngase en contacto con su representante de Adobe. <!--or Adobe transition manager?-->

1. Cree y pruebe las reglas de Amazon EventBridge para permitir que Adobe supervise las claves&#x200B; [Más información](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.


### Mecanismos de protección y limitaciones {#cmk-callouts}

Las siguientes limitaciones y protecciones se aplican a la integración de CMK con Adobe Campaign v8:

* Adobe no proporciona una cuenta de [Amazon Web Service (AWS)](https://aws.amazon.com/){target="_blank"}. Debe tener su propia cuenta de AWS y configurarla para generar y compartir su clave con Adobe.

* Solo se admiten las claves [AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS). No se pueden utilizar claves generadas por el cliente fuera de KMS&#x200B;

* Se espera tiempo de inactividad durante la primera configuración. palo de golfLa duración del tiempo de inactividad depende del tamaño de la base de datos.

* Como cliente, es el propietario y mantiene la clave. Debe ponerse en contacto con Adobe en caso de cualquier cambio en la clave&#x200B;

* Puede auditar su clave mediante [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} y revocarla si es necesario&#x200B;.

* En caso de que revoque, deshabilite o elimine la clave, los recursos cifrados y la instancia dejarán de ser accesibles hasta que revierta la acción correspondiente.

  >[!CAUTION]
  >
  >Si deshabilita la clave y no revierte esta acción en un plazo de 7 días, la base de datos solo se puede recuperar de la copia de seguridad.
  >
  >Si elimina la clave y no revierte esta acción en un plazo de 30 días, todos los datos se eliminarán de forma permanente y se perderán&#x200B;

## Túnel de red privada virtual segura {#secure-vpn-tunneling}

El túnel **Red privada virtual segura (VPN)** es una VPN de sitio a sitio que proporciona acceso seguro a los datos en tránsito a través de una red privada, desde las instalaciones hasta la instancia de [!DNL Adobe Campaign].

<!--As it connects two networks together, it is a site-to-site VPN.-->

Para garantizar la alta disponibilidad (HA), utiliza dos túneles para evitar cualquier interrupción en caso de que se produzca un problema en un túnel.

Se admiten tres casos de uso:

* Acceso de datos federado (FDA) a través de VPN, para acceder a su base de datos local desde la instancia de Campaign a través de VPN

* Inicio de sesión de instancia a través de VPN desde un cliente grande

* Acceso SFTP de instancia a través de VPN

>[!CAUTION]
>
>Se admiten bases de datos locales y en la nube. [Más información](#vpn-databases)

Para garantizar el uso correcto de esta función, siga las directrices a continuación:

* Configure su VPN lateral en función de la configuración de VPN del lado de Adobe.

* Mantenga ambos túneles listos para la alta disponibilidad.

* Monitorice su túnel lateral.

* Debe ser el iniciador del túnel y alinearse para reiniciar la conexión si el túnel se cae.

* Configure un mecanismo de reintento en su extremo en caso de que se produzcan errores de conexión.

### Bases de datos y dispositivos compatibles {#vpn-databases}

Se admiten las siguientes bases de datos locales:

* MySQL
* Netezza
* Oracle
* SAP HANA
* SQL Server
* Sybase
* Teradata
* Hadoop a través de HiveSQL
* PostgreSQL

Se admiten bases de datos en la nube. Consulte la [matriz de compatibilidad](../start/compatibility-matrix.md#FederatedDataAccessFDA).

>[!NOTE]
>
>* No se admite la conectividad VPN con terceros o proveedores externos.
>
>* No se incluyen las VPN adicionales administradas por Adobe a bases de datos privadas de Cloud.
