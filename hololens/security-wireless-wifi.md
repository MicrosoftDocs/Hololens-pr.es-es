---
title: Inalámbrico y Wi-Fi
description: Inalámbrico y Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, inalámbrico, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865771"
---
# Inalámbrico y Wi-Fi

La conectividad de LAN inalámbrica con HoloLens 2 es compatible con una gran variedad de los últimos estándares de seguridad Wi-Fi, como:
  * WPA2 (acceso protegido Wi-Fi 2)  
  * TEAP (túnel, protocolo de autenticación extensible)  
  * DEBE (cifrado inalámbrico oportunista)

TEAP, la próxima generación de la autenticación de red empresarial, ofrece la posibilidad de concatenar varias credenciales de forma segura en una sola transacción.  Esto permite a los administradores exigir una actitud de seguridad mayor: una que necesita identidades válidas para el equipo y el usuario durante la misma transacción de autenticación.

HoloLens 2 tiene protocolos inalámbricos y Wi-Fi modernos que permiten a los clientes con la asistencia máxima. La radio de HoloLens 2 es una solución de Qualcomm WCN3990 que ofrece una experiencia de radio Premium. La Wi-Fi es compatible con la 802,11 AC/n. El rango de frecuencias no es configurable por el usuario y depende del país de uso. En los Estados Unidos, Wi-Fi usa canales de 2,4 GHz (1-11) y de 5 GHz (36-64, 100-165). El usuario o el dispositivo no pueden hacer las listas de permitidos y denegación para frecuencias específicas. El núcleo SIC de 5.0 tiene una antena dedicada de 2.4 GHz para Bluetooth que no se comparte con Wi-Fi. La pila de software de HoloLens 2 es compatible con varios protocolos y perfiles, como HID, HOGP, A2DP y GATT. 

Los administradores de TI pueden: 
  * Permitir o restringir el [Acceso a Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)
  * Establezca [nombres de dispositivo Bluetooth locales](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)
  * Permita que los[dispositivos sean detectables](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)
  * Permitir o denegar [conexiones Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 
  * Permitir o denegar el [de conexión a Wi-Fi fuera de las redes instaladas en servidor MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)
