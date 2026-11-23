---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 5%
---
# Archivo (Clase)

Clase de archivo

> Advertencia:
>
> El acceso a través de las API de archivo está limitado a **var**, **sftp** y a las carpetas temporales de Adobe Campaign.

A continuación se muestra un ejemplo de cómo utilizar la clase para leer y procesar todas las líneas de un archivo en secuencia.

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## Métodos

| Método | Descripción |
| --- | --- |
| [Archivo](m-file-file.md) | Crea un nuevo objeto asociado a un archivo. |
| [cerrar](m-file-close.md) | Cierra el archivo. |
| [copiar a](m-file-copyto.md) | Copia un archivo. |
| [eliminar](m-file-dispose.md) | Libera los recursos utilizados por el objeto. |
| [vaciar](m-file-flush.md) | Fuerza la escritura en el disco |
| [lista](m-file-list.md) | Muestra el contenido de un directorio. |
| [mkdir](m-file-mkdir.md) | Crea un directorio con la ruta del objeto [File](c-file.md) actual. |
| [abrir](m-file-open.md) | Abre el archivo en modo de lectura o escritura. |
| [quitar](m-file-remove.md) | Elimina el archivo. |
| [cambiar el nombre a](m-file-renameto.md) | Cambia el nombre de un archivo. |
| [readln](m-file-readln.md) | Lee una línea del archivo de texto. |
| [rmdir](m-file-rmdir.md) | Elimina el directorio (no en cascada). |
| [writeln](m-file-writeln.md) | Escribe una línea de texto en el archivo. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [canRead](p-file-canread.md) | Devuelve true si el archivo se puede leer. |
| [canWrite](p-file-canwrite.md) | Devuelve true si el archivo se puede modificar. |
| [existe](p-file-exists.md) | Devuelve true si hay un archivo o una carpeta con este nombre. |
| [fullName](p-file-fullname.md) | Devuelve el nombre del archivo en absoluto. |
| [isDirectory](p-file-isdirectory.md) | Devuelve true si el archivo es un directorio. |
| [isFile](p-file-isfile.md) | Devuelve true si el archivo existe y es un archivo. |
| [isOpen](p-file-isopen.md) | Devuelve verdadero si el archivo está abierto. |
| [lastModified](p-file-lastmodified.md) | Devuelve la fecha de la última modificación en forma de objeto Date. |
| [nombre](p-file-name.md) | Devuelve el nombre del archivo con la extensión, pero sin la ruta. |
| [ruta](p-file-path.md) | Devuelve la ruta completa del archivo terminado por el separador. |
| [tamaño](p-file-size.md) | Devuelve el tamaño del archivo en bytes. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
