---
product: campaign
title: Entregas
description: Descubra más información sobre los flujos de trabajo Entregas
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 97%
---

# Entregas{#deliveries}



Los flujos de trabajo detallados a continuación se instalan con el módulo **Envíos** de forma predeterminada.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>Nombre interno</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reporting aggregates</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza los agregados que se utilizan en los informes. Se activa cada día a la 2 de la mañana de forma predeterminada.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturación</span> <br /> </td> 
   <td> <span class="uicontrol">facturación</span> <br /> </td> 
   <td> Este flujo de trabajo envía el informe de actividad del sistema al operador “facturación” por correo electrónico. De forma predeterminada, se activa el día 25 de cada mes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Alias cleansing</span> <br /> </td> 
   <td> <span class="uicontrol">aliasCleansing</span> <br /> </td> 
   <td> Este flujo de trabajo estandariza los valores de enumeración. Se activa cada día a las 3 de la mañana de forma predeterminada.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update for deliverability</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Este flujo de trabajo le permite crear la lista de reglas de las calificaciones del correo rechazado, así como la lista de dominios y los MX de la plataforma. Este flujo de trabajo solo funciona si el puerto HTTPS está abierto. Estas listas no se actualizan a menos que se instale el módulo Deliverability.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> <p>Este flujo de trabajo es el del mantenimiento de la base de datos: realiza diferentes cálculos en las estadísticas y procesos y elimina los datos obsoletos de la base de datos según la configuración definida en el asistente de implementación. Se activa cada día a las 4 a. m. de manera predeterminada.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpieza de flujos de trabajo en pausa</span> <br /> </td> 
   <td> <span class="uicontrol">cleanupPausedWorkflows</span> <br /> </td> 
   <td> <p>Este flujo de trabajo analiza los flujos de trabajo en pausa con opción de gravedad definida en normal y activa las advertencias y notificaciones cuando dichos flujos llevan demasiado tiempo en pausa. Tras un mes, los flujos de trabajo técnicos en pausa se detienen de manera incondicional. De forma predeterminada, se activa todos los lunes a las 5 a. m.</p> <p>Para obtener más información, consulte Administración de flujos de trabajo en pausa </a>.</p></td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Notificación de oferta</span> <br /> </td> 
   <td> <span class="uicontrol">offerMgt</span> <br /> </td> 
   <td> Este flujo de trabajo implementa las ofertas aprobadas en el entorno en línea, así como todas las categorías incluidas en el catálogo de ofertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsión</span> <br /> </td> 
   <td> <span class="uicontrol">previsión</span> <br /> </td> 
   <td> Este flujo de trabajo analiza las entregadas guardadas en el calendario provisional (crea registros provisionales). Se activa cada día a la 1 de la mañana de forma predeterminada.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Seguimiento</span> <br /> </td> 
   <td> <span class="uicontrol">tracking</span> <br /> </td> 
   <td> Este flujo de trabajo realiza la recuperación y la consolidación de la información de seguimiento. También garantiza que se recalculen las estadísticas de seguimiento y envío, especialmente las utilizadas por los flujos de trabajo de archivado del Centro de mensajes. De forma predeterminada se activa una vez cada hora. <br /> </td> 
  </tr> 
 </tbody> 
</table>

