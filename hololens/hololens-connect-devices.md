---
title: Conectarse a dispositivos Bluetooth y USB-C
description: Esta guía recorre la conexión de dispositivos y accesorios Bluetooth y USB-C.
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
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881250"
---
# Conectarse a dispositivos Bluetooth y USB-C

## Emparejar dispositivos Bluetooth

El HoloLens 2 soporta las siguientes clases de dispositivos Bluetooth:

- Mouse
- Teclado
- Dispositivos de salida de audio Bluetooth (A2DP)

> [!NOTE]
> No se pueden usar Micrófonos externos. HoloLens 2 usa su de [matriz de micrófonos integrada](hololens2-hardware.md#audio-and-speech).

El HoloLens (1ª generación) soporta las siguientes clases de dispositivos Bluetooth:

- Mouse
- Teclado
- Mando HoloLens (1era generación)

> [!NOTE]
> Otros tipos de dispositivos Bluetooth, como altavoces, auriculares, teléfonos inteligentes y cartuchos de juegos, pueden aparecer en la lista como disponibles en la configuración de la HoloLens. Sin embargo, estos dispositivos no son compatibles con el HoloLens (1era generación). Para obtener más información, consulte la sección[Configuración de HoloLens, en la que se enumeran los dispositivos disponibles, pero éstos no funcionan](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### Emparejar un teclado o un ratón Bluetooth

1. Encienda el teclado o el ratón y póngalo visible. Para aprender cómo hacer que el dispositivo sea visible, busque información sobre el dispositivo (o su documentación) o visite el sitio web del fabricante.

1. Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a ** Inicio**, y luego selecciona **Ajustes**.

1. Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.  

1. Cuando vea el nombre del dispositivo, seleccione **Emparejar**, y luego sigue las instrucciones.

### HoloLens (1era generación): emparejar el mando

1. Utilice el gesto de eclosión para ir a**Inicio**, y luego seleccione**Ajustes**.

1. Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.

1. Use la punta de un bolígrafo para presionar y mantener el botón de emparejamiento del mando hasta que la luz de estado del mando parpadee en blanco. Asegúrese de mantener pulsado el botón hasta que la luz empiece a parpadear.  

   El botón de apareamiento está en la parte inferior del mando, junto al bucle del dedo.
   
   ![El botón de apareamiento está al lado del bucle del dedo](images/use-hololens-clicker-1.png)
   
1. En la pantalla de apareamiento, seleccione**Comando** > **Emparejamiento**.

## HoloLens 2: conectar dispositivos USB-C

El HoloLens 2 soporta las siguientes clases de dispositivos USB-C:

- Dispositivos de almacenamiento masivo (como las unidades de disco duro)
- Adaptadores Ethernet (incluyendo ethernet más carga)
- Adaptadores de audio digital USB-C a 3.5mm
- Auriculares de audio digital USB-C (incluyendo adaptadores de auriculares más carga)
- Ratón con cable
- Teclado con cable
- Combinación de concentradores de DP (USB A + carga de DP)

> [!NOTE]
> Algunos dispositivos móviles con conexiones USB-C se presentan al HoloLens como adaptadores de ethernet, y por lo tanto podrían ser utilizados en una configuración de atadura, comenzando con el Windows Holographic, versión 2004. No se admiten los módems USB LTE que requieran un controlador diferente, o bien la aplicación instalada para la configuración.

## Conéctese a Miracast

Para utilizar Miracast, siga estos pasos:

1. Realiza una de las siguientes acciones:  

   - Abra el menú **Inicio**y seleccione el icono de la pantalla.
   - Diga "Conectar" mientras mira el menú de**Inicio**.  

1. En la lista de dispositivos que aparece, seleccione un dispositivo disponible.

1. Complete el apareamiento para empezar a proyectar.

## Desactivar Bluetooth

Este procedimiento desactiva los componentes de radiofrecuencia de la radio Bluetooth y desactiva todas las funciones de Bluetooth en el HoloLens de Microsoft.

1. Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a **Inicio**, y luego selecciona **Configuración** > **Dispositivos**.

1. Deslice el interruptor de activación de **Bluetooth** a la posición **Desconectado**.
