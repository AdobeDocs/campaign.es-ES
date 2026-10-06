---
product: campaign
title: 'Nota técnica: cifrado y descifrado asimétricos en Adobe Campaign'
description: 'Nota técnica: cifrado y descifrado asimétricos en Adobe Campaign'
hide: true
exl-id: 6ee8b05b-2a46-4adf-a036-82fdd4809d0d
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 10%
---
# Nota técnica: cifrado y descifrado asimétricos en Adobe Campaign {#asymetric-encryption}

La criptografía de clave pública, o criptografía asimétrica, es el campo de los sistemas criptográficos que utilizan pares de claves relacionadas. Cada par de claves consta de una **clave pública** y una **clave privada** correspondiente.

* La **clave pública** se comparte abiertamente y se usa para cifrar datos.

* La **clave privada** se mantiene secreta y se usa para descifrar datos.

Este método garantiza que, aunque alguien tenga la clave pública, no pueda descifrar el mensaje sin la clave privada. Proporciona funciones de seguridad clave como confidencialidad, autenticación e integridad.

A partir de la versión 8.8.3 de Adobe Campaign, se están añadiendo dos nuevas funciones de Javascript para el cifrado y el descifrado:

* Cifrado con clave pública: `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* Descifrado con clave privada: `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


Ejemplo:

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**Recursos adicionales**

* [Introducción a  [!DNL Campaign] API](https://experienceleague.adobe.com/es/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Documentación de JSAPI de Campaign](https://experienceleague.adobe.com/es/tools/campaign-api){target="_blank"}
