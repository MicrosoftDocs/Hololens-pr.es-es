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
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924186"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="2b3b3-103">Conexión a dispositivos Bluetooth y USB-C</span><span class="sxs-lookup"><span data-stu-id="2b3b3-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="2b3b3-104">Emparejamiento con dispositivos Bluetooth</span><span class="sxs-lookup"><span data-stu-id="2b3b3-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="2b3b3-105">El dispositivo HoloLens 2 es compatible con las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="2b3b3-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="2b3b3-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="2b3b3-107">Mouse</span><span class="sxs-lookup"><span data-stu-id="2b3b3-107">Mouse</span></span>
    - <span data-ttu-id="2b3b3-108">Keyboard</span><span class="sxs-lookup"><span data-stu-id="2b3b3-108">Keyboard</span></span>
- <span data-ttu-id="2b3b3-109">Dispositivos de salida de audio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="2b3b3-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="2b3b3-110">HoloLens 2 es compatible con las siguientes API Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="2b3b3-111">[Servidor](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) y [cliente](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client) GATT</span><span class="sxs-lookup"><span data-stu-id="2b3b3-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="2b3b3-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="2b3b3-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="2b3b3-113">Es posible que tenga que instalar las aplicaciones complementarias correspondientes de Microsoft Store para poder usar los dispositivos HID y GATT.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="2b3b3-114">El dispositivo HoloLens (1.ª generación) es compatible con las siguientes clases de dispositivos Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="2b3b3-115">Mouse</span><span class="sxs-lookup"><span data-stu-id="2b3b3-115">Mouse</span></span>
- <span data-ttu-id="2b3b3-116">Keyboard</span><span class="sxs-lookup"><span data-stu-id="2b3b3-116">Keyboard</span></span>
- [<span data-ttu-id="2b3b3-117">Mando HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="2b3b3-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="2b3b3-118">Otros tipos de dispositivos Bluetooth, como altavoces, auriculares, teléfonos inteligentes y cartuchos de juegos, pueden aparecer en la lista como disponibles en la configuración del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="2b3b3-119">Sin embargo, estos dispositivos no son compatibles con HoloLens (1.ª generación).</span><span class="sxs-lookup"><span data-stu-id="2b3b3-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="2b3b3-120">Para obtener más información, consulte [Los dispositivos que aparecen como Configuración no funcionan](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span><span class="sxs-lookup"><span data-stu-id="2b3b3-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="2b3b3-121">Emparejamiento de un teclado o un mouse Bluetooth</span><span class="sxs-lookup"><span data-stu-id="2b3b3-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="2b3b3-122">Encienda el teclado o el mouse y haga que se detecte.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="2b3b3-123">Para saber cómo hacer que el dispositivo se detecte, busque información sobre el dispositivo (o su documentación) o visite el sitio web del fabricante.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="2b3b3-124">Utilice el gesto de eclosión en HoloLens (1.ª generación) o el gesto Inicio en HoloLens 2 para ir a **Inicio** y luego seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="2b3b3-125">Seleccione **Dispositivos** y asegúrese de que el Bluetooth esté activado.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="2b3b3-126">Cuando vea el nombre del dispositivo, seleccione **Emparejar** y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="2b3b3-127">Desactivación de Bluetooth</span><span class="sxs-lookup"><span data-stu-id="2b3b3-127">Disable Bluetooth</span></span>

<span data-ttu-id="2b3b3-128">Este procedimiento desactiva los componentes de radiofrecuencia de la radio Bluetooth y deshabilita todas las funciones de Bluetooth en Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="2b3b3-129">Utilice el gesto de eclosión en HoloLens (1.ª generación) o el gesto Inicio en HoloLens 2 para ir a **Inicio** y luego seleccione **Configuración** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="2b3b3-130">Mueva el control deslizante de **Bluetooth** a la posición **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="2b3b3-131">HoloLens 2: conectar dispositivos USB-C</span><span class="sxs-lookup"><span data-stu-id="2b3b3-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="2b3b3-132">El dispositivo HoloLens 2 es compatible con las siguientes clases de dispositivos USB-C:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="2b3b3-133">Dispositivos de almacenamiento masivo (como unidades USB)</span><span class="sxs-lookup"><span data-stu-id="2b3b3-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="2b3b3-134">Adaptadores Ethernet (incluido Ethernet más carga)</span><span class="sxs-lookup"><span data-stu-id="2b3b3-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="2b3b3-135">Adaptadores de audio digital USB-C a 3 5 mm</span><span class="sxs-lookup"><span data-stu-id="2b3b3-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="2b3b3-136">Cascos de audio digital USB-C (incluyendo adaptadores de cascos más carga)</span><span class="sxs-lookup"><span data-stu-id="2b3b3-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="2b3b3-137">Micrófonos externos USB-C ([Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y posteriores)</span><span class="sxs-lookup"><span data-stu-id="2b3b3-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="2b3b3-138">Mouse con cable</span><span class="sxs-lookup"><span data-stu-id="2b3b3-138">Wired mouse</span></span>
- <span data-ttu-id="2b3b3-139">Teclado con cable</span><span class="sxs-lookup"><span data-stu-id="2b3b3-139">Wired keyboard</span></span>
- <span data-ttu-id="2b3b3-140">Concentradores de PD de combinación (USB A más carga de PD)</span><span class="sxs-lookup"><span data-stu-id="2b3b3-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="2b3b3-141">En respuesta a los comentarios de los clientes, hemos habilitado compatibilidad limitada para la conectividad a través de la red de telefonía móvil anclada directamente a HoloLens mediante USB-C.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="2b3b3-142">Consulte [Conectar a redes de telefonía móvil y 5G](hololens-cellular.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="2b3b3-143">Compatibilidad con micrófono externo USB-C</span><span class="sxs-lookup"><span data-stu-id="2b3b3-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b3b3-144">La conexión de **un micrófono USB no lo establecerá automáticamente como dispositivo de entrada**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="2b3b3-145">Al conectar un conjunto de auriculares USB-C, los usuarios observarán que el audio del auricular se redirigirá automáticamente a los auriculares, pero el sistema operativo de HoloLens da prioridad a la matriz de micrófonos interna por encima de cualquier otro dispositivo de entrada.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="2b3b3-146">**Para usar un micrófono USB-C, siga los pasos que se indican a continuación.**</span><span class="sxs-lookup"><span data-stu-id="2b3b3-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="2b3b3-147">Los micrófonos externos no se pueden usar en compilaciones anteriores a [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y posteriores.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="2b3b3-148">Los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel de configuración **Sonido**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="2b3b3-149">Los micrófonos USB-C se pueden usar para llamar, grabar, etc.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="2b3b3-150">Abra la aplicación **Configuración** y seleccione **Sistema** > **Sonido**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Configuración de sonido](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="2b3b3-152">Para usar micrófonos externos con **Remote Assist**, los usuarios tendrán que hacer clic en el hipervínculo "Manage sound devices" (Administrar dispositivos de sonido).</span><span class="sxs-lookup"><span data-stu-id="2b3b3-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="2b3b3-153">A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado** o **Communications Default (Predeterminado de comunicaciones)** .</span><span class="sxs-lookup"><span data-stu-id="2b3b3-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="2b3b3-154">Si elige **Predeterminado**, el micrófono externo se usará en todas partes.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="2b3b3-155">Si elige **Communications Default** (Predeterminado de comunicaciones), el micrófono externo se usará en Remote Assist y en otras aplicaciones de comunicaciones, pero en las demás tareas se podrá seguir usando la matriz de micrófonos de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Administrar dispositivos de sonido](images/usbc-mic-2.png)

<br>

![Establecer el valor predeterminado del micrófono](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="2b3b3-158">¿Se admiten los micrófonos Bluetooth?</span><span class="sxs-lookup"><span data-stu-id="2b3b3-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="2b3b3-159">Desafortunadamente, HoloLens 2 todavía no admite los micrófonos Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="2b3b3-160">Concentradores USB-C</span><span class="sxs-lookup"><span data-stu-id="2b3b3-160">USB-C Hubs</span></span>

<span data-ttu-id="2b3b3-161">Es posible que algunos usuarios deban conectar varios dispositivos a la vez.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="2b3b3-162">Para los usuarios que quieren usar un [micrófono USB-C](#usb-c-external-microphone-support) junto con otro dispositivo conectado, los concentradores USB-C pueden ser la respuesta a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="2b3b3-163">Microsoft no ha probado estos dispositivos ni puede recomendar ninguna marca específica.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="2b3b3-164">**Requisitos para concentradores USB-C y dispositivos conectados:**</span><span class="sxs-lookup"><span data-stu-id="2b3b3-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="2b3b3-165">Los dispositivos conectados no deben requerir la instalación de un controlador.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="2b3b3-166">El consumo de potencia total de todos los dispositivos conectados debe ser inferior a 4,5 vatios.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="2b3b3-167">Conexión a Miracast</span><span class="sxs-lookup"><span data-stu-id="2b3b3-167">Connect to Miracast</span></span>

<span data-ttu-id="2b3b3-168">Para utilizar Miracast, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="2b3b3-169">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2b3b3-169">Do one of the following:</span></span>  

   - <span data-ttu-id="2b3b3-170">Abra el menú **Inicio** y seleccione el icono de **Pantalla**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="2b3b3-171">Diga "Conectar" mientras mira el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="2b3b3-172">En la lista de dispositivos que aparece, seleccione un dispositivo disponible.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="2b3b3-173">Complete el emparejamiento para empezar a proyectar.</span><span class="sxs-lookup"><span data-stu-id="2b3b3-173">Complete the pairing to begin projecting.</span></span>
