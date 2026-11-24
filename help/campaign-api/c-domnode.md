---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%
---
# DOMNode (Clase)

DOMNode es la clase principal de diferentes componentes que conforman un documento.

## Métodos

| Método | Descripción |
| --- | --- |
| [insertBefore](m-domnode-insertbefore.md) | Inserte un nodo antes de una posición específica. |
| [replaceChild](m-domnode-replacechild.md) | Reemplace un nodo. |
| [removeChild](m-domnode-removechild.md) | Eliminar un nodo. |
| [appendChild](m-domnode-appendchild.md) | Inserte un nodo al final de la lista de subcarpetas. |
| [hasChildNodes](m-domnode-haschildnodes.md) | Comprueba si el nodo tiene al menos una subcarpeta. |
| [normalizar](m-domnode-normalize.md) | Normaliza el nodo: se combinan nodos de texto adyacentes y se eliminan nodos de texto vacíos. |
| [hasAttributes](m-domnode-hasattributes.md) | Comprueba si el nodo tiene al menos un atributo. |
| [isSameNode](m-domnode-issamenode.md) | Comprueba si la referencia dada representa el mismo nodo. |
| [isDefaultNamespace](m-domnode-isdefaultnamespace.md) | Comprueba si el área de nombres determinada es la predeterminada. |
| [lookupNamespaceURI](m-domnode-lookupnamespaceuri.md) | Se ha buscado el URI del área de nombres vinculada al prefijo dado. |
| [isEqualNode](m-domnode-isequalnode.md) | Compara dos nodos. |

## Propiedades

| Propiedad | Descripción |
| --- | --- |
| [nombreDeNodo](p-domnode-nodename.md) | Nombre de nodo cualificado. El nombre depende del tipo de nodo. |
| [nodeValue](p-domnode-nodevalue.md) | Valor del nodo. El valor depende del tipo de nodo. |
| [nodeType](p-domnode-nodetype.md) | Tipo de nodo. |
| [nodo principal](p-domnode-parentnode.md) | Nodo principal o nulo. |
| [childNodes](p-domnode-childnodes.md) | Devuelve la lista de nodos secundarios en forma de tabla. |
| [firstChild](p-domnode-firstchild.md) | Primer nodo secundario de este nodo o nulo si no tiene elementos secundarios. |
| [lastChild](p-domnode-lastchild.md) | Último nodo secundario de este nodo o nulo si no tiene elementos secundarios. |
| [nextSibling](p-domnode-nextsibling.md) | Nodo que sigue a este nodo o nulo. |
| [hermano anterior](p-domnode-previoussibling.md) | Nodo que precisa inmediatamente este nodo o nulo. |
| [atributos](p-domnode-attributes.md) | Devuelve una tabla que contiene la lista de atributos si el nodo es un elemento; en caso contrario, es nulo. |
| [namespaceURI](p-domnode-namespaceuri.md) | URI del área de nombres del nodo. |
| [prefijo](p-domnode-prefix.md) | El prefijo de espacio de nombres de este nodo o vacío si no se especifica. |
| [localName](p-domnode-localname.md) | Parte local del nombre completo del nodo. |
| [baseURI](p-domnode-baseuri.md) | URI base de este nodo. |
| [textContent](p-domnode-textcontent.md) | Contenido de texto del nodo. El valor depende del tipo de nodo. |
| [ownerDocument](p-domnode-ownerdocument.md) | Documento al que pertenece este nodo. |

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
