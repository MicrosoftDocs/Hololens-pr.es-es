---
title: Conexión a redes de telefonía móvil y 5G
description: Conexión a redes de telefonía móvil desde los dispositivos HoloLens de realidad mixta.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635847"
---
# <a name="connect-to-cellular-and-5g"></a>Conexión a redes de telefonía móvil y 5G

HoloLens 2 admite dos métodos para conectarse a las redes de telefonía móvil y 5G:

- Una red WiFi ad hoc proporcionada por el dispositivo de telefonía móvil, más frecuentemente conocida como "punto de acceso"
- Compatibilidad limitada con dispositivos USB-C con tethering

## <a name="hotspot-wifi"></a>Punto de acceso (WiFi)

La mayoría de las necesidades de conectividad de la red de telefonía móvil pueden satisfacerse con un punto de acceso. La red WiFi de HoloLens 2 es compatible con 802.11ac, que puede proporcionar el ancho de banda y los requisitos de latencia necesarios para la mayoría de los casos de uso. Además, la red WiFi no necesita cable y ofrece compatibilidad con la mayoría de los dispositivos de red de telefonía móvil.

### <a name="connecting-to-a-hotspot"></a>Conexión a un punto de acceso

1. Consulte el manual de su dispositivo para saber cómo habilitar el modo de punto de acceso.
1. Habilite el modo de punto de acceso, proporcione un nombre para la red y una contraseña conocida.
1. En la configuración de red de HoloLens 2, localice la red WiFi que creó en el paso 2 y únase a ella.

## <a name="usb-c-tethering"></a>Tethering USB-C

El tethering USB-C puede ofrecer una latencia inferior para las cargas de trabajo avanzadas que lo necesiten. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), por ejemplo, puede beneficiarse del tethering. Tenga en cuenta que el tethering requiere un cable entre el dispositivo de red de telefonía móvil y HoloLens, y que solo es compatible con un número limitado de dispositivos.

### <a name="usb-c-compatibility"></a>Compatibilidad con USB-C

Un número limitado de dispositivos que se presentan a sí mismos como adaptadores de ethernet pueden usarse con Windows Holographic versión 2004 y posteriores.

Los dispositivos que no se presentan a sí mismos como adaptadores de ethernet deben admitir el controlador genérico de Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-). Sin embargo, solo un número limitado de esos dispositivos son compatibles con HoloLens 2. Consulte al fabricante del dispositivo para obtener más información sobre si es compatible con el controlador genérico de Microsoft RNDIS.

No se admiten dispositivos que no sean compatibles con RNDIS o que necesiten instalar un controlador o una aplicación.

Aunque Microsoft no mantiene ninguna lista de dispositivos compatibles, puede consultar una [entrada](https://aka.ms/HLCommunityCell) en la comunidad sobre el tema.

### <a name="connecting-to-a-tethered-device"></a>Conexión a un dispositivo con tethering

1. Consulte el manual de su dispositivo para saber cómo habilitar el uso compartido de datos por USB. Esta configuración se suele conocer como "tethering USB", "uso compartido de datos" o "módem USB".
1. Habilite el uso compartido de datos por USB.
1. Conecte el dispositivo al puerto USB-C de HoloLens.
1. En la configuración de red de HoloLens 2, el dispositivo aparecerá automáticamente como una conexión a Ethernet.
