---
title: Conexión a dispositivos Bluetooth y USB-C
description: Introducción a la conexión con dispositivos y accesorios Bluetooth y USB-C desde dispositivos HoloLens de realidad mixta.
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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034480"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Conexión a dispositivos Bluetooth y USB-C

## <a name="pair-bluetooth-devices"></a>Emparejamiento con dispositivos Bluetooth

El dispositivo HoloLens 2 es compatible con las siguientes clases de dispositivos Bluetooth:

- [HID](/windows-hardware/drivers/hid/):
    - Mouse
    - Keyboard
- Dispositivos de salida de audio (A2DP)

HoloLens 2 es compatible con las siguientes API Bluetooth:
- [Servidor](/windows/uwp/devices-sensors/gatt-server) y [cliente](/windows/uwp/devices-sensors/gatt-client) GATT
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Es posible que tenga que instalar las aplicaciones complementarias correspondientes de Microsoft Store para poder usar los dispositivos HID y GATT.

El dispositivo HoloLens (1.ª generación) es compatible con las siguientes clases de dispositivos Bluetooth:

- Mouse
- Keyboard
- [Mando HoloLens (1.ª generación)](hololens1-clicker.md)

> [!NOTE]
> Otros tipos de dispositivos Bluetooth, como altavoces, auriculares, teléfonos inteligentes y cartuchos de juegos, pueden aparecer en la lista como disponibles en la configuración del dispositivo HoloLens. Sin embargo, estos dispositivos no son compatibles con HoloLens (1.ª generación). Para obtener más información, consulte [Los dispositivos que aparecen como Configuración no funcionan](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Emparejamiento de un teclado o un mouse Bluetooth

1. Encienda el teclado o el mouse y haga que se detecte. Para saber cómo hacer que el dispositivo se detecte, busque información sobre el dispositivo (o su documentación) o visite el sitio web del fabricante.

1. Utilice el gesto de eclosión en HoloLens (1.ª generación) o el gesto Inicio en HoloLens 2 para ir a **Inicio** y luego seleccione **Configuración**.

1. Seleccione **Dispositivos** y asegúrese de que el Bluetooth esté activado.  

1. Cuando vea el nombre del dispositivo, seleccione **Emparejar** y siga las instrucciones.

## <a name="disable-bluetooth"></a>Desactivación de Bluetooth

Este procedimiento desactiva los componentes de radiofrecuencia de la radio Bluetooth y deshabilita todas las funciones de Bluetooth en Microsoft HoloLens.

1. Utilice el gesto de eclosión en HoloLens (1.ª generación) o el gesto Inicio en HoloLens 2 para ir a **Inicio** y luego seleccione **Configuración** > **Dispositivos**.

1. Mueva el control deslizante de **Bluetooth** a la posición **Desactivado**.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: conectar dispositivos USB-C

El dispositivo HoloLens 2 es compatible con las siguientes clases de dispositivos USB-C:

- Dispositivos de almacenamiento masivo (como unidades USB)
- Adaptadores Ethernet (incluido Ethernet más carga)
- Adaptadores de audio digital USB-C a 3 5 mm
- Cascos de audio digital USB-C (incluyendo adaptadores de cascos más carga)
- Micrófonos externos USB-C ([Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y posteriores)
- Mouse con cable
- Teclado con cable
- Concentradores de PD de combinación (USB A más carga de PD)


> [!NOTE]
> En respuesta a los comentarios de los clientes, hemos habilitado compatibilidad limitada para la conectividad a través de la red de telefonía móvil anclada directamente a HoloLens mediante USB-C. Consulte [Conectar a redes de telefonía móvil y 5G](hololens-cellular.md) para obtener más información.

### <a name="usb-c-external-microphone-support"></a>Compatibilidad con micrófono externo USB-C

> [!IMPORTANT]
> La conexión de **un micrófono USB no lo establecerá automáticamente como dispositivo de entrada**. Al conectar un conjunto de auriculares USB-C, los usuarios observarán que el audio del auricular se redirigirá automáticamente a los auriculares, pero el sistema operativo de HoloLens da prioridad a la matriz de micrófonos interna por encima de cualquier otro dispositivo de entrada. **Para usar un micrófono USB-C, siga los pasos que se indican a continuación.**

> [!NOTE]
> Los micrófonos externos no se pueden usar en compilaciones anteriores a [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y posteriores. 

Los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel de configuración **Sonido**. Los micrófonos USB-C se pueden usar para llamar, grabar, etc.

Abra la aplicación **Configuración** y seleccione **Sistema** > **Sonido**.

![Configuración de Sonido.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar micrófonos externos con **Remote Assist**, los usuarios tendrán que hacer clic en el hipervínculo "Manage sound devices" (Administrar dispositivos de sonido).
>
> A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado** o **Communications Default (Predeterminado de comunicaciones)** . Si elige **Predeterminado**, el micrófono externo se usará en todas partes.
>
> Si elige **Communications Default** (Predeterminado de comunicaciones), el micrófono externo se usará en Remote Assist y en otras aplicaciones de comunicaciones, pero en las demás tareas se podrá seguir usando la matriz de micrófonos de HoloLens.

![Administrar dispositivos de sonido.](images/usbc-mic-2.png)

<br>

![Establecer el valor predeterminado del micrófono.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>¿Se admiten los micrófonos Bluetooth?

Desafortunadamente, HoloLens 2 todavía no admite los micrófonos Bluetooth.

### <a name="usb-c-hubs"></a>Concentradores USB-C

Es posible que algunos usuarios deban conectar varios dispositivos a la vez. Para los usuarios que quieren usar un [micrófono USB-C](#usb-c-external-microphone-support) junto con otro dispositivo conectado, los concentradores USB-C pueden ser la respuesta a sus necesidades. Microsoft no ha probado estos dispositivos ni puede recomendar ninguna marca específica.

**Requisitos para concentradores USB-C y dispositivos conectados:**

- Los dispositivos conectados no deben requerir la instalación de un controlador.
- El consumo de potencia total de todos los dispositivos conectados debe ser inferior a 4,5 vatios.

## <a name="connect-to-miracast"></a>Conexión a Miracast

Para utilizar Miracast, siga estos pasos:

1. Realice una de las siguientes acciones:  

   - Abra el menú **Inicio** y seleccione el icono de **Pantalla**.
   - Diga "Conectar" mientras mira el menú **Inicio**.  

1. En la lista de dispositivos que aparece, seleccione un dispositivo disponible.

1. Complete el emparejamiento para empezar a proyectar.
