---
product: campaign
title: 'Nota técnica: Actualizaciones del sistema de Adobe Campaign'
description: Actualización del sistema de Adobe Campaign
hide: true
hidefromtoc: true
exl-id: cc64cce1-2473-4136-aadc-8b13e89ef7f9
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Actualizaciones del entorno de Adobe Campaign 2023 {#ac-system-upgrade}

La infraestructura de Campaign se basa en sistemas de terceros que deben actualizarse regularmente con las últimas versiones y correcciones. Estas actualizaciones son obligatorias para garantizar la continuidad del servicio y proteger los entornos de Campaign de los riesgos de seguridad. Además, se requiere una actualización de Campaign para garantizar la compatibilidad con los cambios del sistema de terceros.

Como cliente de **Managed Cloud Services**, Adobe le informa sobre estas actualizaciones cuando son necesarias. Sus entornos deberán actualizarse de acuerdo con las recomendaciones para garantizar el cumplimiento.

Por razones de seguridad, Adobe debe [instalar la última compilación de Campaign](#ac-upgrade) y luego actualizar su [sistema operativo](#os-upgrade) y/o su [Sistema de administración de bases de datos de relación (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>En caso de que tenga preguntas acerca de estos cambios, póngase en contacto con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

## Actualización de compilación de Campaign {#ac-upgrade}

**¿Se ha visto afectado?**

Si se ve afectado por la [actualización del sistema operativo](#os-upgrade) y/o la [actualización del sistema de base de datos](#pg-upgrade) que se detalla a continuación, Adobe debe actualizar los entornos de Campaign a [la última versión de la versión 8.4.3](../../v8/start/release-notes.md), que es compatible con estos sistemas.

**¿Cómo realizar la actualización?**

Como cliente de Cloud Services administrados, Adobe se pondrá en contacto con usted y actualizará la versión de Campaign.

## Actualización del sistema operativo {#os-upgrade}

**¿Se ha visto afectado?**

Si está ejecutando Campaign en un sistema operativo Debian, para beneficiarse de las últimas actualizaciones de seguridad de Debian, Adobe debe mover su infraestructura de Campaign a **Debian 11**. Tenga en cuenta que la compatibilidad con la seguridad de Debian 9 estará disponible hasta el 30 de junio de 2023.

**¿Cómo realizar la actualización?**

Como cliente de Cloud Services administrados, Adobe se pondrá en contacto con usted y actualizará su entorno.

## Actualización del sistema de base de datos {#pg-upgrade}

**¿Se ha visto afectado?**

Si el sistema de base de datos de Campaign es PostgreSQL, para beneficiarse de las últimas innovaciones y actualizaciones de seguridad de PostgreSQL, Adobe debe actualizar a **PostgreSQL 14**. Tenga en cuenta que PostgreSQL 11 llegará al fin de su vida útil el 9 de noviembre de 2023.

**¿Cómo realizar la actualización?**

Como cliente de Cloud Services administrados, Adobe se pondrá en contacto con usted y actualizará su sistema de base de datos de PostgreSQL 11 a PostgreSQL 14.
