---
title: Prácticas recomendadas de seguridad de Campaign
description: Introducción a las prácticas recomendadas de seguridad de Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 21%

---

# Prácticas recomendadas de seguridad de Campaign {#ac-security}

En Adobe, nos tomamos muy en serio la seguridad de su experiencia digital. Las prácticas de seguridad están profundamente arraigadas en nuestros procesos y herramientas de desarrollo interno de software y operaciones, y son seguidas rigurosamente por nuestros equipos interfuncionales para prevenir, detectar y responder a los incidentes de manera oportuna.

Además, nuestro trabajo colaborativo con socios, investigadores líderes, instituciones de investigación de seguridad y otras organizaciones del sector nos ayuda a mantenernos al día con las últimas amenazas y vulnerabilidades e incorporamos regularmente técnicas de seguridad avanzadas en los productos y servicios que ofrecemos.

## Privacidad

La configuración y protección de la privacidad es un elemento clave de la optimización de la seguridad. Estas son algunas prácticas recomendadas seguir con respecto a la privacidad:

* Protect proporciona su información personal (PI) al cliente utilizando HTTPS en lugar de HTTP
* Use [restricción de vista PI](../dev/restrict-pi-view.md) para proteger la privacidad y evitar que se usen los datos de manera indebida
* Asegúrese de que las contraseñas cifradas estén restringidas
* Proteja las páginas que puedan contener información personal, como páginas espejo, aplicaciones web, etc.


>[!NOTE]
>
>Como usuario de Cloud Service administrados, Adobe trabajará con usted para implementar estas configuraciones en su entorno.


## Gestión de acceso

La administración del acceso es una parte importante del refuerzo de la seguridad. Estas son algunas de las prácticas recomendadas principales:

* Crear suficientes grupos de seguridad
* Compruebe que cada operador tiene los derechos de acceso adecuados

Obtenga más información sobre los permisos en [esta sección](../start/gs-permissions.md)

## Directrices de codificación

Al desarrollar en Adobe Campaign (flujos de trabajo, Javascript, JSSP, etc.), siga siempre estas directrices:

* **Secuencias de comandos**: Intente evitar las declaraciones SQL, utilice funciones parametrizadas en lugar de concatenaciones de cadenas, evite la inyección de SQL al añadir funciones SQL para usar en la lista de permitidos.

* **Proteger el modelo de datos**: use derechos asignados para limitar las acciones de los operadores y agregue filtros de sistema (sysFilter)

* **Agregar captchas en aplicaciones web**: agregue captchas en las páginas de aterrizaje públicas y en las páginas de suscripción.

Obtenga más información en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=es#installing-campaign-classic){target="_blank"}.


## Personalización

Al añadir enlaces personalizados al contenido, evite siempre cualquier personalización en la parte del nombre de host de la dirección URL para evitar posibles lagunas de seguridad. Los siguientes ejemplos nunca deben utilizarse en todos los atributos de URL &lt;`a href="">` o `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restricción de datos

Debe asegurarse de que los usuarios autenticados con privilegios bajos no puedan acceder a las contraseñas cifradas. Para ello, hay dos formas principales: restringir el acceso solo a campos de contraseña o a toda la entidad.

Esta restricción permite eliminar los campos con contraseñas, pero deja la cuenta externa accesible desde la interfaz para todos los usuarios. Obtenga más información en [esta página](../dev/restrict-pi-view.md).

1. Ir en **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Crear nuevo(a) **[!UICONTROL Extension of a schema]**.

1. Elija **[!UICONTROL External Account]** (extAccount).

1. En la última pantalla, puede editar el nuevo srcSchema para restringir el acceso a todos los campos de contraseña:

   Puede reemplazar el elemento principal (`<element name="extAccount" ... >`):

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   Por lo tanto, el srcSchema extendido puede tener el siguiente aspecto:

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >Puede reemplazar `$(loginId) = 0 or $(login) = 'admin'` por `hasNamedRight('admin')` para permitir que todos los usuarios con derechos de administrador vean estas contraseñas.


## Gestión de acceso

La administración del acceso es una parte importante del refuerzo de la seguridad. Estas son algunas de las prácticas recomendadas principales:

* Crear suficientes grupos de seguridad
* Compruebe que cada operador tiene los derechos de acceso adecuados

Obtenga más información acerca de los permisos en [en esta sección](../start/gs-permissions.md).

## Directrices de codificación

Al desarrollar en Adobe Campaign (flujos de trabajo, Javascript, JSSP, etc.), siga siempre estas directrices:

* **Secuencias de comandos**: Intente evitar las declaraciones SQL, utilice funciones parametrizadas en lugar de concatenaciones de cadenas, evite la inyección de SQL al añadir funciones SQL para usar en la lista de permitidos.

* **Proteger el modelo de datos**: use derechos asignados para limitar las acciones de los operadores y agregue filtros de sistema (sysFilter)

* **Agregar captchas en aplicaciones web**: agregue captchas en las páginas de aterrizaje públicas y en las páginas de suscripción.

Obtenga más información en [Documentación de Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=es#installing-campaign-classic){target="_blank"}.
