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
ms.openlocfilehash: 2f2de4d776a0fdb99555687a96719d111ffb6460
ms.sourcegitcommit: 8bf8e9196c4ea89297f210b5c1d41b31f9edd407
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "11156297"
---
# <span data-ttu-id="3c02c-103">Conectarse a dispositivos Bluetooth y USB-C</span><span class="sxs-lookup"><span data-stu-id="3c02c-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="3c02c-104">No se pueden usar Micrófonos externos.</span><span class="sxs-lookup"><span data-stu-id="3c02c-104">External microphones cannot be used.</span></span> <span data-ttu-id="3c02c-105">HoloLens 2 usa su de [matriz de micrófonos integrada](hololens2-hardware.md#audio-and-speech).</span><span class="sxs-lookup"><span data-stu-id="3c02c-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <span data-ttu-id="3c02c-106">Emparejar dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3c02c-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="3c02c-107">El HoloLens 2 soporta las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="3c02c-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="3c02c-108">Mouse</span><span class="sxs-lookup"><span data-stu-id="3c02c-108">Mouse</span></span>
- <span data-ttu-id="3c02c-109">Teclado</span><span class="sxs-lookup"><span data-stu-id="3c02c-109">Keyboard</span></span>
- <span data-ttu-id="3c02c-110">Dispositivos de salida de audio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="3c02c-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="3c02c-111">El HoloLens (1ª generación) soporta las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="3c02c-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="3c02c-112">Mouse</span><span class="sxs-lookup"><span data-stu-id="3c02c-112">Mouse</span></span>
- <span data-ttu-id="3c02c-113">Teclado</span><span class="sxs-lookup"><span data-stu-id="3c02c-113">Keyboard</span></span>
- <span data-ttu-id="3c02c-114">Mando HoloLens (1era generación)</span><span class="sxs-lookup"><span data-stu-id="3c02c-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="3c02c-115">Otros tipos de dispositivos Bluetooth, como altavoces, auriculares, teléfonos inteligentes y cartuchos de juegos, pueden aparecer en la lista como disponibles en la configuración de la HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3c02c-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="3c02c-116">Sin embargo, estos dispositivos no son compatibles con el HoloLens (1era generación).</span><span class="sxs-lookup"><span data-stu-id="3c02c-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="3c02c-117">Para obtener más información, consulte la sección[Configuración de HoloLens, en la que se enumeran los dispositivos disponibles, pero éstos no funcionan](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="3c02c-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="3c02c-118">Emparejar un teclado o un ratón Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3c02c-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="3c02c-119">Encienda el teclado o el ratón y póngalo visible.</span><span class="sxs-lookup"><span data-stu-id="3c02c-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="3c02c-120">Para aprender cómo hacer que el dispositivo sea visible, busque información sobre el dispositivo (o su documentación) o visite el sitio web del fabricante.</span><span class="sxs-lookup"><span data-stu-id="3c02c-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="3c02c-121">Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a \*\* Inicio\*\*, y luego selecciona **Ajustes**.</span><span class="sxs-lookup"><span data-stu-id="3c02c-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="3c02c-122">Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.</span><span class="sxs-lookup"><span data-stu-id="3c02c-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="3c02c-123">Cuando vea el nombre del dispositivo, seleccione **Emparejar**, y luego sigue las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="3c02c-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="3c02c-124">HoloLens (1era generación): emparejar el mando</span><span class="sxs-lookup"><span data-stu-id="3c02c-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="3c02c-125">Utilice el gesto de eclosión para ir a**Inicio**, y luego seleccione**Ajustes**.</span><span class="sxs-lookup"><span data-stu-id="3c02c-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="3c02c-126">Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.</span><span class="sxs-lookup"><span data-stu-id="3c02c-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="3c02c-127">Use la punta de un bolígrafo para presionar y mantener el botón de emparejamiento del mando hasta que la luz de estado del mando parpadee en blanco.</span><span class="sxs-lookup"><span data-stu-id="3c02c-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="3c02c-128">Asegúrese de mantener pulsado el botón hasta que la luz empiece a parpadear.</span><span class="sxs-lookup"><span data-stu-id="3c02c-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="3c02c-129">El botón de apareamiento está en la parte inferior del mando, junto al bucle del dedo.</span><span class="sxs-lookup"><span data-stu-id="3c02c-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![El botón de apareamiento está al lado del bucle del dedo](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="3c02c-131">En la pantalla de apareamiento, seleccione**Comando** > **Emparejamiento**.</span><span class="sxs-lookup"><span data-stu-id="3c02c-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="3c02c-132">Desactivar Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3c02c-132">Disable Bluetooth</span></span>

<span data-ttu-id="3c02c-133">Este procedimiento desactiva los componentes de radiofrecuencia de la radio Bluetooth y desactiva todas las funciones de Bluetooth en el HoloLens de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c02c-133">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="3c02c-134">Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a **Inicio**, y luego selecciona **Configuración** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3c02c-134">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="3c02c-135">Deslice el interruptor de activación de **Bluetooth** a la posición **Desconectado**.</span><span class="sxs-lookup"><span data-stu-id="3c02c-135">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <span data-ttu-id="3c02c-136">HoloLens 2: conectar dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="3c02c-136">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="3c02c-137">El HoloLens 2 soporta las siguientes clases de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="3c02c-137">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="3c02c-138">Dispositivos de almacenamiento masivo (como las unidades de disco duro)</span><span class="sxs-lookup"><span data-stu-id="3c02c-138">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="3c02c-139">Adaptadores Ethernet (incluyendo ethernet más carga)</span><span class="sxs-lookup"><span data-stu-id="3c02c-139">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="3c02c-140">Adaptadores de audio digital USB-C a 3.5mm</span><span class="sxs-lookup"><span data-stu-id="3c02c-140">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="3c02c-141">Auriculares de audio digital USB-C (incluyendo adaptadores de auriculares más carga)</span><span class="sxs-lookup"><span data-stu-id="3c02c-141">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="3c02c-142">Ratón con cable</span><span class="sxs-lookup"><span data-stu-id="3c02c-142">Wired mouse</span></span>
- <span data-ttu-id="3c02c-143">Teclado con cable</span><span class="sxs-lookup"><span data-stu-id="3c02c-143">Wired keyboard</span></span>
- <span data-ttu-id="3c02c-144">Combinación de concentradores de DP (USB A + carga de DP)</span><span class="sxs-lookup"><span data-stu-id="3c02c-144">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="3c02c-145">Algunos dispositivos móviles con conexiones USB-C se presentan al HoloLens como adaptadores de ethernet, y por lo tanto podrían ser utilizados en una configuración de atadura, comenzando con el Windows Holographic, versión 2004.</span><span class="sxs-lookup"><span data-stu-id="3c02c-145">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="3c02c-146">No se admiten los módems USB LTE que requieran un controlador diferente, o bien la aplicación instalada para la configuración.</span><span class="sxs-lookup"><span data-stu-id="3c02c-146">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

<span data-ttu-id="3c02c-147">En respuesta a los comentarios de los clientes, hemos habilitado la compatibilidad limitada para la conectividad de telefonía móvil anclada directamente a HoloLens mediante USB-C.</span><span class="sxs-lookup"><span data-stu-id="3c02c-147">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span>  <span data-ttu-id="3c02c-148">La conectividad anclada solo funciona para dispositivos que sean compatibles con la implementación del controlador [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) genérico de Microsoft y que no requieran la instalación de controladores o aplicaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="3c02c-148">Tethered connectivity only works for devices that support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver implementation and that don’t require any additional drivers or application installs.</span></span>  <span data-ttu-id="3c02c-149">Este dispositivo, cuando esté conectado, aparecerá automáticamente como una nueva conexión Ethernet en la interfaz de usuario de configuración de red de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3c02c-149">Such device, when connected, will automatically appear as a new Ethernet connection in the HoloLens 2 Network Settings UI.</span></span> <span data-ttu-id="3c02c-150">Consulte con el fabricante del dispositivo para obtener más información sobre si admite el controlador RNDIS genérico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c02c-150">Please consult your device’s manufacturer for further details on whether it supports the generic Microsoft RNDIS driver.</span></span>

## <span data-ttu-id="3c02c-151">Conéctese a Miracast</span><span class="sxs-lookup"><span data-stu-id="3c02c-151">Connect to Miracast</span></span>

<span data-ttu-id="3c02c-152">Para utilizar Miracast, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3c02c-152">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="3c02c-153">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3c02c-153">Do one of the following:</span></span>  

   - <span data-ttu-id="3c02c-154">Abra el menú **Inicio**y seleccione el icono de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="3c02c-154">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="3c02c-155">Diga "Conectar" mientras mira el menú de**Inicio**.</span><span class="sxs-lookup"><span data-stu-id="3c02c-155">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="3c02c-156">En la lista de dispositivos que aparece, seleccione un dispositivo disponible.</span><span class="sxs-lookup"><span data-stu-id="3c02c-156">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="3c02c-157">Complete el apareamiento para empezar a proyectar.</span><span class="sxs-lookup"><span data-stu-id="3c02c-157">Complete the pairing to begin projecting.</span></span>
