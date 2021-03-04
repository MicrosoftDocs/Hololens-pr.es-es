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
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="f1187-103">Conectarse a dispositivos Bluetooth y USB-C</span><span class="sxs-lookup"><span data-stu-id="f1187-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="f1187-104">No se pueden usar Micrófonos externos.</span><span class="sxs-lookup"><span data-stu-id="f1187-104">External microphones cannot be used.</span></span> <span data-ttu-id="f1187-105">HoloLens 2 usa su de [matriz de micrófonos integrada](hololens2-hardware.md#audio-and-speech).</span><span class="sxs-lookup"><span data-stu-id="f1187-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="f1187-106">Emparejar dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f1187-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="f1187-107">El HoloLens 2 soporta las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="f1187-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f1187-108">Mouse</span><span class="sxs-lookup"><span data-stu-id="f1187-108">Mouse</span></span>
- <span data-ttu-id="f1187-109">Teclado</span><span class="sxs-lookup"><span data-stu-id="f1187-109">Keyboard</span></span>
- <span data-ttu-id="f1187-110">Dispositivos de salida de audio Bluetooth (A2DP)</span><span class="sxs-lookup"><span data-stu-id="f1187-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="f1187-111">El HoloLens (1ª generación) soporta las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="f1187-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f1187-112">Mouse</span><span class="sxs-lookup"><span data-stu-id="f1187-112">Mouse</span></span>
- <span data-ttu-id="f1187-113">Teclado</span><span class="sxs-lookup"><span data-stu-id="f1187-113">Keyboard</span></span>
- [<span data-ttu-id="f1187-114">Mando HoloLens (1era generación)</span><span class="sxs-lookup"><span data-stu-id="f1187-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="f1187-115">Otros tipos de dispositivos Bluetooth, como altavoces, auriculares, teléfonos inteligentes y cartuchos de juegos, pueden aparecer en la lista como disponibles en la configuración de la HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f1187-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="f1187-116">Sin embargo, estos dispositivos no son compatibles con el HoloLens (1era generación).</span><span class="sxs-lookup"><span data-stu-id="f1187-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="f1187-117">Para obtener más información, consulte la sección[Configuración de HoloLens, en la que se enumeran los dispositivos disponibles, pero éstos no funcionan](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span><span class="sxs-lookup"><span data-stu-id="f1187-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="f1187-118">Emparejar un teclado o un ratón Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f1187-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="f1187-119">Encienda el teclado o el ratón y póngalo visible.</span><span class="sxs-lookup"><span data-stu-id="f1187-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="f1187-120">Para aprender cómo hacer que el dispositivo sea visible, busque información sobre el dispositivo (o su documentación) o visite el sitio web del fabricante.</span><span class="sxs-lookup"><span data-stu-id="f1187-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="f1187-121">Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a \*\* Inicio\*\*, y luego selecciona **Ajustes**.</span><span class="sxs-lookup"><span data-stu-id="f1187-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="f1187-122">Seleccione **Dispositivos**, y asegúrese de que el Bluetooth esté activado.</span><span class="sxs-lookup"><span data-stu-id="f1187-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="f1187-123">Cuando vea el nombre del dispositivo, seleccione **Emparejar** y luego, siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f1187-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="f1187-124">Desactivar el Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f1187-124">Disable Bluetooth</span></span>

<span data-ttu-id="f1187-125">Este procedimiento desactiva los componentes de radiofrecuencia de la radio Bluetooth y desactiva todas las funciones de Bluetooth en el HoloLens de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1187-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="f1187-126">Utilice el gesto de eclosión (HoloLens (1era generación)) o el gesto de inicio (HoloLens 2) para ir a **Inicio**, y luego selecciona **Configuración** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f1187-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="f1187-127">Deslice el interruptor de activación de **Bluetooth** a la posición **Desconectado**.</span><span class="sxs-lookup"><span data-stu-id="f1187-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="f1187-128">HoloLens 2: conectar dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="f1187-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="f1187-129">El HoloLens 2 soporta las siguientes clases de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="f1187-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="f1187-130">Dispositivos de almacenamiento masivo (como las unidades de disco duro)</span><span class="sxs-lookup"><span data-stu-id="f1187-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="f1187-131">Adaptadores Ethernet (incluyendo ethernet más carga)</span><span class="sxs-lookup"><span data-stu-id="f1187-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="f1187-132">Adaptadores de audio digital USB-C a 3.5mm</span><span class="sxs-lookup"><span data-stu-id="f1187-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="f1187-133">Auriculares de audio digital USB-C (incluyendo adaptadores de auriculares más carga)</span><span class="sxs-lookup"><span data-stu-id="f1187-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="f1187-134">Ratón con cable</span><span class="sxs-lookup"><span data-stu-id="f1187-134">Wired mouse</span></span>
- <span data-ttu-id="f1187-135">Teclado con cable</span><span class="sxs-lookup"><span data-stu-id="f1187-135">Wired keyboard</span></span>
- <span data-ttu-id="f1187-136">Concentradores de PD de combinación (USB A más carga de PD)</span><span class="sxs-lookup"><span data-stu-id="f1187-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="f1187-137">En respuesta a los comentarios de los clientes, hemos habilitado compatibilidad limitada para la conectividad a través de la red de telefonía móvil anclada directamente a HoloLens mediante USB-C.</span><span class="sxs-lookup"><span data-stu-id="f1187-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="f1187-138">Consulte [Conectar a la red de telefonía móvil y 5G](hololens-cellular.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f1187-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="f1187-139">Concentradores USB-C</span><span class="sxs-lookup"><span data-stu-id="f1187-139">USB-C Hubs</span></span>

<span data-ttu-id="f1187-140">Es posible que algunos usuarios deban conectarse a varios dispositivos a la vez.</span><span class="sxs-lookup"><span data-stu-id="f1187-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="f1187-141">Para los usuarios que deseen previsualizar una función de Insider y [usar un micrófono USB-C](hololens-insider.md#usb-c-external-microphone-support) al tiempo que otro dispositivo conectado, los concentradores USB-C pueden adaptarse a las necesidades del cliente.</span><span class="sxs-lookup"><span data-stu-id="f1187-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="f1187-142">Microsoft no ha probado estos dispositivos ni recomienda ninguna marca específica.</span><span class="sxs-lookup"><span data-stu-id="f1187-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="f1187-143">Requisitos para concentradores USB-C y dispositivos conectados:</span><span class="sxs-lookup"><span data-stu-id="f1187-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="f1187-144">Los dispositivos conectados no deben requerir la instalación de un controlador.</span><span class="sxs-lookup"><span data-stu-id="f1187-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="f1187-145">El consumo de potencia total de todos los dispositivos conectados debe ser inferior a 4,5 vatios.</span><span class="sxs-lookup"><span data-stu-id="f1187-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="f1187-146">Conéctese a Miracast</span><span class="sxs-lookup"><span data-stu-id="f1187-146">Connect to Miracast</span></span>

<span data-ttu-id="f1187-147">Para utilizar Miracast, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f1187-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="f1187-148">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f1187-148">Do one of the following:</span></span>  

   - <span data-ttu-id="f1187-149">Abra el menú **Inicio**y seleccione el icono de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f1187-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="f1187-150">Diga "Conectar" mientras mira el menú de**Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f1187-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="f1187-151">En la lista de dispositivos que aparece, seleccione un dispositivo disponible.</span><span class="sxs-lookup"><span data-stu-id="f1187-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="f1187-152">Complete el apareamiento para empezar a proyectar.</span><span class="sxs-lookup"><span data-stu-id="f1187-152">Complete the pairing to begin projecting.</span></span>
