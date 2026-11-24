---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 13%
---
# parseTimeStamp

Convierte una cadena de caracteres que contiene una fecha formulada basada en una versión simplificada de la norma ISO 8601 en un objeto de tipo Fecha.

```text
parseTimeStamp (aString)
```

## Parámetros

**aString** La fecha como cadena de caracteres en formato ISO 8601.

## Valor devuelto

Objeto de tipo Date que coincide con el conjunto de fechas como parámetro.

## Observaciones

La sintaxis es la siguiente:

```javascript
              date
              time[time-zone]
            
```

o

```javascript
              dateTtime[time-zone]
            
```

La fecha debe tener el siguiente formato:

```javascript
YYYY-MM-DD
```

Por motivos de compatibilidad, también se acepta el siguiente formato:

```javascript
YYYY/MM/DD
```

La hora debe tener el siguiente formato:

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

Si se especifica, la zona horaria debe tener el formato siguiente:

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

Si no se especifica la zona horaria, la fecha se convierte a la zona horaria actual (según el contexto). Ejemplos:

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

Si el formato de fecha no es válido, se genera una excepción.

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
