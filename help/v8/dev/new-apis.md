---
product: Adobe Campaign
title: Nuevas API de Campaign v8
description: Nuevas API de Campaign v8
feature: Información general
role: Data Engineer
level: Beginner
source-git-commit: b11b42220dae7d0a878ba102523ee2825d6fb2e2
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 4%

---

# Nuevas API de campaña{#gs-new-api}

Campaign v8 incluye dos nuevas API para administrar datos entre la base de datos local de Campaign y la base de datos de Cloud. Los requisitos previos para utilizarlos son habilitar el mecanismo de ensayo en el esquema. [Más información](staging.md)

* API de ingesta: **xtk.session.ingest**

   Esta API está dedicada únicamente a la inserción de datos. [Más información](#data-insert-api)

* API de actualización/eliminación de datos: **xtk.session.ingestExt**

   Esta API se utiliza para actualizar o eliminar datos. [Más información](#data-update-api)

Un flujo de trabajo integrado dedicado sincronizará los datos en la base de datos de Cloud.

## Insertar datos{#data-insert-api}

La API **xtk.session.ingest** está dedicada únicamente a la inserción de datos. Sin actualización/eliminación.

### Insertar sin reconciliación

**En un flujo de trabajo**

Utilice el siguiente código en una actividad **Javascript code** para insertar datos en la base de datos de Cloud sin reconciliación:

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Una vez ejecutado el flujo de trabajo, la tabla de ensayo se alimenta según lo esperado.

**Desde una llamada SOAP**

1. Obtenga el token de autenticación.
1. Déclencheur de la API. La carga útil es:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. UUID se devuelve a la respuesta SOAP:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Como resultado, la tabla de ensayo se alimenta según lo esperado.

![](assets/no-reconciliation.png)

### Insertar con reconciliación

**En un flujo de trabajo**

Utilice el siguiente código en una actividad **Javascript code** para insertar datos en la base de datos de Cloud con reconciliación:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Una vez ejecutado el flujo de trabajo, la tabla de ensayo se alimenta según lo esperado.

![](assets/with-reconciliation.png)


**Desde una llamada SOAP**

1. Obtenga el token de autenticación.
1. Déclencheur de la API. La carga útil es:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. En este caso, el UUID no se devuelve a la respuesta porque se ha proporcionado en la carga útil. La respuesta es:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Como resultado, la tabla de ensayo se alimenta según lo esperado.

## Actualizar o eliminar datos{#data-update-api}

La API **xtk.session.IngestExt** está optimizada para la actualización/eliminación de datos. Para insertar solamente, prefiera **xtk.session.ingest**. Insert funciona si la clave de registro no está en la tabla de ensayo.

### Insertar/actualizar

**En un flujo de trabajo**

Utilice el siguiente código en una actividad **Javascript code** para actualizar los datos en la base de datos de Cloud:

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Una vez ejecutado el flujo de trabajo, la tabla de ensayo se actualiza según lo esperado.

![](assets/updated-data.png)

**Desde una llamada SOAP**


1. Obtenga el token de autenticación.
1. Déclencheur de la API. La carga útil es:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. La respuesta SOAP es:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Como resultado, la tabla de ensayo se actualiza según lo esperado.

## Administración de suscripciones {#sub-apis}

La administración de suscripciones en Campaign se describe en [esta página](../start/subscriptions.md).

La inserción de los datos de suscripción y baja depende del [Mecanismo de ensayo](staging.md) en la base de datos local de Campaign. La información del suscriptor se almacena temporalmente en tablas de ensayo en la base de datos local y el flujo de trabajo de sincronización envía estos datos de la base de datos local a la base de datos de Cloud. Como consecuencia, los procesos de suscripción y baja son **asíncronos**. Las solicitudes de inclusión y exclusión se procesan cada hora a través de un flujo de trabajo técnico específico. [Más información](../config/replication.md#tech-wf)


**Temas relacionados**

* [Campaign Classic v7 JSAPI](https://docs.adobe.com/content/help/en/campaign-classic/technicalresources/api/p-1.html)
