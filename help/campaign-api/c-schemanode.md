---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 1%
---
# SchemaNode (Clase)

Representa el elemento de un esquema

## Métodos

| Método | Descripción |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | Devuelve una instancia de [SchemaNode](c-schemanode.md) o null si el nodo no existe y el parámetro mustExist está establecido en false. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [niños](p-schemanode-children.md) | Devuelve un objeto para el cual cada propiedad es un nodo secundario indizado por su nombre. |
| [computeString](p-schemanode-computestring.md) | Devuelve la cadena calculada por el nodo actual. |
| [dataPolicy](p-schemanode-datapolicy.md) | Devuelve una cadena de caracteres que proporciona la directiva de datos del nodo actual. |
| [descripción](p-schemanode-description.md) | Devuelve una cadena de caracteres que describe el nodo actual. |
| [defaultValue](p-schemanode-defaultvalue.md) | Devuelve una cadena de caracteres que proporciona el valor predeterminado del nodo actual. |
| [editType](p-schemanode-edittype.md) | Devuelve una cadena de caracteres que especifica el tipo de edición del nodo actual. |
| [enumeración](p-schemanode-enumeration.md) | Devuelve un objeto [Enumeration](c-enumeration.md) que es la enumeración vinculada al nodo actual o null si no hay enumeración. |
| [enumerationImage](p-schemanode-enumerationimage.md) | Devuelve el nombre de la imagen del nodo actual en forma de cadena de caracteres. |
| [folderModel](p-schemanode-foldermodel.md) | Solo en el nodo raíz, devuelve una cadena que contiene las plantillas de carpeta. En los demás nodos, devuelve undefined. |
| [imagen](p-schemanode-image.md) | Devuelve el nombre de la imagen en forma de cadena de caracteres. |
| [integridad](p-schemanode-integrity.md) | Devuelve el tipo de integridad del vínculo. |
| [claves](p-schemanode-keys.md) | Devuelve una tabla con definiciones de las claves [SchemaKey](c-schemakey.md) del nodo actual. |
| [hasEnumeration](p-schemanode-hasenumeration.md) | Devuelve un valor booleano que indica si el valor del nodo actual está vinculado a una enumeración. |
| [childrenCount](p-schemanode-childrencount.md) | Devuelve un número que especifica el número de nodos secundarios. |
| [hasSQLTable](p-schemanode-hassqltable.md) | Devuelve un valor booleano que indica si el nodo actual está vinculado a una tabla SQL. |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | Devuelve un valor booleano que indica si el valor del nodo actual está vinculado a una enumeración de usuarios. |
| [ayuda](p-schemanode-help.md) | Devuelve la cadena de caracteres de ayuda. |
| [esquema](p-schemanode-schema.md) | Devuelve la instancia del objeto principal [Schema](c-schema.md) de este nodo. |
| [isAdvanced](p-schemanode-isadvanced.md) | Devuelve un valor booleano que indica si el nodo actual está avanzado o no. |
| [isAnyType](p-schemanode-isanytype.md) | Devuelve un valor booleano que indica si el nodo actual es normal. |
| [isAttribute](p-schemanode-isattribute.md) | Devuelve un valor booleano que indica si el nodo actual es un atributo. |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | Devuelve un valor booleano que indica si el valor del nodo actual se incrementa automáticamente. |
| [isAutoPK](p-schemanode-isautopk.md) | Devuelve un valor booleano que indica si el nodo actual es una clave principal. |
| [isBlob](p-schemanode-isblob.md) | Devuelve un valor booleano que indica si el nodo actual es un BLOB. |
| [isCalculated](p-schemanode-iscalculated.md) | Devuelve un valor booleano que indica si el valor del nodo actual es el resultado de un cálculo. |
| [isCDATA](p-schemanode-iscdata.md) | Devuelve un valor booleano que indica si el nodo actual está asignado desde un XML de tipo CDATA. |
| [isCollection](p-schemanode-iscollection.md) | Devuelve un valor booleano que indica si el nodo actual es una colección de subelementos o atributos. |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | Devuelve un valor booleano. Si el valor añadido es vario, durante la anulación de duplicación de registros, el valor predeterminado (definido en defaultValue) se vuelve a aplicar automáticamente durante la grabación. |
| [isElementOnly](p-schemanode-iselementonly.md) | Devuelve un valor booleano que indica si el nodo actual es una subdivisión lógica del esquema. |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | True si el nodo es un vínculo y si la unión es externa. |
| [isFeature](p-schemanode-isfeature.md) | Devuelve un valor booleano que indica si el nodo es una característica. |
| [isLink](p-schemanode-islink.md) | Devuelve un valor booleano que indica si el nodo es un vínculo. |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | Devuelve un valor booleano que indica si el nodo es una asignación XML. |
| [isMemo](p-schemanode-ismemo.md) | Devuelve un valor booleano que indica si el nodo actual está asignado por un Memo. |
| [isMemoData](p-schemanode-ismemodata.md) | Devuelve un valor booleano que indica si el nodo actual está asignado por MemoData. |
| [isNotNull](p-schemanode-isnotnull.md) | Devuelve un valor booleano que indica si el nodo actual puede tener en cuenta el valor nulo o no. |
| [isRequired](p-schemanode-isrequired.md) | Devuelve un valor booleano que indica si el valor del nodo actual es obligatorio o no. |
| [isRoot](p-schemanode-isroot.md) | Devuelve un valor booleano que indica si el nodo es la raíz del esquema. |
| [isSQL](p-schemanode-issql.md) | Devuelve un valor booleano que indica si el nodo actual está asignado en SQL. |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | Devuelve un valor booleano que indica si la tabla es temporal. La tabla no se creará durante la creación de la base de datos. |
| [isUnbound](p-schemanode-isunbound.md) | Devuelve un valor booleano que indica si el nodo actual tiene un número ilimitado de elementos secundarios del mismo tipo. |
| [isUser](p-schemanode-isuser.md) | Devuelve un valor booleano que indica si el nodo es de tipo usuario o no. |
| [joinParts](p-schemanode-joinparts.md) | Devuelve una tabla de instancias de SchemaNode para las que cada elemento representa una condición de la combinación. |
| [etiqueta](p-schemanode-label.md) | Devuelve una cadena de caracteres que es la descripción del nodo actual. |
| [nombre](p-schemanode-name.md) | Devuelve una cadena de caracteres que es el nombre del nodo actual. |
| [rutaDeAccesoDeNodo](p-schemanode-nodepath.md) | Devuelve una cadena de caracteres que es la ruta absoluta del nodo actual. |
| [principal](p-schemanode-parent.md) | Devuelve un objeto [SchemaNode](c-schemanode.md) que es el objeto principal o nulo si no lo hay. |
| [PKSequence](p-schemanode-pksequence.md) | Devuelve una cadena de caracteres que proporciona el nombre de la secuencia que se va a utilizar para la clave principal. |
| [packageStatus](p-schemanode-packagestatus.md) | Devuelve un número que indica el estado del paquete. |
| [reverseLink](p-schemanode-reverselink.md) | Si el elemento es un vínculo, devuelve un objeto [SchemaNode](c-schemanode.md) que representa un vínculo inverso (a través del esquema de destino). Si no es así, la propiedad no está definida. |
| [SQLName](p-schemanode-sqlname.md) | El nombre SQL del campo. La propiedad es una cadena vacía si el objeto no es un campo de tipo SQL. |
| [SQLTable](p-schemanode-sqltable.md) | El nombre SQL de la tabla. La propiedad es una cadena vacía si el objeto no es el elemento principal o si la asignación de esquema no es del tipo SQL. |
| [tamaño](p-schemanode-size.md) | El tamaño del tipo de cadena de caracteres. |
| [tableDefinition](p-schemanode-tabledefinition.md) | Instancia de [SchemaNode](c-schemanode.md) que es la descripción de la tabla que contiene el nodo actual, nulo si no hay ninguno. |
| [destino](p-schemanode-target.md) | El elemento principal del esquema del destinatario del vínculo. Si el objeto no es un vínculo, la propiedad no está definida. |
| [tipo](p-schemanode-type.md) | Devuelve una cadena de caracteres que proporciona el tipo de valor del nodo actual. |
| [userEnumeration](p-schemanode-userenumeration.md) | Devuelve una cadena de caracteres que es el nombre de la enumeración de usuarios que utiliza el nodo actual. |

## Funciones

**Disponible en:**

* Administración de contenido
* Propiedades de envío
* Regla de tipología
* JSSP
* Método SOAP
* WebApp
* Flujo de trabajo
