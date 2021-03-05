---
title: Conectar a redes de telefonía móvil y 5G
description: Conectarse a redes de telefonía móvil desde sus dispositivos de realidad mixta de HoloLens.
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
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385651"
---
# <a name="connect-to-cellular-and-5g"></a>Conectar a redes de telefonía móvil y 5G

HoloLens 2 admite dos métodos para conectarse a las redes de telefonía móvil y 5G:

- Una red WiFi ad hoc proporcionada por el dispositivo de telefonía móvil, más frecuentemente conocida como "Punto de acceso"
- Compatibilidad limitada con dispositivos USB-C anclados a la red

## <a name="hotspot-wifi"></a>Punto de acceso (WiFi)

La mayoría de las necesidades de conectividad de la red de telefonía móvil pueden satisfacerse con un punto de conexión. HoloLens 2 WiFi es compatible con 802.11ac, el cual proporciona el ancho de banda y los requisitos de latencia necesarios para la mayoría de los casos de uso. Además, el WiFi no necesita cable y ofrece compatibilidad con la mayoría de los dispositivos de red de telefonía móvil.

### <a name="connecting-to-a-hotspot"></a>Conectar a un punto de acceso

1. Consulte el manual de su dispositivo para saber cómo habilitar el modo de punto de acceso.
1. Habilitar el modo de punto de acceso, proporcionar un nombre para la red y una contraseña conocida.
1. En la configuración de red de HoloLens 2, localice la red WiFi que creó en el paso 2 y únase a ella.

## <a name="usb-c-tethering"></a>Anclado de red USB-C

El anclado de red con USB-C proporciona una latencia inferior para las cargas de trabajo avanzadas que lo necesiten. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), por ejemplo, puede beneficiarse del anclado de red. Tenga en cuenta que el anclado de red requiere un cable entre el dispositivo de red de telefonía móvil y HoloLens, y que solo es compatible con un número limitado de dispositivos.

### <a name="usb-c-compatibility"></a>Compatibilidad con USB-C

Los dispositivos que se presentan por sí solo como adaptadores de ethernet pueden usarse con Windows Holographic versión 2004 y posteriores.

Los dispositivos que no se presenten por sí solos como adaptadores de ethernet deben ser compatibles con el controlador genérico de Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-). Consulte al fabricante del dispositivo para obtener más información sobre si es compatible con el controlador genérico de Microsoft RNDIS.

No se admiten dispositivos que no sean compatibles con RNDIS o que necesiten instalar un controlador o una aplicación.

Aunque Microsoft no mantiene ninguna lista de dispositivos compatibles, puede encontrar una discusión de la comunidad sobre el tema [aquí](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Conectarse a un dispositivo anclado a la red

1. Consulte el manual de su dispositivo para saber cómo habilitar el uso compartido de datos por USB. Esta configuración se conoce a menudo como "anclado de red USB", "uso compartido de datos" o "módem USB".
1. Habilite el uso compartido de datos por USB.
1. Conecte el dispositivo al puerto USB-C de HoloLens.
1. En la configuración de red de HoloLens 2, el dispositivo aparecerá automáticamente como una conexión a Ethernet.
