---
title: Migración de los operadores de Campaign a Adobe Identity Management System (IMS)
description: Obtenga información sobre cómo migrar operadores de Campaign a Adobe Identity Management System (IMS)
hide: true
hidefromtoc: true
source-git-commit: a141ba08b9c40fb89cfdf63c3078082d32afd861
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 2%

---

# Migración de los operadores de Campaign a Adobe Identity Management System (IMS) {#migrate-users-to-ims}

A partir de la versión 8.6 de Campaign, se está mejorando el proceso de autenticación en la versión 8 de Campaign. Todos los operadores utilizarán [Adobe Identity Management System (IMS)](https://helpx.adobe.com/es/enterprise/using/identity.html){target="_blank"} solo para conectarse a Campaign. Ya no se admitirá la conexión con usuario/contraseña. Adobe recomienda realizar esta migración en Campaign v8.5.2 para poder migrar sin problemas a Campaign v8.6.

Este artículo detalla los pasos necesarios para migrar un operador técnico a una cuenta técnica en la consola de Adobe Developer.

## ¿Qué ha cambiado?{#move-to-ims-changes}

Todos los usuarios normales de Campaign ya deben conectarse a la consola del cliente de Adobe Campaign con su Adobe ID, a través del Sistema Identity Management de Adobe (IMS). Sin embargo, con algunas configuraciones anteriores, las conexiones de usuario y contraseña seguían estando disponibles. Esto ya no se permitirá a partir de la versión 8.6 de Campaign.

Además, como parte del esfuerzo por reforzar la seguridad y el proceso de autenticación, la aplicación del cliente de Adobe Campaign ahora llama a las API de Campaign directamente mediante el token de cuenta técnica de IMS. La migración de operadores técnicos se detalla en un artículo específico, disponible en [esta página](ims-migration.md).

Este cambio es aplicable a partir de la versión 8.5.2 de Campaign y será **obligatorio** inicio de Campaign v8.6.


## ¿Se ha visto afectado?{#migrate-ims-impacts}

Si los operadores de su organización se conectan a la consola del cliente de Campaign mediante su inicio de sesión/contraseña (también conocido como. (autenticación nativa), se ha visto afectado y debe migrar estos operadores a Adobe IMS como se detalla a continuación.

La migración a IMS es un imperativo de seguridad para que sus entornos sean seguros y estandarizados, ya que la mayoría de las demás aplicaciones DX de Adobe ya están en IMS.

## ¿Cómo realizar la migración?{#ims-migration-procedure}

### Requisitos previos{#ims-migration-prerequisites}

Antes de iniciar el proceso de migración, debe ponerse en contacto con su representante de Adobe (Transition Manager) para que los equipos técnicos de Adobe puedan migrar los grupos de operadores y los derechos asignados existentes a Adobe Identity Management System (IMS).

### Pasos clave {#ims-migration-steps}

A continuación se enumeran los pasos clave para esta migración:

1. El Adobe actualiza sus entornos a Campaign v8.5.2.
1. Después de la actualización, aún puede crear nuevos usuarios con ambos métodos, como usuario nativo o con IMS.
1. El administrador de Campaign interno debe agregar correos electrónicos únicos a todos los usuarios nativos en la consola del cliente de Campaign y confirmar en el administrador de transición de Adobe una vez que lo haya hecho. Este paso se detalla en [esta sección](#ims-migration-id).
1. Trabaje con el Adobe para asegurar una fecha para que el Adobe ejecute la migración automática de usuarios no técnicos (operadores) y perfiles de producto. Este paso requiere un intervalo de horas sin tiempo de inactividad en ninguna de las instancias.
1. El administrador de Campaign interno valida estos cambios y proporciona una firma. Después de esta migración, ya no debe crear ningún operador adicional que se autentique con este inicio de sesión y contraseña.

Ahora puede planificar la migración de usuarios técnicos a IMS según lo siguiente [esta nota técnica](ims-migration.md)y confirme con el Administrador de transición de Adobe una vez finalizado.
El Adobe marcará la migración como completada y activará los indicadores para bloquear la creación de nuevos usuarios nativos y el inicio de sesión de usuarios nativos.

## Preguntas frecuentes {#ims-migration-faq}

### ¿Cuándo se puede iniciar la migración? {#ims-migration-start}

Un requisito previo para la migración a Adobe Identity Management System (IMS) es actualizar su entorno a Campaign v8.5.2.

Puede iniciar la migración de IMS en el entorno de ensayo, una vez que se haya actualizado a Campaign v8.5.2 y, en consecuencia, planificar el entorno de producción.

### ¿Qué sucede después de la actualización de la compilación a Campaign v8.5.2? {#ims-migration-after-upgrade}

Una vez que los entornos se hayan actualizado a Campaign v8.5.2, puede realizar la migración de Adobe de Identity Management System (IMS).

La creación de nuevos usuarios nativos sigue estando permitida hasta que se complete la migración de IMS.

### ¿Cuándo se completa la migración? {#ims-migration-end}

Una vez completada la migración de usuarios finales y la migración de usuarios técnicos a Adobe Identity Management System (IMS), debe ponerse en contacto con el administrador de transición de Adobe para que el Adobe pueda marcar la migración como completada y bloquear la creación de usuarios desde la consola del cliente e iniciar sesión como usuario nativo.


### ¿Cómo se crean usuarios después de la migración? {#ims-migration-native}

Una vez completada la migración de IMS, el Adobe aplicará las restricciones que bloquearán la creación de nuevos usuarios nativos. Estas restricciones no se aplican hasta que se completa la migración de IMS.

Para nuevos clientes: no se permite la creación de nuevos usuarios nativos desde el principio.

Como administrador de Campaign, puede conceder permisos a los usuarios de su organización a través de Adobe Admin Console y la consola del cliente de Campaign. Los usuarios inician sesión en Adobe Campaign con su Adobe ID. Obtenga más información en [esta documentación](../../v8/start/gs-permissions.md).

### ¿Cómo se agregan correos electrónicos para los usuarios nativos actuales? {#ims-migration-id}

Como administrador de Campaign, debe agregar ID de correo electrónico a todos los usuarios nativos desde la consola del cliente. Para ello, siga los pasos a continuación:

1. Conéctese a la consola de cliente de y busque **Administración > Administración de acceso > Operadores**
1. Seleccione el operador que desea actualizar en la lista de operadores.
1. Introduzca el correo electrónico del operador en la **Puntos de contacto** del formulario del operador.
1. Guarde los cambios.


### ¿Cómo iniciar sesión en Campaign a través de IMS? {#ims-migration-log}

Obtenga información sobre cómo conectarse a Campaign con su Adobe ID en [esta sección](../../v8/start/connect.md).

### ¿Habrá un tiempo de inactividad durante esta migración? {#ims-migration-downtime}

Para finalizar la migración (migrar usuarios y perfiles de producto), el Adobe requiere un intervalo de una hora sin tiempo de inactividad en ninguna de las instancias (flujos de trabajo, etc.).

Durante este periodo, todos los usuarios de Campaign deben cerrar la sesión y volver a iniciarla con su Adobe ID una vez finalizada la migración a IMS.


### ¿Qué les sucede a los usuarios que iniciaron sesión durante la migración de usuarios de IMS? {#ims-migration-log-off}

El Adobe recomienda encarecidamente que se cierre la sesión de todos los usuarios durante la ventana de migración.

### Los usuarios de mi organización ya están utilizando IMS, ¿aún necesito realizar la migración de IMS?

Existen dos aspectos en esta migración: migración de usuarios no técnicos &quot;humanos&quot; y migración de usuarios técnicos (utilizados en las API de su código personalizado).

Si todos los usuarios (operadores de Campaign) están en IMS, no es necesario que realice esta migración. Sin embargo, aún debe migrar a los usuarios técnicos que pueda haber utilizado en el código personalizado. Obtenga más información en [esta página](ims-migration.md).