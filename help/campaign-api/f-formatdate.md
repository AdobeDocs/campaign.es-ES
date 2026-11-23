---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 6%
---
# formatDate

Aplica formato a una fecha como cadena de caracteres.

```text
formatDate (date, format [, timeZone ])
```

## Parámetros

**fecha** La fecha que se va a convertir.

**formato** Cadena de caracteres que describe el formato que se va a utilizar. Los caracteres utilizados para dar formato a las diferentes partes de la fecha son los siguientes:

* Y - Año
* M - Mes del año (1-12)
* B - Nombre del mes
* D - Día del mes (1-31)
* A - Nombre del día
* J - Día del año (1-366)
* W - Semana del año
* H - Hora (0-23)
* I - Hora (1-12)
* N - Minutos (0-59)
* S - Segundos (0-59)
* P - AM/PM

Puede especificar un número delante de algunos de estos caracteres. Los caracteres A y B pueden ir seguidos de una l para utilizar el nombre completo en lugar de la versión abreviada o de una i para utilizar el nombre en inglés. Ejemplos:

* &quot;%4Y/%2M/%2D&quot; => 2000/01/24.
* &quot;%A %D %B %4Y&quot; => mon 24 jan 2000.
* &quot;%Al %D %Bl %4Y&quot; => lunes 24 de enero de 2000.
* &quot;%02H:%02N:%02S&quot; muestra la hora, los minutos y los segundos a dos cifras.

**timeZone**: cadena de caracteres correspondiente a la zona horaria. Los valores posibles se especifican en el esquema de enumeración xtk:common:timezone.

## Valor devuelto

Cadena de caracteres que representa la fecha en el formato solicitado.

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Envío del mensaje
* Regla de tipología
* Importación
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
