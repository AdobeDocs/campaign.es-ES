---
product: Adobe Campaign
title: Prácticas recomendadas de seguridad de Campaign
description: Introducción a las prácticas recomendadas de seguridad de Campaign
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 20%

---

# Prácticas recomendadas de seguridad de Campaign {#ac-security}

En el Adobe, nos tomamos muy en serio la seguridad de su experiencia digital. Las prácticas de seguridad están profundamente arraigadas en nuestros procesos y herramientas internos de desarrollo de software y operaciones, y nuestros equipos interfuncionales las siguen rigurosamente para prevenir, detectar y responder a incidentes de manera expedita.

Además, nuestro trabajo colaborativo con socios, investigadores destacados, instituciones de investigación en seguridad y otras organizaciones del sector nos ayuda a estar al día con las últimas amenazas y vulnerabilidades, y regularmente incorporamos técnicas de seguridad avanzadas en los productos y servicios que ofrecemos.

## Privacidad

La configuración y el endurecimiento de la privacidad son elementos clave de la optimización de la seguridad. Estas son algunas prácticas recomendadas a seguir con respecto a la privacidad:

* Protect su información personal del cliente (PI) utilizando HTTPS en lugar de HTTP
* Utilice la [restricción de vista de IP](../dev/restrict-pi-view.md) para proteger la privacidad e impedir que se utilicen incorrectamente los datos
* Asegúrese de que las contraseñas cifradas estén restringidas
* Proteja las páginas que puedan contener información personal, como páginas espejo, aplicaciones web, etc.

[!DNL :speech_balloon:] Como usuario de Cloud Services administrados, Adobe trabajará con usted para implementar estas configuraciones en su entorno.

## Personalización

Al añadir enlaces personalizados al contenido, evite siempre cualquier personalización en la parte del nombre de host de la dirección URL para evitar posibles lagunas de seguridad. Los siguientes ejemplos nunca deben utilizarse en todos los atributos de URL &lt;`a href="">` o `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restricción de datos

Debe asegurarse de que los usuarios autenticados con privilegios bajos no puedan acceder a las contraseñas cifradas. Para ello, hay dos maneras principales: restringir el acceso solo a campos de contraseña o a toda la entidad.

Esta restricción permite eliminar los campos de contraseñas, pero deja la cuenta externa accesible desde la interfaz para todos los usuarios. Obtenga más información en [esta página](../dev/restrict-pi-view.md).

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Cree un nuevo **[!UICONTROL Extension of a schema]**.

1. Seleccione **[!UICONTROL External Account]** (extAccount).

1. En la última pantalla, puede editar el nuevo srcSchema para restringir el acceso a todos los campos de contraseña:

   Puede reemplazar el elemento principal (`<element name="extAccount" ... >`) por:

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

La gestión del acceso es una parte importante del refuerzo de la seguridad. Estas son algunas de las prácticas recomendadas principales:

* Crear suficientes grupos de seguridad
* Compruebe que cada operador tenga los derechos de acceso adecuados
* Evite utilizar el operador de administrador y evite tener demasiados operadores en el grupo de administración

[!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator){target=&quot;_blank&quot;}

## Directrices de codificación

Cuando desarrolle en Adobe Campaign (flujos de trabajo, JavaScript, JSSP, etc.), siga siempre estas directrices:

* **Secuencias de comandos**: Intente evitar las declaraciones SQL, utilice funciones parametrizadas en lugar de concatenaciones de cadenas, evite la inyección de SQL al añadir funciones SQL para usar en la lista de permitidos.

* **Proteja el modelo** de datos: usar derechos asignados para limitar las acciones de operadores, agregar filtros de sistema (sysFilter)

* **Añadir captchas en aplicaciones** web: agregue captchas en las páginas de aterrizaje públicas y páginas de suscripción.

[!DNL :arrow_upper_right:] Obtenga más información en la documentación de  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target=&quot;_blank&quot;}
