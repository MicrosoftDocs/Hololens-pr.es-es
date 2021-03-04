---
title: Conectarse a dispositivos Bluetooth y USB-C
description: Empiece ya a conectar a con dispositivos y accesorios que tengan Bluetooth y USB-C desde sus dispositivos de realidad mixta HoloLens.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385491"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Conectarse a dispositivos Bluetooth y USB-C

> [!NOTE]
> No se pueden usar Micrófonos externos. HoloLens 2 usa su de [matriz de micrófonos integrada](hololens2-hardware.md#audio-and-speech).

## <a name="pair-bluetooth-devices"></a>Emparejar dispositivos Bluetooth

El HoloLens 2 soporta las siguientes clases de dispositivos Bluetooth:

- Mouse
- Teclado
- Dispositivos de salida de audio Bluetooth (A2DP)

El HoloLens (1ª generación) soporta las siguientes clases de dispositivos Bluetooth:

- Mouse
- Teclado
- [Mando HoloLens (1era generación)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Otros tipos de dispositivos Bluetooth, como altavoces, auriculares, teléfonos inteligentes y cartuchos de juegos, pueden aparecer en la lista como disponibles en la configuración de la HoloLens. Sin embargo, estos dispositivos no son compatibles con el HoloLens (1era generación). Para obtener más información, consulte la sección[Configuración de HoloLens, en la que se enumeran los dispositivos disponibles, pero éstos no funcionan](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Emparejar un teclado o un ratón Bluetooth

1. Encienda el teclado o el ratón y póngalo visible. Para aprender cómo hacer que el dispositivo sea visible, busque información sobre el dispositivo (o su documentación) o visite el sitio web del fabricante.

1. Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a ** Inicio**, y luego selecciona **Ajustes**.

1. Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.  

1. Cuando vea el nombre del dispositivo, seleccione **Emparejar** y luego, siga las instrucciones.

## <a name="disable-bluetooth"></a>Desactivar el Bluetooth

Este procedimiento desactiva los componentes de radiofrecuencia de la radio Bluetooth y desactiva todas las funciones de Bluetooth en el HoloLens de Microsoft.

1. Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a **Inicio**, y luego selecciona **Configuración** > **Dispositivos**.

1. Deslice el interruptor de activación de **Bluetooth** a la posición **Desconectado**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: conectar dispositivos USB-C

El HoloLens 2 soporta las siguientes clases de dispositivos USB-C:

- Dispositivos de almacenamiento masivo (como las unidades de disco duro)
- Adaptadores Ethernet (incluyendo ethernet más carga)
- Adaptadores de audio digital USB-C a 3.5mm
- Auriculares de audio digital USB-C (incluyendo adaptadores de auriculares más carga)
- Ratón con cable
- Teclado con cable
- Concentradores de PD de combinación (USB A más carga de PD)

> [!NOTE]
> En respuesta a los comentarios de los clientes, hemos habilitado compatibilidad limitada para la conectividad a través de la red de telefonía móvil anclada directamente a HoloLens mediante USB-C. Consulte [Conectar a la red de telefonía móvil y 5G](hololens-cellular.md) para obtener más información.

### <a name="usb-c-hubs"></a>Concentradores USB-C

Es posible que algunos usuarios deban conectarse a varios dispositivos a la vez. Para los usuarios que deseen previsualizar una función de Insider y [usar un micrófono USB-C](hololens-insider.md#usb-c-external-microphone-support) al tiempo que otro dispositivo conectado, los concentradores USB-C pueden adaptarse a las necesidades del cliente. Microsoft no ha probado estos dispositivos ni recomienda ninguna marca específica.

**Requisitos para concentradores USB-C y dispositivos conectados:**

- Los dispositivos conectados no deben requerir la instalación de un controlador.
- El consumo de potencia total de todos los dispositivos conectados debe ser inferior a 4,5 vatios.

## <a name="connect-to-miracast"></a>Conéctese a Miracast

Para utilizar Miracast, siga estos pasos:

1. Realiza una de las siguientes acciones:  

   - Abra el menú **Inicio**y seleccione el icono de la pantalla.
   - Diga "Conectar" mientras mira el menú de**Inicio**.  

1. En la lista de dispositivos que aparece, seleccione un dispositivo disponible.

1. Complete el apareamiento para empezar a proyectar.
