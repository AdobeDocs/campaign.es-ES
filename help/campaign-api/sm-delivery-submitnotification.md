---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%
---
# SubmitNotification

Crear y enviar una notificación desde un escenario.

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## Parámetros

**scenarioName** nombre interno de la plantilla

**target** población de destinatarios de envío que reemplaza a la del escenario

## Valor(es) devuelto(s)

**notificationId** Identificador de notificación

## Observaciones

Advertencia: Esta API no está diseñada para administrar grandes volúmenes de datos ni funciona en tiempo real. Está desarrollado para procesar un máximo de varias llamadas por minuto. SubmitNotification bloqueará el subproceso durante el análisis de envío. Esto puede tardar unos segundos. El parámetro &quot;target&quot; especifica el destino de la entrega. Anula un destino especificado en la plantilla. Para enviar a un destino en la base de datos, el elemento de destino utiliza la siguiente sintaxis:

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

Para enviar a un destinatario en un archivo:

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

Es posible definir explícitamente el objetivo (en realidad el contenido del archivo utilizado como objetivo):

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

También es posible mantener el objetivo definido en la plantilla con el atributo &quot;\_keepTemplateTarget&quot;

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## Funciones

**Esquema:** [nms:delivery](s-nms-delivery.md)

**Estático:**

Sí
