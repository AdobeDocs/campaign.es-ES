---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%
---
# execCommand

> Advertencia: Esta función está disponible para un entorno local.

Ejecuta un comando y captura el código de error y la salida estándar.

```text
execCommand (command [, bNoThrow ])
```

## Parámetros

**comando**: comando que se ejecutará con sus parámetros.

**bNoThrow** true para obtener el resultado y el código de error aunque el comando no devuelva cero (false de forma predeterminada).

## Valor devuelto

Devuelve una tabla cuyo primer elemento corresponde al código de retorno del comando (si el código de retorno es diferente de cero, hay una anomalía) y el segundo elemento es una cadena de caracteres que contiene el resultado estándar producido.

## Observaciones

Sin la opción Ninguno, se produce una excepción si el comando no se puede ejecutar o si se ejecuta con un error. Si bNoThrow es igual a true, se genera una excepción sólo si no se puede ejecutar el comando. El operador necesita derechos &quot;createProcess&quot; para utilizar esta función; de lo contrario, se genera una excepción. Según la instalación, algunos comandos pueden estar en la lista de bloqueados. Por ejemplo: ln, dd, openssl, curl, wget, python, python3, perl, ruby, sh, bash, dash, zsh, base64, nlserver, node, phantomjs, java, awk, nc, telnet, ssh, scp, ftp.

## Ejemplo

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
