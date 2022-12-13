---
product: campaign
title: 'Nota técnica: Actualizaciones del sistema de Adobe Campaign'
description: Actualización del sistema de Adobe Campaign
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: 3535e1e4fcd326412b6378253e5dde1249bce1f2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Actualizaciones del entorno de Adobe Campaign 2023 {#ac-system-upgrade}

La infraestructura de Campaign depende de sistemas de terceros que deben actualizarse regularmente con las versiones y correcciones más recientes. Estas actualizaciones son obligatorias para garantizar la continuidad del servicio y los entornos seguros de Campaign frente a riesgos de seguridad. Además, se requiere una actualización de Campaign para garantizar la compatibilidad con los cambios del sistema de terceros.

Como **Cliente de Cloud Services administrados**, Adobe le informa de estas actualizaciones cuando las necesita. Los entornos deberán actualizarse de acuerdo con las recomendaciones para garantizar el cumplimiento.

Por razones de seguridad, el Adobe debe [instale la última versión de Campaign](#ac-upgrade)y, a continuación, actualice su [sistema operativo](#os-upgrade) y/o [Sistema de administración de bases de datos de relación (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>En caso de que tenga preguntas acerca de estos cambios, póngase en contacto con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Actualización de la versión de Campaign {#ac-upgrade}

**¿Se ha visto afectado?**

Si se ve afectado por el [actualización del sistema operativo](#os-upgrade) y/o [actualización del sistema de bases de datos](#pg-upgrade) detallado a continuación, Adobe debe actualizar los entornos de Campaign a [la última versión 8.4.3](../../v8/start/release-notes.md), que es compatible con estos sistemas.

**¿Cómo realizar la actualización?**

Como cliente de Cloud Services administrados, el Adobe se pondrá en contacto con usted y actualizará su versión de Campaign.

## Actualización del sistema operativo {#os-upgrade}

**¿Se ha visto afectado?**

Si está ejecutando Campaign en un sistema operativo Debian, para beneficiarse de las últimas actualizaciones de seguridad de Debian, Adobe debe trasladar su infraestructura de Campaign a **Debian 11**. Tenga en cuenta que el soporte de seguridad para Debian 9 estará disponible hasta el 30 de junio de 2023.

**¿Cómo realizar la actualización?**

Como cliente de Cloud Services administrados, el Adobe se pondrá en contacto con usted y actualizará su entorno.

## Actualización del sistema de bases de datos {#pg-upgrade}

**¿Se ha visto afectado?**

Si el sistema de base de datos para Campaign es PostgreSQL, para beneficiarse de las últimas innovaciones y actualizaciones de seguridad de PostgreSQL, el Adobe debe actualizarse a **PostgreSQL 14**. Tenga en cuenta que PostgreSQL 11 llegará al fin de su vida útil el 9 de noviembre de 2023.

**¿Cómo realizar la actualización?**

* Como cliente de Cloud Services administrados, Adobe se pondrá en contacto con usted y actualizará su sistema de base de datos de PostgreSQL 11 a PostgreSQL 14.
