---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 3%

---
# Análisis de entradas de AC-UI Jira - Resumen de trabajo
**Fecha:** 12 de enero de 2026
**Tipo de documento:** Documento de trabajo / Análisis interno

---

## Resumen ejecutivo

Este documento analiza los tickets de producto Jira de varias consultas relacionadas con las versiones de la IU de AC (enero de 2026 y noviembre de 2025). El análisis se centra en identificar los requisitos de documentación, proponer tickets DOCAC y destacar las preguntas abiertas.

**Total de tickets únicos analizados:** 19
**Tickets que requieren documentación:** 14
**Entradas Ya Documentadas:** 5
**Entradas sin necesidad de documentos:** 5

---

## &#x200B;1. Lista de tickets analizados

### 1.1 AC-UI-26-01-Versión mensual (enero de 2026)

| ID de vale | Título | Estado | Prioridad | Componentes |
|-----------|-------|--------|----------|------------|
| NEO-91565 | [Interfaz de usuario web] Agregar compatibilidad con campos de personalización (Integración avanzada con AEM) | Resuelto | Normal | ACS a ACC, IU/UX PIX |
| NEO-80973 | Disponibilidad del sistema de informes dinámico para todos los usuarios de IU web | En curso | Normal | ACS a ACC, IU/UX PIX |
| NEO-86754 | Prueba A/B de [UX/UI] | En curso | Bloqueador | IU/UX PIX |
| NEO-76126 | Creación de esquemas: creación de una nueva tabla, ampliación de esquemas y acceso a bases de datos externas | En curso | Importante | IU/UX PIX |
| NEO-93487 | [Interfaz de usuario web] Proceso de cálculo de programación de envíos similar al de ACS | Nuevo | Importante | IU/UX PIX |
| NEO-92400 | Mejoras de la versión, 26 de enero | Nuevo | Normal | IU/UX PIX |
| NEO-88838 | Editor de contenido: usar variables de temas en el fragmento | Nuevo | Normal | IU/UX PIX |
| NEO-92668 | [UX/UI] de análisis web | Nuevo | Normal | IU/UX PIX |
| NEO-86753 | Integración de [UX/UI] AEM para Live Copies/Copias de idioma | Nuevo | Bloqueador | ACS a ACC, IU/UX PIX |

### 1.2 Mejoras de la versión Tickets vinculados (NEO-92400)

| ID de vale | Título | Estado | Prioridad | Componentes |
|-----------|-------|--------|----------|------------|
| NEO-92942 | [Generador de reglas] Filtros predefinidos: opción compartida | Resuelto | Normal | IU/UX PIX |
| NEO-91299 | Interfaz de usuario web: actividad de envío continua | Cerrada | Principal | IU/UX PIX |
| NEO-90130 | Habilitar la carga de archivos OOTB para entregas de notificaciones push multilingües | Cerrada | Importante | ACS a ACC, IU/UX PIX |

### 1.3 AC-UI-25-11-Versión mensual (noviembre de 2025)

| ID de vale | Título | Estado | Prioridad | Componentes |
|-----------|-------|--------|----------|------------|
| NEO-91566 | [IU web] compatible con el seguimiento de CTA en la interfaz de usuario web | Cerrada | Normal | ACS a ACC, IU/UX PIX |
| NEO-91564 | [Interfaz de usuario web] [AEM multilingüe en ACC] Soporte de interfaz de usuario para AEM multilingüe | Cerrada | Normal | ACS a ACC, IU/UX PIX |
| NEO-90183 | [UX/UI] push enriquecida multilingüe - IU | Cerrada | Bloqueador | IU/UX PIX |
| NEO-91567 | [Interfaz de usuario web] Agregar compatibilidad con la función NRT | Resuelto | Normal | ACS a ACC, IU/UX PIX |
| NEO-91563 | API de REST transaccional para enriquecimiento basado en perfiles: IU web | Resuelto | Normal | ACS a ACC, IU/UX PIX |
| NEO-92151 | Mensajería transaccional de enriquecimiento basada en perfiles [UI/UX] - Fase 2 | Resuelto | Principal | ACS a ACC, IU/UX PIX |
| NEO-84916 | [UX/UI]: configure y administre el proceso de aprobación | Resuelto | Importante | IU/UX PIX |

---

## &#x200B;2. Billetes que requieren documentación

### 2.1 ALTA PRIORIDAD: desarrollo activo (AC-UI-26-01)

#### **NEO-86754: prueba A/B**
- **Estado:** En Curso (En Seguimiento)
- **Por qué se necesita documentación:** Nueva característica importante para la experimentación de contenido de correo electrónico con capacidades de prueba A/B
- **DOCAC existente:** DOCAC-13104 (nuevo estado)
- **Ámbito de la documentación:**
   - Creación de experimentos de prueba A/B en envíos
   - Definición de variantes de contenido/entrega
   - Configuración de proporciones de muestra y envío de variantes de prueba
   - Definición de criterios de evaluación
   - Análisis de los resultados del experimento y selección de ganadores
   - Prácticas recomendadas y limitaciones
- **Audiencia de destino:** Usuarios de marketing, administradores de campaña
- **Versión:** 8.9.1, AC-UI-26-01-Monthly
- **Preguntas abiertas:**
   - ¿Estado final de validación de IU/UX?
   - ¿Alguna limitación para los mensajes transaccionales?
   - ¿Integración con la previsualización de contenido preciso?

#### **NEO-80973: disponibilidad de informes dinámicos**
- **Estado:** en curso (listo para revisión)
- **Por qué se necesita documentación:** Expandir el sistema de informes dinámico a todos los usuarios de la interfaz de usuario web (no solo a los clientes de ACS 8.7)
- **DOCAC existente:** DOCAC-11070 (Cerrado), DOCAC-13432 (Resuelto: limitaciones de idioma)
- **Ámbito de la documentación:**
   - Disponibilidad y requisitos de acceso
   - Documentación de idiomas admitidos
   - Limitaciones conocidas frente a informes preexistentes
   - Las métricas en conflicto se muestran con los informes heredados
   - Configuración del entorno de demostración
- **Audiencia de destino:** Todos los usuarios de interfaz de usuario web, analistas
- **Versión:** 8.8.1, AC-UI-26-01-Monthly
- **Preguntas abiertas:**
   - Estado de disponibilidad del entorno de demostración
   - ¿Lista completa de métricas en conflicto con los informes heredados?
   - Matriz de compatibilidad de idiomas

#### **NEO-76126: creación de esquemas**
- **Estado:** En Curso (En Seguimiento)
- **Por qué se necesita documentación:** Característica de administración significativa para la administración del modelo de datos
- **DOCAC existente:** DOCAC-13826 (nuevo estado)
- **Ámbito de la documentación:**
   - Creación de nuevas tablas
   - Ampliación de esquemas existentes
   - Acceso a bases de datos externas
   - Definición de formulario para entidades personalizadas
   - Operaciones de navegación y CRUD
   - Funciones de la fase 3 (creación y ampliación de esquemas): fin de febrero de ETA
- **Audiencia de destino:** Usuarios administradores, administradores técnicos
- **Versión:** AC-UI-26-01-Monthly
- **Fecha de vencimiento:** 28 de febrero de 2026
- **Preguntas abiertas:**
   - ¿Cuándo se completará la Fase 2 para la activación de FF?
   - ¿Fase 3 de confirmación del plazo de entrega?
   - Requisitos de configuración del entorno

#### **NEO-93487: Proceso de cálculo de programación de entregas (H&amp;M)**
- **Estado:** Nuevo
- **Por qué se necesita documentación:** Escalación crítica del cliente: horario de entrega basado en zona horaria
- **DOCAC existente:** Ninguno identificado
- **Ámbito de la documentación:**
   - Programación de entregas según la zona horaria del usuario
   - Uso de fórmulas calculadas para regiones de varias zonas horarias
   - Ejemplos de configuración (por ejemplo, Estados Unidos con varias zonas horarias)
   - Prácticas recomendadas para campañas globales
   - Comparación de funciones con ACS
- **Audiencia de destino:** Administradores de campañas, Usuarios de marketing
- **Impacto en el cliente:** H&amp;M (más de 50 mercados)
- **Versión:** 8.9.1, AC-UI-26-01-Monthly, 8.8.2.NEO-90300
- **Preguntas abiertas:**
   - ¿Demostración de la función programada con PM?
   - ¿Especificaciones funcionales completas disponibles?
   - ¿Moquetas de IU finalizadas?

#### **NEO-86753: integración de AEM para Live Copies/Copias de idioma**
- **Estado:** Nuevo
- **Por qué se necesita documentación:** función específica de Microsoft para la administración de contenido multilingüe
- **DOCAC existente:** DOCAC-13829 (resuelto)
- **Ámbito de la documentación:**
   - Exploración de plantillas de entrega de AEM
   - Creación de Live Copies
   - Creación de variantes de contenido de copias de idioma
   - Flujo de trabajo y prácticas recomendadas
   - Requisitos de configuración de integración
- **Audiencia objetivo:** Usuarios de marketing que trabajan con equipos de AEM y Microsoft
- **Versión:** AC-UI-26-01-Monthly
- **Prioridad:** Bloqueador
- **Preguntas abiertas:**
   - Trabajo transferido al equipo de Himanshu - ¿estado actual?
   - ¿Cronología de finalización?

#### **NEO-92668: Web Analytics**
- **Estado:** Nuevo (En seguimiento)
- **Por qué se necesita documentación:** Configuración de cuenta externa para la integración de análisis web
- **DOCAC existente:** Ninguno identificado
- **Ámbito de la documentación:**
   - Creación de cuenta externa de Web Analytics
   - Parámetros de configuración
   - Integración con el seguimiento de envíos
   - Funcionalidades de informes
- **Audiencia objetivo:** Usuarios administradores, analistas de marketing
- **Versión:** AC-UI-26-01-Monthly
- **Preguntas abiertas:**
   - Estado de disponibilidad del entorno?
   - ¿Pasos de configuración necesarios?

### 2.2 PRIORIDAD DE MEDIUM: Entregas recientes (AC-UI-25-11)

#### **NEO-90183: inserción enriquecida multilingüe**
- **Estado:** Cerrado
- **Por qué se necesita documentación:** Nueva capacidad para push enriquecidas con iOS/Android con soporte multilingüe
- **DOCAC existente:** DOCAC-13565 (nuevo estado)
- **Ámbito de la documentación:**
   - Configuración de notificaciones push enriquecidas para iOS y Android
   - Variantes de contenido multilingües
   - Selección de plantilla
   - Campos adicionales para contenido enriquecido
   - Funcionalidades de carga de archivos
   - Prácticas recomendadas y limitaciones
- **Audiencia de destino:** Usuarios de marketing, administradores de canales móviles
- **Versión:** AC-UI-25-11-Monthly, 8.8.2
- **Cliente:** H&amp;M

#### **NEO-84916: administración del proceso de aprobación**
- **Estado:** Resuelto
- **Por qué se necesita documentación:** Función principal de flujo de trabajo para la validación de envíos
- **DOCAC existente:** DOCAC-13827 (nuevo estado)
- **Ámbito de la documentación:**
   - Configuración de operadores de aprobación en envíos/campañas
   - Configuración de aprobación de contenido
   - Configuración de aprobación de destino
   - Administración de flujos de trabajo de aprobación entre canales (correo electrónico, SMS, push para iOS/Android, correo directo, centro de llamadas)
   - Aceptar/rechazar procesos
   - Informes de aprobación y seguimiento
- **Audiencia de destino:** Administradores de campañas, usuarios administradores
- **Versión:** AC-UI-25-11-Monthly
- **Prioridad:** Crítico
- **Cliente:** Pierre Fabre

#### **NEO-91299: Actividad de envío continuo**
- **Estado:** Cerrado
- **Por qué se necesita documentación:** Nueva actividad de flujo de trabajo para escenarios de envío recurrentes
- **DOCAC existente:** DOCAC-13586 (Nuevo estado), DOCAC-13808 (Cerrado: ayuda contextual)
- **Ámbito de la documentación:**
   - Configuración de actividad de envío continuo
   - Requisitos del selector de plantillas de envío
   - Tratamiento de errores de procesos
   - Integración de flujo de trabajo
   - Casos de uso y ejemplos
- **Audiencia de destino:** usuarios técnicos, diseñadores de flujo de trabajo
- **Versión:** AC-UI-26.01.06

#### **NEO-90130: carga de archivos push multilingües (H&amp;M)**
- **Estado:** Cerrado
- **Por qué se necesita documentación:** OOTB ofrece paridad con ACS para push multilingüe basado en archivos
- **DOCAC existente:** DOCAC-13606 (nuevo estado)
- **Ámbito de la documentación:**
   - Carga de archivo CSV para notificaciones push multilingües
   - Especificaciones del formato de archivo
   - Asignación de campos
   - Configuraciones específicas de iOS y Android
   - Tratamiento del tipo de mensaje de datos
   - Solución de problemas y problemas conocidos
- **Audiencia de destino:** Usuarios de marketing, administradores de campaña
- **Versión:** AC-UI-25-10-Monthly, AC-UI-25.11.03
- **Prioridad:** Crítico
- **Cliente:** H&amp;M (migración de ACS a ACC)

#### **NEO-92942: filtros predefinidos - Opción compartida**
- **Estado:** Resuelto
- **Por qué se necesita documentación:** Mejora de la funcionalidad del generador de reglas
- **DOCAC existente:** DOCAC-13697 (Estado de revisión de código), DOCAC-13522 (Cerrado: asistente)
- **Ámbito de la documentación:**
   - Opción compartida para filtros predefinidos
   - Administración de la visibilidad del filtro con otros operadores
   - Comportamientos de ACC frente a Brand Recorrido
   - Administración de listas de filtros
- **Audiencia de destino:** Todos los usuarios, diseñadores de consultas
- **Versión:** Versión principal
- **FF:** enable-query-filter-shared

### 2.3 PRIORIDAD BAJA: mejora del editor de contenido

#### **NEO-88838: variables de tema en fragmentos**
- **Estado:** Nuevo (En espera)
- **Por qué se necesita documentación:** Funcionalidad del tema de Designer de correo electrónico
- **DOCAC existente:** DOCAC-12941 (nuevo estado)
- **Ámbito de la documentación:**
   - Uso de variables de temática en fragmentos de correo electrónico
   - Configuración del tema
   - Administración de variables
   - Prácticas recomendadas
- **Audiencia de destino:** Diseñadores de correo electrónico, Usuarios de marketing
- **Versión:** AC-UI-26-01-Monthly
- **Nota:** La característica está en espera mientras se realiza una revisión del lado de Acrite

---

## &#x200B;3. Billetes que NO requieren documentación

### 3.1 Cancelado/Ya no aplicable

| ID de vale | Título | Motivo |
|-----------|-------|--------|
| NEO-91566 | Seguimiento de CTA en webui | No se esperaba ningún trabajo de IU; información pendiente de MSFT |
| NEO-91564 | Compatibilidad con IU multilingüe de AEM | Trabajo de IU administrado por un equipo diferente |
| NEO-91567 | Compatibilidad con funciones NRT | Sin impacto en la IU web; especificaciones disponibles |
| NEO-91563 | API de REST transaccional | No funciona la IU web; actualización de instancia pendiente |
| NEO-92151 | Enriquecimiento de perfil, fase 2 | La historia no tiene tareas; marcada como ya no se aplica |

### 3.2 Marcador de posición/Tickets de seguimiento

| ID de vale | Título | Motivo |
|-----------|-------|--------|
| NEO-92400 | Mejoras de la versión, 26 de enero | Marcador de posición para rastrear la finalización de mejoras |

---

## &#x200B;4. Billetes DOCAC propuestos

### 4.1 Se necesitan nuevas entradas DOCAC

#### **DOCAC-XXXX: Programación de entregas con compatibilidad con zona horaria**
**vale principal:** NEO-93487
**Prioridad:** Crítico
**Versión de Target:** AC-UI-26-01-Monthly
**Descripción:**
Documente el nuevo proceso de cálculo de programación de entregas que habilita la programación de entregas basada en zona horaria similar a la funcionalidad ACS. Esta función permite a los especialistas en marketing enviar comunicaciones basadas en las zonas horarias de los destinatarios mediante fórmulas calculadas, lo que resulta especialmente importante en mercados con varias zonas horarias como EE. UU.

**Ámbito:**
- Guía de configuración para programación basada en huso horario
- Ejemplos de fórmulas calculadas
- Situaciones de mercado de varias zonas horarias
- Guía de migración de ACS
- Prácticas recomendadas y limitaciones

**Cliente:** H&amp;M (crítico para la migración de ACS a ACC)

#### **DOCAC-XXXX: Configuración de cuenta externa de Web Analytics**
**vale principal:** NEO-92668
**Prioridad:** Normal
**Versión de Target:** AC-UI-26-01-Monthly
**Descripción:**
Documente la configuración y el uso del tipo de cuenta externa Web Analytics en la interfaz de usuario web.

**Ámbito:**
- Pasos de creación de cuenta externa
- Parámetros de configuración
- Integración con el seguimiento de envíos
- Funcionalidades de informes
- Solución de problemas

---

### 4.2 Entradas DOCAC existentes para actualizar

#### **DOCAC-13104: prueba A/B**
**Estado:** Nuevo
**Ticket Principal:** NEO-86754
**Acción necesaria:** Iniciar documentación: característica en desarrollo activo
**Envío estimado:** febrero de 2026 (pendiente de finalización del desarrollo)

#### **DOCAC-11070 Y DOCAC-13432: Informes dinámicos**
**Estado:** cerrado/resuelto
**Ticket Principal:** NEO-80973
**Acción necesaria:**
- Actualización de la disponibilidad general (no solo 8.7)
- Documentar métricas en conflicto con informes heredados
- Verificar la documentación de asistencia lingüística

#### **DOCAC-13826: creación de esquemas**
**Estado:** Nuevo
**Ticket Principal:** NEO-76126
**Acción necesaria:**
- Documentación de la fase 2 (navegación + CRUD + definición del formulario)
- Preparación para la fase 3 (creación/ampliación de esquemas): fin de febrero de ETA

#### **DOCAC-13829: AEM Live Copies/Copias de idioma**
**Estado:** Resuelto
**Ticket Principal:** NEO-86753
**Acción necesaria:** Compruebe el estado actual y actualice según sea necesario

#### **DOCAC-13565: Inserción enriquecida multilingüe**
**Estado:** Nuevo
**Ticket Principal:** NEO-90183
**Acción necesaria:** Documentación completa; función entregada en noviembre de 2025

#### **DOCAC-13827: proceso de aprobación**
**Estado:** Nuevo
**Ticket Principal:** NEO-84916
**Acción necesaria:** Documentación completa; función entregada en noviembre de 2025

#### **DOCAC-13586 y DOCAC-13808: Entrega continua**
**Estado:** Nuevo/Cerrado
**Ticket Principal:** NEO-91299
**Acción necesaria:** Documentación principal completa (13586); función entregada

#### **DOCAC-13606: Carga de archivos push multilingües**
**Estado:** Nuevo
**Ticket Principal:** NEO-90130
**Acción necesaria:** Documentación completa - función entregada

#### **DOCAC-13697 y DOCAC-13522: filtros predefinidos compartidos**
**Estado:** revisión de código/cerrado
**Ticket Principal:** NEO-92942
**Acción necesaria:** finalizar documentación (13697)

#### **DOCAC-12941: temas en el correo electrónico Designer**
**Estado:** Nuevo
**Ticket Principal:** NEO-88838
**Acción necesaria:** En espera con revisión pendiente de la función

---

## &#x200B;5. Preguntas abiertas e información que falta

### 5.1 Por función

#### **Prueba A/B (NEO-86754)**
- [ ] ¿Cuál es el estado final de validación de IU/UX?
- [ ] ¿Existen limitaciones específicas para los mensajes transaccionales?
- [ ] ¿Cómo se integra esto con la vista previa de contenido Acrite (bloqueo de NEO-92516)?
- [ ] ¿Cuáles son las capacidades de simular/previsualizar dentro de cada variante?

#### **Informes dinámicos (NEO-80973)**
- [ ] ¿Cuál es el estado de la reactivación del entorno de demostración?
- [ ] ¿Lista completa de métricas en conflicto con los informes heredados?
- [ ] ¿Matriz detallada de compatibilidad con idiomas?
- [ ] ¿Comparación de rendimiento con informes heredados?

#### **Creación de esquemas (NEO-76126)**
- [ ] ¿Cuándo se activará la Fase 2 FF?
- [ ] ¿ETA confirmado para la fase 3 (crear/ampliar esquemas)?
- [ ] ¿Cuáles son los requisitos de configuración del entorno?
- [ ] ¿Alguna limitación o funcionalidad de la consola de cliente?

#### **Programación de entrega (NEO-93487)**
- [ ] ¿Está programada la demostración de la función con PM?
- [ ] ¿Se encuentran disponibles las especificaciones funcionales completas?
- [ ¿Finalizaron y revisaron ] pruebas de interfaz de usuario?
- [ ] ¿Cuál es la sintaxis/estructura exacta de la fórmula?

#### **AEM Live/Copias de idioma (NEO-86753)**
- [ ] ¿Cuál es el estado actual del equipo de Himanshu?
- [ ] ¿Se actualizó el calendario de envíos?
- [ ] ¿Alguna dependencia de la versión de AEM?

#### **Análisis web (NEO-92668)**
- [ ] ¿Qué es el estado de disponibilidad del entorno?
- [ ] ¿Requisitos de configuración completos?
- [ ] ¿Plataformas de análisis compatibles?

#### **Variables de tema en fragmentos (NEO-88838)**
- [ ] ¿Cuándo volverá Acrite a utilizar la función?
- [ ] ¿Está aún planificado para AC-UI-26-01?

### 5.2 Por versión

#### **AC-UI-26-01-Monthly (enero de 2026)**
- [ ] ¿Confirmación oficial de la fecha de lanzamiento?
- [ ] ¿Fecha de congelación de característica?
- [ ] ¿Cronología de finalización de prueba?
- [ ] ¿Plazo de entrega de documentación?

#### **Características entregadas en noviembre de 2025**
- [ ] ¿Qué características ya están activadas en la producción?
- [ ] ¿Se detectaron problemas o limitaciones conocidos después del lanzamiento?
- [ ] comentarios del cliente recibidos?

### 5.3 Proceso de documentación

- [ ] ¿Quiénes son los EM para cada característica?
- [ ] ¿Qué es el proceso de revisión de documentación?
- [ ] ¿Idioma de documentación de destino (solo EN o multilingüe)?
- [ ] ¿Requisitos de plataforma/formato de documentación?
- [ ¿Disponibilidad de entornos de demostración y capturas de pantalla de ]?

---

## &#x200B;6. Impacto y escalaciones para el cliente

### 6.1 Tickets de cliente críticos

| Cliente | Ticket | Función | Impacto |
|----------|--------|---------|--------|
| **H&amp;M** | NEO-93487 | Programación de envíos | Más de 50 mercados; requisitos de entrega de varias zonas horarias; bloqueador de migración de ACS a ACC |
| **H&amp;M** | NEO-90130 | Carga de archivo push multilingüe | Esencial para la migración de ACS a ACC; reduce los costes operativos |
| **Pierre Fabre** | NEO-84916 | Proceso de aprobación | Requisitos normativos y de flujo de trabajo |

### 6.2 Funciones específicas de Microsoft

| Ticket | Función | Estado | Notas |
|--------|---------|--------|-------|
| NEO-86753 | AEM Live/Copies de idioma | Nuevo | Muy utilizado por Microsoft |
| NEO-91566 | Seguimiento de CTA | Cerrado/Ya No Se Aplica | Información pendiente de MSFT |
| NEO-91567 | Función NRT | Resuelto/sin impacto en la IU | Nueva función ACS para MSFT |

---

## &#x200B;7. Prioridades de la documentación y calendario

### 7.1 Acción inmediata requerida (enero de 2026)

**ALTA PRIORIDAD - Entregada pero no documentada:**
1. **NEO-90183** - Inserción enriquecida multilingüe (DOCAC-13565)
2. **NEO-84916** - Proceso de aprobación (DOCAC-13827)
3. **NEO-91299** - Entrega continua (DOCAC-13586)
4. **NEO-90130** - Carga de archivos push multilingües (DOCAC-13606)

### 7.2 En curso: desarrollo en curso (febrero-marzo de 2026)

**PRIORIDAD CRÍTICA:**
1. **NEO-86754** - Prueba A/B (DOCAC-13104) - Vencimiento: febrero de 2026
2. **NEO-76126** - Creación de esquemas (DOCAC-13826) - Fase 2: Feb, Fase 3: End Feb
3. **NEO-93487** - Programación de entrega (NUEVO DOCAC) - Escalación crítica del cliente

**PRIORIDAD NORMAL:**
1. **NEO-80973** - Informes dinámicos (actualizar DOCAC-11070)
2. **NEO-92668** - Web Analytics (NUEVO DOCAC)
3. **NEO-86753** - AEM Live/Copias de idioma (DOCAC-13829)

### 7.3 En espera/Futuro

1. **NEO-88838** - Variables de tema (DOCAC-12941) - Revisión precisa pendiente

---

## &#x200B;8. Pasos siguientes

### 8.1 Acciones del equipo de documentación
1. **Priorizar las funciones entregadas** sin documentación (sección 7.1)
2. **Crear nuevos tickets DOCAC** para NEO-93487 y NEO-92668
3. **Actualizar tickets DOCAC** existentes con ámbito detallado (Sección 4.2)
4. **Programar entrevistas de EM** para pruebas A/B, esquemas y programación de envíos
5. **Recopilar capturas de pantalla** y preparar entornos de demostración
6. **Revisar y finalizar** limitaciones de idioma para el sistema de informes dinámico

### 8.2 Recopilación de información
1. **Póngase en contacto con posibles clientes de ingeniería** para obtener actualizaciones de estado sobre:
   - Validación final de la prueba A/B
   - Esquemas Fase 2/3 cronología
   - Especificaciones del programa de entregas
2. **Programar demostraciones de características** con la administración de productos
3. **Recopilar comentarios de clientes** de H&amp;M y Pierre Fabre
4. **Verificar la disponibilidad del entorno** para análisis web y creación de informes dinámica

### 8.3 Coordinación
1. **Sincronizar con el equipo de Himanshu** en AEM Live/Copies de idioma
2. **Coordinar con el equipo Acrite** el estado de las variables del tema
3. **Realizar seguimiento de las características específicas de Microsoft** con el equipo de la cuenta

---

## Historial de documentos

| Fecha | Autor | Versión | Cambios |
|------|--------|---------|---------|
| 12-01-2026 | Asistente de IA | 1,0 | Análisis inicial de consultas Jira |

---

## Apéndice: Consultas Jira analizadas

1. `project = NEO AND fixVersion = AC-UI-26-01-Monthly and type = story order by status`
2. `issueFunction in linkedIssuesOf('key=NEO-92400', 'is implemented by')`
3. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and type = story order by status`
4. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and fixVersion != 8.8.2 and type = story order by status`

**Resultados totales:** 19 tickets únicos analizados

