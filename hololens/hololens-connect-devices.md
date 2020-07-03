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
ms.openlocfilehash: d4c5441c1df198ae1c85be5d8f4fe38f10f0be4b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828715"
---
# <span data-ttu-id="85b5f-103">Conectarse a dispositivos Bluetooth y USB-C</span><span class="sxs-lookup"><span data-stu-id="85b5f-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="85b5f-104">Emparejar dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="85b5f-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="85b5f-105">El HoloLens 2 soporta las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="85b5f-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="85b5f-106">Mouse</span><span class="sxs-lookup"><span data-stu-id="85b5f-106">Mouse</span></span>
- <span data-ttu-id="85b5f-107">Teclado</span><span class="sxs-lookup"><span data-stu-id="85b5f-107">Keyboard</span></span>
- <span data-ttu-id="85b5f-108">Dispositivos de salida de audio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="85b5f-108">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="85b5f-109">El HoloLens (1ª generación) soporta las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="85b5f-109">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="85b5f-110">Mouse</span><span class="sxs-lookup"><span data-stu-id="85b5f-110">Mouse</span></span>
- <span data-ttu-id="85b5f-111">Teclado</span><span class="sxs-lookup"><span data-stu-id="85b5f-111">Keyboard</span></span>
- <span data-ttu-id="85b5f-112">Mando HoloLens (1era generación)</span><span class="sxs-lookup"><span data-stu-id="85b5f-112">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="85b5f-113">Otros tipos de dispositivos Bluetooth, como altavoces, auriculares, teléfonos inteligentes y cartuchos de juegos, pueden aparecer en la lista como disponibles en la configuración de la HoloLens.</span><span class="sxs-lookup"><span data-stu-id="85b5f-113">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="85b5f-114">Sin embargo, estos dispositivos no son compatibles con el HoloLens (1era generación).</span><span class="sxs-lookup"><span data-stu-id="85b5f-114">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="85b5f-115">Para obtener más información, consulte la sección[Configuración de HoloLens, en la que se enumeran los dispositivos disponibles, pero éstos no funcionan](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="85b5f-115">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="85b5f-116">Emparejar un teclado o un ratón Bluetooth</span><span class="sxs-lookup"><span data-stu-id="85b5f-116">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="85b5f-117">Encienda el teclado o el ratón y póngalo visible.</span><span class="sxs-lookup"><span data-stu-id="85b5f-117">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="85b5f-118">Para aprender cómo hacer que el dispositivo sea visible, busque información sobre el dispositivo (o su documentación) o visite el sitio web del fabricante.</span><span class="sxs-lookup"><span data-stu-id="85b5f-118">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="85b5f-119">Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a \*\* Inicio\*\*, y luego selecciona **Ajustes**.</span><span class="sxs-lookup"><span data-stu-id="85b5f-119">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>
1. <span data-ttu-id="85b5f-120">Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.</span><span class="sxs-lookup"><span data-stu-id="85b5f-120">Select **Devices**, and make sure that Bluetooth is on.</span></span>  
1. <span data-ttu-id="85b5f-121">Cuando vea el nombre del dispositivo, seleccione **Emparejar**, y luego sigue las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="85b5f-121">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="85b5f-122">HoloLens (1era generación): emparejar el mando</span><span class="sxs-lookup"><span data-stu-id="85b5f-122">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="85b5f-123">Utilice el gesto de eclosión para ir a**Inicio**, y luego seleccione**Ajustes**.</span><span class="sxs-lookup"><span data-stu-id="85b5f-123">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="85b5f-124">Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.</span><span class="sxs-lookup"><span data-stu-id="85b5f-124">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="85b5f-125">Use la punta de un bolígrafo para presionar y mantener el botón de emparejamiento del mando hasta que la luz de estado del mando parpadee en blanco.</span><span class="sxs-lookup"><span data-stu-id="85b5f-125">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="85b5f-126">Asegúrese de mantener pulsado el botón hasta que la luz empiece a parpadear.</span><span class="sxs-lookup"><span data-stu-id="85b5f-126">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="85b5f-127">El botón de apareamiento está en la parte inferior del mando, junto al bucle del dedo.</span><span class="sxs-lookup"><span data-stu-id="85b5f-127">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![El botón de apareamiento está al lado del bucle del dedo](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="85b5f-129">En la pantalla de apareamiento, seleccione**Comando** > **Emparejamiento**.</span><span class="sxs-lookup"><span data-stu-id="85b5f-129">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="85b5f-130">HoloLens 2: conectar dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="85b5f-130">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="85b5f-131">El HoloLens 2 soporta las siguientes clases de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="85b5f-131">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="85b5f-132">Dispositivos de almacenamiento masivo (como las unidades de disco duro)</span><span class="sxs-lookup"><span data-stu-id="85b5f-132">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="85b5f-133">Adaptadores Ethernet (incluyendo ethernet más carga)</span><span class="sxs-lookup"><span data-stu-id="85b5f-133">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="85b5f-134">Adaptadores de audio digital USB-C a 3.5mm</span><span class="sxs-lookup"><span data-stu-id="85b5f-134">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="85b5f-135">Auriculares de audio digital USB-C (incluyendo adaptadores de auriculares más carga)</span><span class="sxs-lookup"><span data-stu-id="85b5f-135">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="85b5f-136">Ratón con cable</span><span class="sxs-lookup"><span data-stu-id="85b5f-136">Wired mouse</span></span>
- <span data-ttu-id="85b5f-137">Teclado con cable</span><span class="sxs-lookup"><span data-stu-id="85b5f-137">Wired keyboard</span></span>
- <span data-ttu-id="85b5f-138">Combinación de concentradores de DP (USB A + carga de DP)</span><span class="sxs-lookup"><span data-stu-id="85b5f-138">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="85b5f-139">Algunos dispositivos móviles con conexiones USB-C se presentan al HoloLens como adaptadores de ethernet, y por lo tanto podrían ser utilizados en una configuración de atadura, comenzando con el Windows Holographic, versión 2004.</span><span class="sxs-lookup"><span data-stu-id="85b5f-139">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="85b5f-140">No se admiten los módems USB LTE que requieren un controlador separado, y/o la aplicación instalada para la configuración</span><span class="sxs-lookup"><span data-stu-id="85b5f-140">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported</span></span>

## <span data-ttu-id="85b5f-141">Conéctese a Miracast</span><span class="sxs-lookup"><span data-stu-id="85b5f-141">Connect to Miracast</span></span>

<span data-ttu-id="85b5f-142">Para utilizar Miracast, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="85b5f-142">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="85b5f-143">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="85b5f-143">Do one of the following:</span></span>  

   - <span data-ttu-id="85b5f-144">Abra el menú **Inicio**y seleccione el icono de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="85b5f-144">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="85b5f-145">Diga "Conectar" mientras mira el menú de**Inicio**.</span><span class="sxs-lookup"><span data-stu-id="85b5f-145">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="85b5f-146">En la lista de dispositivos que aparece, seleccione un dispositivo disponible.</span><span class="sxs-lookup"><span data-stu-id="85b5f-146">On the list of devices that appears, select an available device.</span></span>
1. <span data-ttu-id="85b5f-147">Complete el apareamiento para empezar a proyectar.</span><span class="sxs-lookup"><span data-stu-id="85b5f-147">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="85b5f-148">Desactivar Bluetooth</span><span class="sxs-lookup"><span data-stu-id="85b5f-148">Disable Bluetooth</span></span>

<span data-ttu-id="85b5f-149">Este procedimiento desactiva los componentes de radiofrecuencia de la radio Bluetooth y desactiva todas las funciones de Bluetooth en el HoloLens de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85b5f-149">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="85b5f-150">Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a **Inicio**, y luego selecciona **Configuración** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="85b5f-150">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>
1. <span data-ttu-id="85b5f-151">Deslice el interruptor de activación de **Bluetooth** a la posición **Desconectado**.</span><span class="sxs-lookup"><span data-stu-id="85b5f-151">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
