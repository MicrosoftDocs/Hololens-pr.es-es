---
title: Conectar HoloLens a una red
description: Instrucciones sobre cómo conectarte a Internet con HoloLens y sobre cómo identificar la dirección IP del dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, inalámbrico, Internet, IP, dirección IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 734176dcf8a789f130aa8b010f5f3c9ec1d22c72
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857798"
---
# <span data-ttu-id="79a31-104">Conectar HoloLens a una red</span><span class="sxs-lookup"><span data-stu-id="79a31-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="79a31-105">Para hacer la mayoría de las cosas en HoloLens, debes estar conectado a una red.</span><span class="sxs-lookup"><span data-stu-id="79a31-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="79a31-106">Esta guía te ayudará a:</span><span class="sxs-lookup"><span data-stu-id="79a31-106">This guide will help you:</span></span>

- <span data-ttu-id="79a31-107">Conéctate a una red con Wi-Fi o (solo para HoloLens 2) Ethernet a través de USB-C</span><span class="sxs-lookup"><span data-stu-id="79a31-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="79a31-108">Deshabilitar y volver a habilitar Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="79a31-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="79a31-109">Más información sobre cómo [usar HoloLens sin conexión](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="79a31-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="79a31-110">Conectarte por primera vez</span><span class="sxs-lookup"><span data-stu-id="79a31-110">Connecting for the first time</span></span>

<span data-ttu-id="79a31-111">La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="79a31-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="79a31-112">Si tienes problemas para conectarte a una red Wi-Fi durante la instalación, asegúrate de que tu red es una red abierta protegida con contraseña o una red de portales cautivos.</span><span class="sxs-lookup"><span data-stu-id="79a31-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="79a31-113">Asegúrate de que la red no requiera que uses un certificado para conectarte.</span><span class="sxs-lookup"><span data-stu-id="79a31-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="79a31-114">Tras la configuración, puedes conectarte a otros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="79a31-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="79a31-115">Conexión a una red Wi-Fi después de la configuración</span><span class="sxs-lookup"><span data-stu-id="79a31-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="79a31-116">Selecciona **Inicio** > **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="79a31-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="79a31-117">*Solo HoloLens (1.ª generación)*: usa la mirada para colocar la aplicación Configuración y, a continuación, mantenla pulsada en el aire para colocarla o di "Colocar".</span><span class="sxs-lookup"><span data-stu-id="79a31-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="79a31-118">Selecciona **Red e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="79a31-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="79a31-119">Si no ves la red, desplázate hacia abajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="79a31-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="79a31-120">Selecciona una red y, a continuación, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="79a31-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="79a31-121">Si se te pide una contraseña de red, escríbela y, a continuación, selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="79a31-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="79a31-122">Conectarte a Wi-Fi en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="79a31-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="79a31-123">HoloLens contiene una radio Wi-Fi 2x2 compatible con 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="79a31-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="79a31-124">Conectar HoloLens a una red Wi-Fi es similar a conectar un dispositivo móvil o Windows 10 Desktop a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="79a31-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configuración de Wi-Fi de HoloLens](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="79a31-126">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="79a31-127">Selecciona la aplicación Configuración en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="79a31-128">La aplicación Configuración se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="79a31-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="79a31-129">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="79a31-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="79a31-130">Asegúrate de que la conexión Wi-Fi está activada.</span><span class="sxs-lookup"><span data-stu-id="79a31-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="79a31-131">Selecciona una red Wi-Fi en la lista.</span><span class="sxs-lookup"><span data-stu-id="79a31-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="79a31-132">Si es necesario, escribe la contraseña de la red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="79a31-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="79a31-133">También puedes confirmar que estás conectado a una red Wi-Fi comprobando el estado de Wi-Fi en el menú **Inicio**:</span><span class="sxs-lookup"><span data-stu-id="79a31-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="79a31-134">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="79a31-135">Mira el estado de la Wi-Fi en la parte superior izquierda del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="79a31-136">Se mostrará el estado de la Wi-Fi y del SSID de la red conectada.</span><span class="sxs-lookup"><span data-stu-id="79a31-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="79a31-137">Solución de problemas de la conexión a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="79a31-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="79a31-138">Si tiene problemas para conectarse a una conexión Wi-Fi, consulte [No puedo conectarme a Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="79a31-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="79a31-139">Cuando inicia sesión en una cuenta de empresa u organización en el dispositivo, también puede aplicar la directiva de Administración de dispositivos móviles (MDM), si su administrador de TI configura la directiva.</span><span class="sxs-lookup"><span data-stu-id="79a31-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="79a31-140">Deshabilitar Wi-Fi en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="79a31-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="79a31-141">Usar la aplicación Configuración en HoloLens</span><span class="sxs-lookup"><span data-stu-id="79a31-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="79a31-142">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="79a31-143">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="79a31-144">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="79a31-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="79a31-145">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="79a31-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="79a31-146">Selecciona el interruptor del control deslizante de Wi-Fi para moverlo a la posición **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="79a31-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="79a31-147">Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y deshabilitará todas las características de Wi-Fi en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="79a31-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="79a31-148">Cuando la radio de Wi-Fi está deshabilitada, HoloLens no podrá cargar automáticamente sus [espacios](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="79a31-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="79a31-149">Mueve el interruptor del control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="79a31-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="79a31-150">El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.</span><span class="sxs-lookup"><span data-stu-id="79a31-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="79a31-151">Identificación de la dirección IP de HoloLens en la red Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="79a31-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="79a31-152">Mediante la aplicación Configuración</span><span class="sxs-lookup"><span data-stu-id="79a31-152">By using the Settings app</span></span>

1. <span data-ttu-id="79a31-153">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="79a31-154">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="79a31-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="79a31-155">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="79a31-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="79a31-156">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="79a31-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="79a31-157">Desplázate hasta debajo de la lista de redes Wi-Fi disponibles y selecciona **Propiedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="79a31-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propiedades de hardware en configuración de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="79a31-159">La dirección IP aparece junto a **Dirección IPv4**.</span><span class="sxs-lookup"><span data-stu-id="79a31-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="79a31-160">Con Cortana</span><span class="sxs-lookup"><span data-stu-id="79a31-160">By using Cortana</span></span>

<span data-ttu-id="79a31-161">Di "Hola Cortana, ¿cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="79a31-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="79a31-162">y Cortana mostrará y leerá tu dirección IP.</span><span class="sxs-lookup"><span data-stu-id="79a31-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="79a31-163">Con el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="79a31-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="79a31-164">En un explorador web de tu PC, abre el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="79a31-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="79a31-165">Ve a la sección **Redes**.</span><span class="sxs-lookup"><span data-stu-id="79a31-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="79a31-166">Esta sección muestra tu dirección IP y otra información de la red.</span><span class="sxs-lookup"><span data-stu-id="79a31-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="79a31-167">Con este método, puedes copiar y pegar de la dirección IP en tu PC de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="79a31-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
