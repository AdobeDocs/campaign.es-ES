---
product: campaign
title: Configuración de reglas de control
description: Obtenga información sobre cómo configurar reglas de control
feature: Typology Rules
version: Campaign v8, Campaign Classic v7
exl-id: 79e442ea-f856-41bf-b065-25cb2ad2c65b
TQID: 'https://experienceleague.adobe.com/xluD-4nygREOMWZyFT6OrenJvfvFVWTVf7i6-ZoYfTI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 75%
---
# Reglas de control{#control-rules}

Las reglas de control permiten garantizar la validez y calidad de los mensajes antes de la entrega: visualización de caracteres, tamaño de SMS, formato de dirección, etc.

Un conjunto de reglas predeterminadas permite realizar comprobaciones habituales. Estas comprobaciones (que aparecen en negrita en la interfaz) son:

* **[!UICONTROL Object approval]** (correo electrónico): comprueba que el objeto de remitente y la dirección no contienen caracteres especiales que podrían causar problemas en determinados agentes de correo.
* **[!UICONTROL URL label approval]** (correo electrónico): comprueba que cada URL de seguimiento tiene una etiqueta.
* **[!UICONTROL URL approval]** (correo electrónico): comprueba las URL de seguimiento (presencia del carácter “&amp;”).
* **[!UICONTROL Message size approval]** (móvil): comprueba el tamaño de los mensajes SMS.
* **[!UICONTROL Validity period check]** (correo electrónico): comprueba que el periodo de validez de la entrega sea lo suficientemente largo como para enviar todos los mensajes.
* **[!UICONTROL Proof size check]** (todos los canales): genera un mensaje de error si la población de destino de prueba supera los 100 destinatarios.
* **[!UICONTROL Wave scheduling check]** (correo electrónico): comprueba que la última tanda de envíos está programada para iniciarse antes del final del periodo de validez, si la entrega se divide en varias tandas.
* **[!UICONTROL Unsubscription link approval]** (correo electrónico): comprueba la presencia de al menos una URL de baja (exclusión) en cada contenido (HTML y texto).

## Creación de una regla de control {#create-a-control-rule}

Es posible crear nuevas reglas de control para adaptarlas a sus necesidades. Para ello, cree una regla de tipología de **[!UICONTROL Control]** e introduzca la fórmula de control en SQL en la pestaña **[!UICONTROL Code]**.

**Ejemplo:**

En el siguiente ejemplo creamos una regla para evitar que una oferta SMS se envíe a más de 100 destinatarios. Esta regla se vincula a una tipología de campaña y luego a las entregas de SMS para los que la oferta relacionada está disponible.

Siga estos pasos:

1. Cree una regla de tipología de **[!UICONTROL Control]**. Seleccione un nivel de alerta **[!UICONTROL Warning]**.

   ![Cuadro de diálogo de creación de reglas de tipología, pestaña General: Tipo de regla de control, canal SMS, lista desplegable Nivel con advertencia resaltada.](assets/campaign_opt_create_control_01.png)

1. En la pestaña **[!UICONTROL Code]**, introduzca la secuencia de comandos para aplicar el umbral deseado, como se muestra a continuación:

   ![Pestaña Código de regla de tipología con el script que registra una advertencia cuando el destino de la entrega supera los 100 contactos.](assets/campaign_opt_create_control_02.png)

   Esta secuencia de comandos activa una advertencia si la entrega supera los 100 destinatarios:

   ```
   if( delivery.FCP == false && delivery.properties.toDeliver > 100 ) { logWarning("Significant number of SMS to deliver (" + delivery.properties.toDeliver + "). Please make sure the target is correct.") return false; } return true
   ```

1. Vincule esta regla a una tipología de campaña y haga referencia a la tipología en la entrega de SMS correspondiente.

   ![Propiedades de entrega, pestaña Tipología: la lista desplegable Tipología incluye Móvil (máximo 100) entre las tipologías disponibles.](assets/campaign_opt_create_control_03.png)

1. Durante el análisis de envío, se aplica la regla y se crea una advertencia si procede.

   ![Registro de análisis de envío que muestra una advertencia de que la regla +100 mensajes detectó un problema; Confirmar envío está disponible.](assets/campaign_opt_create_control_04.png)

   Sin embargo, la entrega está listo para realizarse.

   Si aumenta el nivel de alerta, esto impide que se inicie la entrega.

   ![Ficha General de regla de tipología con la lista desplegable Nivel abierta y Error seleccionado en lugar de Advertencia.](assets/campaign_opt_create_control_05.png)

   Al final del análisis, el botón **[!UICONTROL Confirm delivery]** deja de estar disponible.

   ![El registro de análisis de envío termina en un error, con el botón Confirmar envío deshabilitado.](assets/campaign_opt_create_control_06.png)
