---
title: Introducción a los informes de análisis de Adobe Campaign
description: Aprenda a crear cubos
feature: Reporting
role: Data Engineer
level: Beginner
exl-id: f57f3074-981f-4bcf-9274-7908cd00a4a2
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 77%

---

# Introducción a los informes de análisis de Campaign {#gs-cube}

Adobe Campaign incorpora una intuitiva herramienta de exploración de datos para crear informes dinámicos.

Utilice las capacidades de marketing analytics para analizar y medir datos, calcular estadísticas y simplificar y optimizar la creación y el cálculo de informes. Puede crear informes y crear poblaciones de destinatarios y almacenarlas en listas que se puedan usar en Adobe Campaign para tareas de segmentación o segmentación.

Puede ampliar las capacidades de análisis y exploración de base de datos al mismo tiempo que facilita a los usuarios finales la configuración de informes y tablas: estos últimos solo necesitan seleccionar un cubo existente (completamente configurado) al crear su informe o tabla para procesar cálculos, medidas y estadísticas.

Los cubos se utilizan para generar ciertos informes integrados, como [informes de envío](delivery-reports.md) (seguimiento de envíos, clics, aperturas, etc.).

Una vez que se han creado y configurado, los cubos se utilizan en las casillas de consulta de los informes y en las aplicaciones web. Se pueden utilizar y manipular dentro de las tablas dinámicas.

Utilice el módulo Campaign Marketing Analytics para lo siguiente:

1. Crear cubos e indicadores

   * acumular datos y almacenarlos en una tabla de trabajo para precalcular los indicadores según las necesidades del usuario,
   * reducir el volumen de datos implicados en los distintos cálculos utilizados para los informes y las consultas, lo que optimiza de manera significativa los tiempos de cálculo del indicador,
   * simplificar el acceso a los datos, permitiendo a los usuarios manipular los datos (independientemente de si se acumularon previamente o no) en función de las distintas dimensiones.

   Para obtener más información sobre esto, consulte [Creación de indicadores](cube-indicators.md).

1. Crear tablas dinámicas explorar datos

   * explorar datos calculados y medidas configuradas,
   * seleccionar los datos que se van a mostrar y su modo de visualización,
   * personalizar las medidas y los indicadores utilizados,
   * ofrecer herramientas interactivas de análisis a los usuarios sin conocimientos técnicos.

   Para obtener más información sobre esto, consulte [Uso de cubos para explorar datos](cube-tables.md).

1. Crear una consulta con datos calculados y acumulados en un cubo.
1. Identificar poblaciones y hacerles referencia en listas.

## Terminología {#terminology}

A continuación se enumeran términos específicos al trabajar con cubos.

* **Cubo**: un cubo es una representación de información multidimensional; proporciona a los usuarios finales estructuras diseñadas para el análisis interactivo de los datos.

* **Tabla o esquema de hechos** - La tabla de hechos (o esquema de hechos) contiene los datos sin procesar o básicos en los que se basarán los análisis. Principalmente, se trata de tablas de gran volumen (posiblemente con tablas enlazadas) con cálculos que pueden ser largos. Por ejemplo, una tabla de datos puede ser: la tabla de broadlog, la tabla de compras, etc.

* **Dimensión**: las dimensiones permiten segmentar los datos en grupos: una vez creadas, las dimensiones actúan como ejes de análisis. En la mayoría de los casos se definen varios niveles para una dimensión determinada. Por ejemplo, para una dimensión temporal, los niveles son meses, días, horas, minutos, etc. Este conjunto de niveles representa la jerarquía de dimensiones y permite varios niveles de análisis de datos.

* **Agrupamiento**: en algunos campos, se puede definir un agrupamiento para reunir valores y facilitar la lectura de la información. El agrupamiento se aplica a los niveles. Se recomienda definir un agrupamiento cuando pueda haber muchos valores diferentes.

* **Medida**: las medidas más frecuentes son suma, media, máximo, mínimo, desviación típica, etc. Las medidas se pueden calcular, por ejemplo, la tasa de aceptación de una oferta es la relación entre el número de veces que se presentó comparada con el número de veces que se aceptó.
