---
title: Consultar la base de datos con queryDef
description: Aprenda a utilizar los métodos queryDef y NLWS para consultar la base de datos de Campaign
feature: API
role: Developer
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 0fd39d6c-9e87-4b0f-a960-2aef76c9c8eb
source-git-commit: 26fededf0ee83299477e45e891df30a46c6d40fe
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 2%

---

# Consultar la base de datos con queryDef {#query-database-api}

[!DNL Adobe Campaign] proporciona métodos JavaScript eficaces para interactuar con la base de datos mediante `queryDef` y `NLWS`. Estos métodos le permiten cargar, crear, actualizar y consultar datos utilizando JSON, XML o SQL.

>[!NOTE]
>
>Esta documentación cubre las API orientadas a datos para consultar la base de datos mediante programación. Para las API de REST, consulte [Introducción a las API de REST](api/get-started-apis.md). Para generar consultas visuales, consulte [Trabajar con el editor de consultas](../start/query-editor.md).

## Requisitos previos {#prerequisites}

Antes de usar los métodos queryDef y NLWS, debe estar familiarizado con lo siguiente:

* JavaScript
* [!DNL Adobe Campaign] modelo de datos y esquemas
* Expresiones XPath para navegar por elementos de esquema

Obtenga más información acerca del modelo de datos de Campaign en [esta página](datamodel.md).

## Métodos estáticos de esquema de entidad {#entity-schema-methods}

Cada esquema de [!DNL Adobe Campaign] (por ejemplo, `nms:recipient`, `nms:delivery`) viene con métodos estáticos accesibles a través del objeto `NLWS`. Estos métodos proporcionan una forma cómoda de interactuar con entidades de base de datos.

### Carga, guardado y creación de entidades {#load-save-create}

**Cargar una entidad por identificador y actualizarla:**

```javascript
// Load a delivery by @id and save
var delivery = NLWS.nmsDelivery.load("12435");
delivery.label = "New label";
delivery.save();
```

**Crear un destinatario con JSON:**

```javascript
// Create via JSON, edit via JS and save
var recipient = NLWS.nmsRecipient.create({
  x: { // the key 'x' doesn't matter
    email: 'john.doe@example.com',
  }
});
recipient.folder_id = 1183;
recipient.firstName = 'John';
recipient.lastName = 'Doe';
recipient.save();
```

**Crear un destinatario con XML:**

```javascript
// Create via XML and save
var recipient = NLWS.nmsRecipient.create(
  <recipient
    email="support@adobe.com"
    lastName="Adobe"
    firstName="Support"
  />
);
recipient.save();
```

## Información general de QueryDef {#querydef-overview}

El esquema `xtk:queryDef` proporciona métodos para generar y ejecutar consultas de base de datos. Puede usar `NLWS.xtkQueryDef.create()` para generar consultas con sintaxis JSON o XML.

**Operaciones disponibles:**

* `select` - Recuperar varios registros
* `get` - Recuperar un solo registro (SQL `LIMIT 1`)
* `getIfExists` - Recuperar un solo registro, devolver nulo si no se encuentra
* `count` - Recuento de registros que coinciden con los criterios

Obtenga más información acerca de los métodos queryDef en la [documentación de Campaign JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}.

## Consulta con JSON {#query-json}

Use `NLWS.xtkQueryDef.create()` para generar consultas con sintaxis JSON. La operación `get` recupera un único registro (SQL `LIMIT 1`), mientras que `select` recupera varios registros.

**Obtener un solo destinatario:**

```javascript
var email = "contact@example.com";
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "get", // "get" does a SQL "LIMIT 1"
    select: { 
      node: [{expr: "@id"}, {expr: "@email"}, {expr: "@firstName"}] 
    },
    where: { 
      condition: [
        {expr: "@email = '" + email + "'"}, // filter by email
      ],
    }
  }
});

var res = query.ExecuteQuery(); 
// res is an XML object such as <recipient id="1234" email="contact@example.com" firstName="John"/>
var recipient = NLWS.nmsRecipient.load(res.$id); // conversion to a JavaScript object
recipient.email = "newemail@example.com";
recipient.save();
```

**Use `getIfExists` para evitar excepciones:**

Si el registro no existe, use `operation: "getIfExists"` en lugar de `get` para evitar excepciones:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient", 
    operation: "getIfExists",
    select: { node: [{expr: "@id"}] },
    where: { 
      condition: [{expr: "@email = 'nonexistent@example.com'"}]
    }
  }
});

var res = query.ExecuteQuery();
if (res) {
  logInfo("Recipient found: " + res.$id);
} else {
  logInfo("Recipient not found");
}
```

## Seleccionar varios registros {#select-multiple}

Utilice la operación `select` para recuperar varios registros. Puede agregar condiciones, pedidos y límites.

**Flujos de trabajo de consulta con filtros y orden:**

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "xtk:workflow", 
    operation: "select", 
    select: {
      node: [
        {expr: "@id"},
        {expr: "@label"},
        {expr: "@internalName"}
      ] 
    }, 
    where: {
      condition: [
        {expr: "[folder/@name]='nmsTechnicalWorkflow'"},
        {expr: "@production = 1"}
      ]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }
});

var res = query.ExecuteQuery();

var workflows = res.getElementsByTagName("workflow");
for each (var w in workflows) {
  logInfo(w.getAttribute("internalName"));
}
```

**Envíos de consulta con sintaxis XML:**

```javascript
var q = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select" lineCount="3">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
      <node expr="@created"/>
    </select>
    <where>
      <condition expr="@label NOT LIKE '%Proof%'" bool-operator="AND"/>
      <condition expr="@created &lt;= '2024-12-01'" bool-operator="AND"/>
    </where>
    <orderBy>
      <node expr="@lastModified" sortDesc="true"/>
    </orderBy>    
  </queryDef>
);

var deliveries = q.ExecuteQuery();
for each(var delivery in deliveries.delivery) {
  logInfo(delivery.@id + ": " + delivery.@label);
}
```

>[!NOTE]
>
>El parámetro `lineCount` limita el número de resultados. Sin ella, el límite predeterminado es de 10 000 registros.

Más información sobre [ExecuteQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-ExecuteQuery.html?lang=es){target="_blank"}.

## Consulta de datos de transición de flujo de trabajo {#workflow-transition-data}

Al trabajar con actividades de JavaScript en flujos de trabajo, puede consultar datos de transiciones entrantes mediante `vars.targetSchema` y `vars.tableName`.

**Consultar datos de destinatario de una transición de flujo de trabajo:**

```javascript
// Query data from the incoming transition
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema, // The schema from the previous activity
    operation: 'select', 
    lineCount: 999999999, // Override default 10,000 limit
    select: { 
      node: [
        {expr: '@id'},
        {expr: '@email'},
        {expr: '@firstName'},
        {expr: '@lastName'}
      ]
    },
  }
});

var records = query.ExecuteQuery(); // Returns a DOMElement

for each(var record in records.getElements()) {
  logInfo("Processing: " + record.$id + " - " + record.$email);
  
  // Clean email address
  var cleanedEmail = record.$email.replace(/\s+/g, '').toLowerCase();
  
  // Update using parameterized query to prevent SQL injection
  sqlExec(
    "UPDATE " + vars.tableName + " SET sEmail=$(sz) WHERE iId=$(l)", 
    cleanedEmail, 
    record.$id
  );
}
```

>[!CAUTION]
>
>Utilice siempre consultas parametrizadas con `$(sz)` para cadenas y `$(l)` para enteros con el fin de evitar vulnerabilidades de inyección de SQL. Obtenga más información en la [documentación de JSAPI de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/f-sqlExec.html){target="_blank"}.

## Recuento de registros {#count-records}

Use `Count(@id)` con un alias para contar registros.

**Recuento ejecutando hipótesis:**

```javascript
var jobCount = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:remaHypothesis" operation="get">
    <select>
      <node expr="Count(@id)" alias="@count"/>
    </select>
    <where>
      <condition expr={"@status=" + HYPOTHESIS_STATUS_RUNNING}/>
    </where>
  </queryDef>
);

var iJobCount = parseInt(jobCount.ExecuteQuery().@count);
logInfo("Running jobs: " + iJobCount);
```

**Recuento con varias condiciones:**

```javascript
var xmlQuery = <queryDef schema="nms:trackingLogRcp" operation="select">
  <select>
    <node expr="DateOnly(@logDate)" groupBy="1"/>
    <node expr="count(@id)" alias="@count"/>
    <node expr="countDistinct([@broadLog-id])" alias="@distinctCount"/>
  </select>
  <where>
    <condition expr={"@logDate IS NOT NULL AND @logDate &lt; #" + today + "# AND [@url-id] &lt;&gt; 1"}/>
  </where>
</queryDef>;

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Distribución de valores {#distribution-values}

Obtenga la distribución de valores para un campo específico, útil para analizar patrones de datos.

**Distribución de códigos de país:**

```javascript
/**
 * @class DistributionOfValues
 * @param {string} schema - The schema name (e.g., 'nms:recipient')
 * @param {string} field - The field to analyze (e.g., '@country')
 */
function DistributionOfValues(schema, field) {
  this.queryDef = {
    operation: 'select', 
    lineCount: 200, 
    schema: schema,
    select: {
      node: [
        {alias: '@expr', expr: field, groupBy: 'true', noSqlBind: 'true'},
        {alias: '@count', expr: 'COUNT()', label: 'Count'},
      ]
    },
    orderBy: {
      node: [{expr: 'COUNT()', sortDesc: 'true'}]
    },
  };
  
  /**
   * Execute the query and return results
   * @return {Array} XML list of results
   */
  this.get = function() {
    this.results = NLWS.xtkQueryDef.create({queryDef: this.queryDef}).ExecuteQuery();
    return this.results.getElements();
  };
}

// Usage example
var d = new DistributionOfValues('nms:recipient', '@country');

// Optional: Add additional filters
d.queryDef.where = {
  condition: [{expr: 'DateOnly(@created) = #2024-12-01#'}]
};

// Execute and display results
for each(var result in d.get()) {
  logInfo(result.$expr + ': ' + result.$count);
}
```

## Construcción dinámica de consultas {#dynamic-queries}

Cree consultas de forma dinámica añadiendo condiciones mediante programación.

**Anexar condiciones a una consulta existente:**

```javascript
var xmlQuery = <queryDef schema="nms:delivery" operation="select">
  <select>
    <node expr="@id"/>
    <node expr="@label"/>
  </select>
  <where/>
</queryDef>;

// Dynamically add conditions
if (includeProofs) {
  xmlQuery.where.appendChild(
    <condition expr="@label LIKE '%Proof%'"/>
  );
}

if (startDate) {
  xmlQuery.where.appendChild(
    <condition expr={"@created >= #" + Format.toISO8601(startDate) + "#"}/>
  );
}

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

**Generar cláusulas select y where en bucles:**

```javascript
// Build select dynamically
var select = <select/>;
var fields = ["@id", "@label", "@created"];
for each(var field in fields) {
  select.appendChild(<node expr={field}/>);
}

// Build where dynamically
var where = <where/>;
var conditions = [
  "@status = 1",
  "@type = 'email'"
];
for each(var condition in conditions) {
  where.appendChild(<condition expr={condition}/>);
}

// Create complete query
var xmlQuery = <queryDef operation="select" schema="nms:delivery"/>;
xmlQuery.appendChild(select);
xmlQuery.appendChild(where);

var result = NLWS.xtkQueryDef.create(xmlQuery).ExecuteQuery();
```

## Métodos queryDef avanzados {#advanced-methods}

Más allá de `ExecuteQuery()`, queryDef proporciona varios métodos especializados para casos de uso avanzados.

### BuildQuery: generar SQL sin ejecutar {#build-query}

Use `BuildQuery()` para generar la instrucción SQL sin ejecutarla. Esto resulta útil para depurar, registrar o pasar consultas a sistemas externos.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
    </select>
    <where>
      <condition expr="@email IS NOT NULL"/>
    </where>
  </queryDef>
);

// Get the generated SQL
var sql = query.BuildQuery();
logInfo("Generated SQL: " + sql);
// Output: "SELECT iRecipientId, sEmail FROM NmsRecipient WHERE sEmail IS NOT NULL"
```

Más información sobre [BuildQuery](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQuery.html){target="_blank"}.

### BuildQueryEx: obtener SQL con cadena de formato {#build-query-ex}

`BuildQueryEx()` devuelve la consulta SQL y una cadena de formato compatible con la función `sqlSelect()`.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@email"/>
      <node expr="@firstName"/>
    </select>
  </queryDef>
);

var [sql, format] = query.BuildQueryEx();
logInfo("SQL: " + sql);
logInfo("Format: " + format);

// Use with sqlSelect
var results = sqlSelect(format, sql);
```

Más información sobre [BuildQueryEx](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-BuildQueryEx.html){target="_blank"}.

### Seleccionar todo: agregue todos los campos que desea seleccionar {#select-all}

El método `SelectAll()` agrega automáticamente todos los campos del esquema a la cláusula select, lo que le evita enumerar cada campo manualmente.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:recipient" operation="select">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Add all fields to the select
query.SelectAll(false);

var result = query.ExecuteQuery();
// Result contains all recipient fields
```

Más información sobre [SelectAll](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-SelectAll.html){target="_blank"}.

### Actualización: Actualización masiva de registros {#mass-update}

El método `Update()` le permite realizar actualizaciones masivas de los registros que coinciden con los criterios de consulta sin cargar cada registro individualmente.

```javascript
// Mass update example: set a field value for all matching records
var updateQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "update",
    where: {
      condition: [{expr: "@country = 'US'"}]
    },
    set: {
      node: [{expr: "@blackList", value: "0"}]
    }
  }
});

// Execute mass update
updateQuery.Update();
logInfo("Mass update completed");
```

>[!CAUTION]
>
>Las actualizaciones masivas afectan a todos los registros que coinciden con la cláusula where. Pruebe siempre primero las condiciones where con una consulta de selección para comprobar qué registros se verán afectados.

Más información sobre [Actualización](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-Update.html){target="_blank"}.

### GetInstanceFromModel: instancias de plantilla de consulta {#get-instance-from-model}

Utilice `GetInstanceFromModel()` para recuperar datos de instancias creadas a partir de plantillas.

```javascript
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="select">
    <select>
      <node expr="@id"/>
      <node expr="@label"/>
    </select>
    <where>
      <condition expr="@isModel = 1"/>
    </where>
  </queryDef>
);

// Get instance data from template
var instance = query.GetInstanceFromModel("nms:delivery");
```

Más información sobre [GetInstanceFromModel](https://experienceleague.adobe.com/developer/campaign-api/api/sm-queryDef-GetInstanceFromModel.html){target="_blank"}.

## Operaciones por lotes {#batch-operations}

Procesar varios registros en lote para mejorar el rendimiento.

**Actualizar etiquetas de envío por lotes:**

```javascript
// Query all deliveries to update
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: vars.targetSchema,
    operation: 'select', 
    lineCount: 999999999,
    select: { 
      node: [{expr: '@id'}]
    },
    where: {
      condition: [{expr: "@label LIKE '%OLD%'"}]
    }
  }
});

var records = query.ExecuteQuery();

// Process each record
for each(var record in records.getElements()) {
  var delivery = NLWS.nmsDelivery.load(record.$id);
  var oldLabel = delivery.label.toString();
  var newLabel = oldLabel.replace(/OLD/g, 'NEW');
  
  logInfo("Updating: " + oldLabel + " => " + newLabel);
  
  delivery.label = newLabel;
  delivery.save();
}

logInfo("Updated " + records.getElements().length + " deliveries");
```

## Ejecución de SQL sin procesar {#raw-sql}

Para operaciones complejas, puede ejecutar SQL sin procesar directamente.

**Ejecutar SQL parametrizado:**

```javascript
var dbEngine = instance.engine;

// Using parameterized query (recommended)
dbEngine.exec(
  "UPDATE NmsUserAgentStats SET iVisitorsOfTheDay=$(l) WHERE tsDate=$(dt)", 
  visitorCount,
  Format.parseDateTimeInter(dateString)
);
```

**Consulta con sqlSelect:**

```javascript
// Execute SELECT query and parse results
var xml = sqlSelect(
  "collection,@id,@email", 
  "SELECT iId as id, sEmail as email FROM " + vars.tableName + " WHERE iStatus = 1"
);

logInfo(xml.toXMLString()); // "<select><collection id="1" email="..."/></select>"

for each(var record in xml.collection) {
  logInfo('ID: ' + record.@id + ', Email: ' + record.@email);
  
  // Load full object if needed
  if (vars.targetSchema == "nms:recipient") {
    var recipient = NLWS.nmsRecipient.load(record.@id);
    recipient.lastName = recipient.lastName.toUpperCase();
    recipient.save();
  }
}
```

>[!CAUTION]
>
>Al utilizar SQL sin procesar:
>
>* Validar y sanear siempre las entradas del usuario
>* Usar consultas parametrizadas con `$(sz)`, `$(l)`, `$(dt)`, etc.
>* Tenga en cuenta las diferencias entre las bases de datos locales y en la nube en [implementaciones de FDAC](../architecture/enterprise-deployment.md)

## Prácticas recomendadas {#best-practices}

Al trabajar con métodos queryDef y NLWS:

* **Usar consultas parametrizadas** - Usar siempre parámetros enlazados (`$(sz)`, `$(l)`) con `sqlExec` para evitar la inyección de SQL
* **Establecer lineCount** - Anule el límite predeterminado de 10.000 registros cuando sea necesario con `lineCount: 999999999`
* **Usar getIfExists** - Usar `operation: "getIfExists"` cuando no existan registros para evitar excepciones
* **Optimizar consultas** - Agregar las `where` condiciones adecuadas para limitar los conjuntos de resultados
* **Procesamiento por lotes**: procese conjuntos de datos grandes por lotes para evitar tiempos de espera
* **Seguridad de transacciones** - Considere la posibilidad de utilizar transacciones para varias actualizaciones relacionadas
* **Reconocimiento de FDAC** - En [implementaciones empresariales (FDAC)](../architecture/enterprise-deployment.md), tenga en cuenta que [!DNL Campaign] funciona con dos bases de datos



## Casos de uso prácticos {#use-cases}

### Depuración y registro de consultas {#debug-queries}

Use `BuildQuery()` para inspeccionar el SQL generado antes de la ejecución:

```javascript
var query = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@blackList = 0"}] }
  }
});

// Log the SQL for debugging
var sql = query.BuildQuery();
logInfo("About to execute: " + sql);

// Now execute
var results = query.ExecuteQuery();
```

### Duplicación de un registro con SelectAll {#duplicate-record}

Use `SelectAll()` para copiar todos los campos al duplicar registros:

```javascript
// Query the original record
var query = NLWS.xtkQueryDef.create(
  <queryDef schema="nms:delivery" operation="get">
    <select/>
    <where>
      <condition expr="@id = 12345"/>
    </where>
  </queryDef>
);

// Select all fields for duplication
query.SelectAll(true); // true indicates duplication mode

var original = query.ExecuteQuery();

// Create a new delivery from the original
var newDelivery = NLWS.nmsDelivery.create(original);
newDelivery.label = original.@label + " (Copy)";
newDelivery.save();
```

### Validar antes de la actualización masiva {#validate-mass-update}

Previsualice siempre los registros afectados antes de realizar actualizaciones masivas:

```javascript
// Step 1: Preview what will be updated
var previewQuery = NLWS.xtkQueryDef.create({
  queryDef: {
    schema: "nms:recipient",
    operation: "select",
    select: { node: [{expr: "@id"}, {expr: "@email"}] },
    where: { condition: [{expr: "@country = 'US' AND @blackList = 1"}] }
  }
});

var preview = previewQuery.ExecuteQuery();
var count = preview.getElementsByTagName("recipient").length;
logInfo("About to update " + count + " recipients");

// Step 2: If count looks correct, proceed with mass update
if (count > 0 && count < 10000) {
  sqlExec("UPDATE NmsRecipient SET iBlackList = 0 WHERE sCountryCode = 'US' AND iBlackList = 1");
  logInfo("Mass update completed for " + count + " recipients");
} else {
  logWarning("Update cancelled: count is " + count);
}
```

## Referencia de sintaxis de definición de consulta {#querydef-reference}

Estructura completa del objeto `queryDef`:

```javascript
{
  queryDef: {
    schema: 'nms:recipient',           // Required: target schema
    operation: 'select',                // select|get|getIfExists|count
    lineCount: 100,                    // Maximum records to return
    startLine: 0,                      // Offset for pagination
    select: {
      node: [
        {
          expr: '@id',                 // XPath expression
          alias: '@myAlias',           // Optional alias
          label: 'ID',                 // Optional label
          groupBy: 'true',             // Group by this field
          noSqlBind: 'true'            // No SQL binding on constants
        }
      ]
    },
    where: {
      condition: [
        {
          expr: '@email IS NOT NULL',  // Condition expression
          boolOperator: 'AND',         // AND|OR
          setOperator: 'EXISTS',       // EXISTS|NOT EXISTS|IN|NOT IN
          enabledIf: '',               // Enabling condition
          ignore: false,               // Ignore this condition
          sql: '',                     // Native SQL expression
          'filter-name': ''            // Predefined filter name
        }
      ]
    },
    orderBy: {
      node: [
        {
          expr: '@lastModified',       // Field to sort by
          sortDesc: 'true'             // true for DESC, false for ASC
        }
      ]
    },
    groupBy: {
      node: [
        {expr: '@country'}             // Group by field
      ]
    }
  }
}
```

## Temas relacionados {#related-topics}

* [Introducción a las API de Campaign](api.md)
* [Referencia de API queryDef](https://experienceleague.adobe.com/developer/campaign-api/api/s-xtk-queryDef.html){target="_blank"}
* [Documentación de JSAPI de Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=es){target="_blank"}
* [Modelo de datos](datamodel.md)
* [Trabajo con esquemas](schemas.md)
* [Trabajo con el editor de consultas](../start/query-editor.md)

