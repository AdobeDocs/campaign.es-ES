---
product: campaign
title: Ejemplo de extensión
description: Ejemplo de extensión
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: advanced-parameters
exl-id: d4acf99b-cef4-48f7-b4cd-c032ec12592f
TQID: 'https://experienceleague.adobe.com/TQZaYrJop03HAw47XPFqgmoxb073iC-xztTp-f-5dEk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 85%
---
# Ejemplo de extensión{#extension-example}



En el caso de un contacto entrante (centro de llamadas o sitio web), las ofertas más relevantes se sugieren a un contacto determinado mediante un conjunto de reglas de elegibilidad. Para mejorar los criterios de idoneidad de sus ofertas, amplíe el esquema **nms:interaction**.

* Para añadir un un nuevo contexto de interacción, amplíe el esquema **nms:interaction** y cree tantos elementos **atributo** como sea necesario en el esquema.

  En el siguiente ejemplo, los criterios añadidos son el código de país y la última página visitada.

  ![Se agregó el esquema de datos de interacciones con el código de país y los atributos de la última página visitada.](assets/s_ncs_configuration_offer_schemas.png)

* A continuación, se puede utilizar los atributos creados previamente al realizar la definición de criterios de idoneidad.

  En el ejemplo siguiente, se puede crear criterios de idoneidad para mostrar una oferta en función del país del usuario o de la última página web que visitó.

  ![Editor de consultas de idoneidad con los campos Código de país y Última interacción de página visitada seleccionables como criterios.](assets/s_ncs_configuration_offer_context.png)

* Al configurar las llamadas SOAP, inserte el elemento XML **context** para hacer referencia a la información contextual añadida en el esquema de interacción. Para obtener más información, consulte [Integración mediante SOAP (lado del servidor)](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/offers/inbound/interaction-integration){target="_blank"} (documentación de Campaign v8).
