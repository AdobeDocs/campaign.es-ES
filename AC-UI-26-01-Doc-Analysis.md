---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01 Análisis de la documentación

## Contenido de la próxima versión

Este documento analiza los JIRA del producto para las versiones mensuales AC-UI-26-01 y AC-UI-25-11 para planificar las acciones de documentación.

### Filtros JIRA

1. **[Historias mensuales de AC-UI-26-01](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Historias de la versión principal
2. **[Mejoras de NEO-92400](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))**: problemas vinculados con mejoras en la versión
3. **[Historias mensuales de AC-UI-25-11](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Arrastre de la versión anterior
4. **[AC-UI-25-11 Excluyendo 8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** - Versión anterior filtrada

&#x200B;---

## 🟢 Crear DOCAC

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) - Agregar compatibilidad con campos de personalización (integración avanzada de AEM)**Estado:** Resuelto\Se requiere **Doc:** Sí\**DOCAC existente:** Ninguno\**Acción:** Crear DOCAC

**Ámbito:**
- Compatibilidad de documentos para campos de personalización en la integración avanzada de AEM
- Flujo de trabajo de IU y pasos de configuración
- Funciones de integración multilingüe de AEM

**Descripción de característica:**
Compatibilidad para añadir campos de personalización en las entregas mediante la integración avanzada de AEM, lo que permite la inserción de contenido dinámico desde los datos de Campaign en plantillas de correo electrónico creadas por AEM.

**Contexto:** ACS a paridad ACC, requisito específico de MSFT

**Referencias:** [wiki multilingüe de AEM](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

&#x200B;---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) - Proceso de cálculo de programación de envíos (paridad ACS)**Estado:** Nuevo\Se requiere **Doc:** Sí\**DOCAC existente:** Ninguno\**Acción:** Crear DOCAC

**Ámbito:**
- Proceso de cálculo de programación de entrega de documentos para notificaciones push
- Fórmulas de programación basadas en zonas horarias
- Carga de archivos para direccionamiento de varias zonas horarias

**Descripción de característica:**
Habilite la programación de envíos basada en archivos OOTB con tiempos de envío calculados según la zona horaria del destinatario, lo que permite una sola segmentación de envíos en varias zonas horarias con tiempos de envío optimizados por región.

**Contexto:** Impulsado por el cliente (H&amp;M), ACS a requisito de paridad ACC

**Referencias:** [Documentación de ACS](https://experienceleague.adobe.com/en/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

&#x200B;---

## DOCAC de actualización de 🔄

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973): disponibilidad de informes dinámicos para todos los usuarios de la interfaz de usuario web&#x200B;**Estado:** En Curso\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070) (Cerrado), [DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432) (Resuelto)\**Acción:** revisar DOCAC

**Ámbito:**
- Actualizar la información de disponibilidad (ahora para todos los usuarios de la interfaz de usuario web, no solo para 8.7)
- Limitaciones de idioma del documento
- Aclarar la visualización de métricas conflictivas con informes heredados

**Descripción de característica:**
El sistema de informes dinámico ya está disponible para todos los usuarios de la interfaz de usuario web de Campaign (anteriormente limitado a 8,7 ACS para clientes ACC), lo que proporciona funciones avanzadas de análisis e informes personalizados con una interfaz de estilo ACS.

**Contexto:** expansión de características, dependencia de compilación del servidor (8.8.1)

**Referencias:** [Wiki - Comparación de informes](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

&#x200B;---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - Prueba A/B&#x200B;**Estado:** En Curso\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104) (Nuevo)\**Acción:** Actualizar DOCAC

**Ámbito:**
- Documentación completa del flujo de trabajo de pruebas A/B
- Configuración de experimentación de contenido y configuración de variante
- Definición de la proporción de muestra y criterios de selección del ganador
- Recopilación y evaluación de estadísticas

**Descripción de característica:**
La experimentación de contenido y las pruebas A/B para envíos de correo electrónico permiten a los especialistas en marketing probar diferentes variantes de contenido, definir tamaños de muestra, recopilar estadísticas de rendimiento y enviar automáticamente la variante ganadora a los destinatarios restantes.

**Contexto:** proyecto Europa, requisito de Microsoft, indicador de funcionalidad habilitado

**Referencias:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [Figma se burla](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

&#x200B;---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126): creación de esquemas (crear nueva tabla, ampliar esquemas, acceder a BD externa)**Estado:** En Curso\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826) (Nuevo)\**Acción:** Actualizar DOCAC

**Ámbito:**
- Flujo de trabajo de creación de esquemas de documentos (solo 3 opciones: crear tabla, ampliar esquema, acceder a base de datos externa)
- Definición de formulario para entidades personalizadas
- Operaciones Navigate y CRUD en esquemas personalizados
- Funciones de fase 2 y fase 3

**Descripción de característica:**
Funciones de creación de esquemas en la interfaz de usuario web que permiten a los administradores crear nuevas tablas de base de datos, ampliar esquemas existentes con campos personalizados y conectarse a bases de datos externas, lo que resulta esencial para personalizar el modelo de datos.

**Contexto:** requisito de Microsoft, proyecto Europa, entrega por fases (fase 2 activa, fase 3, fin de febrero)

**Referencias:** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

&#x200B;---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) - Web Analytics&#x200B;**Estado:** Nuevo\Se requiere **Doc:** Sí\**DOCAC existente:** Ninguno\**Acción:** Crear DOCAC

**Ámbito:**
- Configuración de cuenta externa de Web Analytics
- Configuración y autenticación de la integración
- Uso de datos de Analytics en campañas

**Descripción de característica:**
Integración de Web Analytics que permite la conexión a plataformas de análisis web para el seguimiento y la creación de informes sobre el rendimiento de la campaña y el comportamiento de los visitantes del sitio web.

**Contexto:** Solicitud de cliente (P2E-RSC), disponibilidad de entorno pendiente

**Referencias:** Ninguna proporcionada

&#x200B;---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753): integración de AEM para Live Copies/Copias de idioma&#x200B;**Estado:** Nuevo\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829) (resuelto)\**Acción:** revisar DOCAC

**Ámbito:**
- Examinar plantillas de envío de AEM
- Crear Live Copies y copias de idioma con un solo clic
- Flujo de trabajo de creación de variantes de contenido multilingüe

**Descripción de característica:**
Integración de AEM optimizada que permite crear con un solo clic Live Copies y copias de idioma a partir de plantillas de entrega de AEM, lo que simplifica la creación de campañas multilingües para los usuarios de AEM.

**Contexto:** Requisito de Microsoft, trabajo transferido al equipo de Himanshu

**Referencias:** [Documentación de ACS](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html)

&#x200B;---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) - Editor de contenido: usar variables de temas en el fragmento&#x200B;**Estado:** Nuevo\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941) (Nuevo)\**Acción:** Actualizar DOCAC

**Ámbito:**
- Variables de tema en el diseñador de correo electrónico (Beta)
- Uso de temáticas en fragmentos
- Activación precisa de funciones

**Descripción de característica:**
Compatibilidad para utilizar variables de temas dentro de fragmentos de contenido, lo que permite una aplicación del sistema de diseño y promoción de la marca coherente en todos los componentes de correo electrónico con administración centralizada de temas.

**Contexto:** En espera, característica precisa que se volverá a visitar

**Referencias:** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

&#x200B;---

## ➕ Crear DOCAC (mejoras)

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) - Filtros predefinidos - Opción compartida&#x200B;**Estado:** Resuelto\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697) (Revisión de código), [DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522) (Cerrado - Ayudante)\**Acción:** revisar DOCAC

**Ámbito:**
- Opción compartida para filtros predefinidos
- Filtrar la visibilidad con otros operadores (comportamiento de ACC frente a Brand Recorrido)
- Administración de usuarios de filtros compartidos

**Descripción de característica:**
Los filtros predefinidos ahora se pueden marcar como &quot;compartidos&quot; para que sean visibles para otros operadores, con un comportamiento diferente para ACC (predeterminado) y Brand Recorrido (filtrado específico del usuario).

**Contexto:** Mejora del generador de reglas, indicador de características: enable-query-filter-shared

**Referencias:** relacionadas con [NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)

&#x200B;---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) - Actividad de entrega continua&#x200B;**Estado:** Cerrado\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586) (Nuevo), [DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808) (Cerrado: ayuda contextual)\**Acción:** Actualizar DOCAC

**Ámbito:**
- Actividad de flujo de trabajo de entrega continua
- Configuración del selector de plantillas de envío
- Generación automática de transición saliente
- Opciones de segmentación (sin acceso a contenido)

**Descripción de característica:**
La actividad de envío continuo para flujos de trabajo permite la ejecución de envíos recurrentes desde plantillas, lo que genera automáticamente transiciones salientes para la orquestación del flujo de trabajo sin modificación de contenido.

**Contexto:** Indicador de característica: enable-continuous-delivery

**Referencias:** Épica relacionada [NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

&#x200B;---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130): habilitar la carga de archivos OOTB para notificaciones push multilingües&#x200B;**Estado:** Cerrado\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606) (Nuevo)\**Acción:** Actualizar DOCAC

**Ámbito:**
- Carga de archivos para notificaciones push multilingües (iOS y Android)
- Formato CSV y asignación de campos
- Compatibilidad push enriquecida con funciones multilingües

**Descripción de característica:**
Capacidad de carga de archivos OOTB para crear envíos de notificaciones push multilingües mediante la importación de CSV, la coincidencia de la funcionalidad de ACS y la activación de una configuración de campaña multilingüe eficaz.

**Contexto:** impulsado por el cliente (H&amp;M), paridad de ACS con ACC, crítico para la migración

**Referencias:** [Documentación de ACS](https://experienceleague.adobe.com/en/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

&#x200B;---

## ❌ Cancelado/Ya No Se Aplica

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566): compatibilidad con el seguimiento de CTA en webui&#x200B;**Estado:** Cerrado (Ya No Se Aplica)\Se requiere **Doc:** No\**DOCAC existente:** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821) (Nuevo)\**Acción:** Cerrar DOCAC

**Motivo:** Nueva característica de ACS compatible con MSFT: no iniciada, con información pendiente de MSFT, no se esperaba ningún trabajo de interfaz de usuario

**Contexto:** requisito de seguimiento CTA específico de Microsoft

&#x200B;---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564): compatibilidad con IU multilingüe de AEM&#x200B;**Estado:** Cerrado (Ya No Se Aplica)\Se requiere **Doc:** No\**DOCAC existente:** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822) (Nuevo)\**Acción:** Cerrar DOCAC

**Razón:** trabajo en la interfaz de usuario administrado por el equipo de Himanshu (historia diferente)

**Contexto:** requisito de Microsoft, trabajo transferido

&#x200B;---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) - Agregar compatibilidad con la función NRT&#x200B;**Estado:** Resuelto (Ya No Se Aplica)\Se requiere **Doc:** No\**DOCAC existente:** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824) (Nuevo)\**Acción:** Cerrar DOCAC

**Razón:** Nueva característica específica de ACS para MSFT: especificación disponible, pero sin impacto en la interfaz de usuario web

**Contexto:** requisito de Microsoft, mensajería transaccional

&#x200B;---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563): API REST transaccional para enriquecimiento basado en perfiles&#x200B;**Estado:** Resuelto (Ya No Se Aplica)\Se requiere **Doc:** No\**DOCAC existente:** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825) (Nuevo)\**Acción:** Cerrar DOCAC

**Motivo:** No funciona la interfaz de usuario web, la instancia actualizada está pendiente y la actualización de la compilación es obligatoria para el lanzamiento

**Contexto:** característica de extremo de API de REST

&#x200B;---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) - Mensajería transaccional de enriquecimiento basada en perfiles Fase 2&#x200B;**Estado:** Resuelto (Ya No Se Aplica)\Se requiere **Doc:** No\**DOCAC existente:** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823) (Nuevo)\**Acción:** Cerrar DOCAC

**Motivo:** La historia no tiene tareas, marcadas como &quot;ya no se aplica&quot;

**Contexto:** requisito de Microsoft, proyecto Europa

&#x200B;---

## 🟢 Documentación Lista (Desde AC-UI-25-11)

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) - Inserción enriquecida multilingüe - IU&#x200B;**Estado:** Cerrado\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565) (Nuevo)\**Acción:** revisar DOCAC

**Ámbito:**
- Campos push enriquecidos para envíos multilingües
- Compatibilidad con las plataformas iOS y Android
- Configuración de plantilla y contenido

**Descripción de característica:**
Compatibilidad con notificaciones push enriquecidas con funciones multilingües, lo que permite a los especialistas en marketing crear notificaciones push mejoradas con imágenes, botones y medios enriquecidos tanto para iOS como para Android en varios idiomas.

**Contexto:** Impulsado por el cliente (H&amp;M), entregado entre el 25 y el 11, trabajo back-end completado

**Referencias:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

&#x200B;---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916): configure y administre el proceso de aprobación&#x200B;**Estado:** Resuelto\Se requiere **Doc:** Sí\**DOCAC existente:** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827) (Nuevo)\**Acción:** Actualizar DOCAC

**Ámbito:**
- Configuración de operadores de validación en entrega/campaña
- Configuración del flujo de trabajo de aprobación
- Proceso de aprobación de contenido y destinatario
- Compatibilidad con varios canales (correo electrónico, SMS, push, correo directo, centro de llamadas, personalizado)

**Descripción de característica:**
Gestión del proceso de aprobación que permite flujos de trabajo de validación para el contenido de envío y la segmentación, con asignación de operadores y seguimiento de aprobación en todos los canales de envío.

**Contexto:** Impulsado por el cliente (Pierre Fabre), requisito de Microsoft, desarrollo completado y en prueba

**Referencias:** [Documentación clásica](https://experienceleague.adobe.com/en/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [Burlas de Figma](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

&#x200B;---

## 📊 resumen por acción

| Acción | Recuento |
|--------|-------|
| 🟢 Crear DOCAC | 3 |
| DOCAC de actualización de 🔄 | 6 |
| ✅ revisar DOCAC | 3 |
| ❌ Cerrar DOCAC | 5 |
| **Total** | **17** |

&#x200B;---

## ⚠️ preguntas abiertas

1. NEO-93487 - Escalación de H&amp;M - necesita atención urgente para programar el proceso de computación
2. NEO-92668: Análisis web: esperando la disponibilidad del entorno antes de poder completar la documentación
3. NEO-76126: Esquemas, fase 3: fin de febrero de ETA; se necesita una historia de documentación independiente.
4. NEO-88838: variables de tema, en espera, pendiente de revisión de la función de Acrite
5. Informes dinámicos: aclare las métricas conflictivas y muestre las directrices con los informes heredados

&#x200B;---

## 🔗 épicas relacionadas

- NEO-85263: épica principal de ACS a ACC (EUROPA)
- NEO-67972: mejoras en el flujo de trabajo
- NEO-87980: integración avanzada con AEM
- NEO-90199: preparación de la versión de Dynamic Reporting
- NEO-63067: experimentación de contenido UX/UI
- NEO-67726: Pruebas A/B y experimentación de contenido
- NEO-85274 - Esquema y formulario (Fase 2)
- NEO-87993: esquema y formulario (fase 3)
