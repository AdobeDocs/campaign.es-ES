---
title: 'Seguimiento de vínculos personalizados '
description: Obtenga información sobre cómo rastrear vínculos personalizados en correos electrónicos
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 50%

---

# Seguimiento de vínculos personalizados  {#tracking-personalized-links}

Los vínculos del contenido del correo electrónico que contienen personalización necesitan rastrearse con una sintaxis específica.

El uso de JavaScript en el contenido del correo electrónico (HTML o texto) le permite generar y enviar contenido dinámico a los destinatarios, con dos limitaciones:

* La secuencia de comandos no puede acceder directamente a la base de datos (la función SQL y las funciones API no están disponibles),
* Adobe Campaign debe poder detectar direcciones URL para poder rastrear los vínculos.

## Instrucciones de preprocesamiento {#pre-processing-instructions}

Puede añadir instrucciones de preprocesamiento específicas para crear una secuencia de comandos de la dirección URL y rastrearla. Estas instrucciones deben escribirse en JavaScript y comenzar con `<%@`.

Por ejemplo:

```
<%@ value object="myObject" xpath="@myField" %>
```

Esta instrucción recupera el valor del campo `myField` del objeto `myObject`.

## Detección de URL {#url-detection}

Para la detección de seguimiento, Adobe Campaign incrusta [Tidy](https://www.html-tidy.org/) para analizar la fuente HTML y detectar el patrón. Enumera todas las direcciones URL del contenido para que se puedan rastrear individualmente. Adobe Campaign utiliza de nuevo Tidy para reemplazar la dirección URL (`http://myurl.com`) por otra URL que apunte al servidor de redirección de Adobe Campaign.

Por ejemplo, en el contenido inicial: `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>` se sustituye por un destinatario en particular con: `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

Donde:

* &quot;h&quot; significa contenido HTML (o &quot;t&quot; para contenido de texto).
* 617791 es el ID del mensaje/el ID de broadLog (hexadecimal).
* 71ffa3 es el ID de NmsDelivery (hexadecimal).
* 71ffa8 es el ID de NmsTrackingUrl (hexadecimal).
* p1, p2, etc., son todos los parámetros que se sustituirán en la dirección URL.

### Ejemplo de no detección {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>` funciona y envía el contenido real de la página web por correo electrónico a los destinatarios. Pero no se realiza el seguimiento de ninguno de los enlaces. El motivo es que el servidor de correo ejecuta `"<%=getURL(..."` por cada correo electrónico antes de enviarlo. Puede ser diferente para cada destinatario, por lo que Adobe Campaign no puede conocer las direcciones URL para el seguimiento ni asignarles un ID de etiqueta.

Cuando la página que se va a descargar es la misma para todos los destinatarios, se recomienda utilizar:

```
<%@ include url="http://mynewsletter.com" %>
```

En ese caso, la página se descarga durante el análisis, antes de la detección de seguimiento. Permite a Adobe Campaign descubrir los vínculos, asignar un ID de etiqueta y realizar un seguimiento de ellos.

### Patrón recomendado {#recommended-pattern}

Después de procesar `<%@` instrucciones, la dirección URL que se va a rastrear debe tener la siguiente sintaxis:

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>Todos los demás patrones no son compatibles con Adobe y deben evitarse para prevenir posibles brechas de seguridad.

## Parámetros de URL {#url-parameters}

Para asegurarse de que las direcciones URL personalizadas se rastrean correctamente, debe utilizar la función `escapeUrl()` o el método de codificación adecuado para los parámetros de las direcciones URL.

**Ejemplo:**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

Esto garantizará que Adobe Campaign codifique y rastree correctamente el parámetro personalizado.

## Reproducir en bucle con `<%@ foreach %>` {#foreach}

La instrucción `<%@ foreach %>` le permite iterar matrices de objetos cargados en la entrega para rastrear vínculos individuales relacionados con los objetos.

### Sintaxis

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**Parámetros:**

* **`object`**: nombre del objeto desde el que se va a realizar el inicio (normalmente un objeto de secuencia de comandos adicional, pero puede ser un envío)
* **`xpath`** (opcional): XPath de la colección en la que se va a realizar un bucle. El valor predeterminado es &quot;.&quot;, lo que significa que el objeto es la matriz con la que se debe realizar el bucle
* **`index`** (opcional): Si xpath no es &quot;.&quot; y el objeto es una matriz en sí, índice de elementos del objeto (comienza en 0)
* **`item`** (opcional): nombre de un nuevo objeto accesible con `<%@ value %>` dentro del bucle foreach. El valor predeterminado es el nombre del vínculo en el esquema

### Ejemplo

En las propiedades/personalización de envío, cargue una matriz de artículos y una tabla de relación entre destinatario y artículos.

Puede mostrar vínculos a estos artículos con seguimiento individual:

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

Esto permite a Adobe Campaign rastrear en qué artículo específico hizo clic cada destinatario, en lugar de solo rastrear que se hizo clic en un vínculo de artículo.

## Prácticas recomendadas {#best-practices}

* Utilice siempre la función `escapeUrl()` para los parámetros de URL dinámicos
* Utilice `<%@ foreach %>` cuando necesite realizar el seguimiento de elementos individuales en colecciones
* Pruebe el seguimiento antes de realizar el envío para asegurarse de que todos los vínculos funcionan correctamente
* Compruebe que los vínculos personalizados tienen el formato correcto en el contenido de envío
* Compruebe los registros de seguimiento para confirmar que los parámetros personalizados se capturan correctamente

## Temas relacionados {#related-topics}

* [Obtenga información sobre cómo configurar los vínculos rastreados](tracked-links.md)
* [Obtenga información sobre cómo configurar las opciones de seguimiento de URL](url-tracking.md)
* [Aprenda a añadir campos de personalización](personalization-fields.md)

