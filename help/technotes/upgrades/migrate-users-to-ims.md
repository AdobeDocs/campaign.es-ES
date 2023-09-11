---
title: Migración de los operadores de Campaign a Adobe Identity Management System (IMS)
description: Obtenga información sobre cómo migrar operadores de Campaign a Adobe Identity Management System (IMS)
hide: true
hidefromtoc: true
source-git-commit: 53412ab167721c8a8f9d84e07112b0f410d4785d
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 4%

---

# Migración de los operadores de Campaign a Adobe Identity Management System (IMS) {#migrate-users-to-ims}

A partir de la versión 8.6 de Campaign, se está mejorando el proceso de autenticación en la versión 8 de Campaign. Todos los operadores utilizarán [Adobe Identity Management System (IMS)](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"} **solamente** para conectarse a Campaign. Ya no se permitirá conectarse con usuario/contraseña (también conocido como autenticación nativa). Adobe recomienda realizar esta migración en Campaign v8.5.2 para poder migrar sin problemas a Campaign v8.6.

Como cliente de servicios administrados de Campaign Classic v7, si está migrando a Campaign v8, este procedimiento también se le aplica.

Este artículo detalla los pasos necesarios para migrar un operador técnico a una cuenta técnica en la consola de Adobe Developer.

## ¿Qué ha cambiado?{#move-to-ims-changes}

Con Campaign v8, todos los usuarios normales ya deben conectarse a la consola del cliente de Adobe Campaign con su Adobe ID, a través del Sistema Identity Management de Adobe (IMS). Sin embargo, con algunas configuraciones anteriores, las conexiones de usuario y contraseña seguían estando disponibles. **Esto ya no se permitirá a partir de la versión 8.6 de Campaign.**

Además, como parte del esfuerzo por reforzar la seguridad y el proceso de autenticación, la aplicación cliente de Adobe Campaign ahora llama a las API de Campaign directamente mediante el token de cuenta técnica de IMS. La migración para operadores técnicos se detalla en un artículo dedicado, disponible en [esta página](ims-migration.md).

Este cambio es aplicable a partir de la versión 8.5.2 de Campaign y será **obligatorio** inicio de Campaign v8.6.

## ¿Se ha visto afectado?{#migrate-ims-impacts}

Si los operadores de su organización se conectan a la consola del cliente de Campaign mediante su inicio de sesión/contraseña (también conocido como. (autenticación nativa), se ha visto afectado y debe migrar estos operadores a Adobe IMS como se detalla a continuación.

Migración a [Adobe Identity Management System (IMS)](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"} Es un imperativo de seguridad hacer que sus entornos sean seguros y estandarizados, ya que la mayoría de las otras soluciones y aplicaciones de Adobe Experience Cloud ya están en IMS.

## ¿Cómo realizar la migración?{#ims-migration-procedure}

### Requisitos previos{#ims-migration-prerequisites}

Antes de iniciar el proceso de migración, debe ponerse en contacto con su representante de Adobe (Transition Manager) para que los equipos técnicos de Adobe puedan migrar los grupos de operadores y los derechos asignados existentes a Adobe Identity Management System (IMS).

### Pasos clave {#ims-migration-steps}

A continuación se enumeran los pasos clave para esta migración:

1. El Adobe actualiza sus entornos a Campaign v8.5.2.
1. Después de la actualización, aún puede crear nuevos usuarios con ambos métodos, como usuario nativo o con IMS.
1. El administrador de Campaign interno debe agregar correos electrónicos únicos a todos los usuarios nativos en la consola del cliente de Campaign y confirmar en el administrador de transición de Adobe una vez que lo haya hecho. Este paso se detalla en [esta sección](#ims-migration-id).
1. Trabaje con el Adobe de para asegurar una fecha de Adobe para ejecutar la migración automatizada para los usuarios no técnicos (operadores) y los perfiles de producto. Este paso requiere un intervalo de horas sin tiempo de inactividad en ninguna de las instancias.
1. El administrador de Campaign interno valida estos cambios y proporciona una firma. Después de esta migración, ya no debe crear ningún operador adicional que se autentique con este inicio de sesión y contraseña.

Ahora puede migrar sus operadores técnicos a la consola de Adobe Developer como se detalla en [esta nota técnica](ims-migration.md). Este paso es obligatorio si utiliza las API de Campaign.

Una vez completada esta migración, confirme en el Administrador de transición de Adobe: Adobe marca la migración como completada y bloquea la creación de nuevos usuarios nativos y el inicio de sesión de usuarios nativos. A continuación, su entorno está protegido y estandarizado.

## Preguntas frecuentes {#ims-migration-faq}

### ¿Cuándo puedo iniciar la migración? {#ims-migration-start}

Un requisito previo para la migración a [Adobe Identity Management System (IMS)](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"} es actualizar su entorno a Campaign v8.5.2.

Puede iniciar la migración de IMS en el entorno de ensayo, una vez que se haya actualizado a Campaign v8.5.2 y, en consecuencia, planificar el entorno de producción.

### ¿Qué sucede después de la actualización de la compilación a Campaign v8.5.2? {#ims-migration-after-upgrade}

Una vez que los entornos se hayan actualizado a Campaign v8.5.2, puede iniciar la transición a [Adobe Identity Management System (IMS)](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"}.

La creación de nuevos usuarios nativos sigue estando permitida hasta que se complete la migración de IMS.

### ¿Cuándo se completa la migración? {#ims-migration-end}

Una vez completada la migración de usuarios finales y la migración de usuarios técnicos a Adobe Identity Management System (IMS), debe ponerse en contacto con el administrador de transición de Adobe para que el Adobe pueda marcar la migración como completada, bloquear la creación de usuarios desde la consola del cliente y deshabilitar el inicio de sesión de usuarios nativos.


### ¿Cómo se crean usuarios después de la migración? {#ims-migration-native}

Una vez completada la migración de IMS, el Adobe aplicará las restricciones que bloquearán la creación de nuevos usuarios nativos. Estas restricciones no se aplican hasta que se completa la migración de IMS.

Para nuevos clientes: no se permite la creación de nuevos usuarios nativos desde el principio.

Como administrador de Campaign, puede conceder permisos a los usuarios de su organización a través de Adobe Admin Console y la consola del cliente de Campaign. Los usuarios inician sesión en Adobe Campaign con su Adobe ID. Obtenga más información en [esta documentación](../../v8/start/gs-permissions.md).

### ¿Cómo se agregan correos electrónicos para los usuarios nativos actuales? {#ims-migration-id}

Como administrador de Campaign, debe agregar ID de correo electrónico a todos los usuarios nativos desde la consola del cliente. Para ello, siga los pasos a continuación:

1. Conéctese a la consola de cliente de y busque **Administración > Administración de acceso > Operadores**.
1. Seleccione el operador que desea actualizar en la lista de operadores.
1. Introduzca el correo electrónico del operador en la **Puntos de contacto** del formulario del operador.
1. Guarde los cambios.

También puede importar un archivo CSV para actualizar todos los perfiles de operadores con su correo electrónico.


### ¿Cómo iniciar sesión en Campaign a través de IMS? {#ims-migration-log}

Obtenga información sobre cómo conectarse a Campaign con su Adobe ID en [esta sección](../../v8/start/connect.md).

### ¿Habrá un tiempo de inactividad durante esta migración? {#ims-migration-downtime}

Para finalizar la migración (migrar usuarios y perfiles de producto), el Adobe requiere un intervalo de una hora sin tiempo de inactividad en ninguna de las instancias (flujos de trabajo, etc.).

Durante este periodo, todos los usuarios de Campaign deben cerrar la sesión y volver a iniciarla con su Adobe ID una vez finalizada la migración a IMS.

### ¿Qué les sucede a los usuarios que iniciaron sesión durante la migración de usuarios de IMS? {#ims-migration-log-off}

El Adobe recomienda encarecidamente que se cierre la sesión de todos los usuarios durante la ventana de migración.

### Los usuarios de mi organización ya están utilizando IMS, ¿aún necesito realizar la migración de IMS?{#ims-migration-needed}

Esta migración tiene dos aspectos: migración de usuarios finales y migración de usuarios técnicos (utilizados en las API de su código personalizado).

Si todos los usuarios (operadores de Campaign) están en IMS, no es necesario que realice esta migración. Sin embargo, aún debe migrar a los usuarios técnicos que pueda haber utilizado en el código personalizado. Obtenga más información en [esta página](ims-migration.md).

Una vez completada esta migración, debe ponerse en contacto con el administrador de transición de Adobe para que Adobe finalice la migración.

## Vínculos útiles {#ims-useful-links}

* [Migración de usuarios técnicos a la consola de Adobe Developer](ims-migration.md)
* [Cómo conectarse a Adobe Campaign v8](../../v8/start/connect.md)
* [Acceso y permisos en Adobe Campaign v8](../../v8/start/gs-permissions.md)
* [Notas de la versión de Adobe Campaign v8](../../v8/start/release-notes.md)
* [¿Qué es Adobe Identity Management System (IMS)?](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"}

