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
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883154"
---
# <span data-ttu-id="03ed6-104">Conectar HoloLens a una red</span><span class="sxs-lookup"><span data-stu-id="03ed6-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="03ed6-105">Para hacer la mayoría de las cosas en HoloLens, debes estar conectado a una red.</span><span class="sxs-lookup"><span data-stu-id="03ed6-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="03ed6-106">Esta guía te ayudará a:</span><span class="sxs-lookup"><span data-stu-id="03ed6-106">This guide will help you:</span></span>

- <span data-ttu-id="03ed6-107">Conéctate a una red con Wi-Fi o (solo para HoloLens 2) Ethernet a través de USB-C</span><span class="sxs-lookup"><span data-stu-id="03ed6-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="03ed6-108">Deshabilitar y volver a habilitar Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="03ed6-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="03ed6-109">Más información sobre cómo [usar HoloLens sin conexión](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="03ed6-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="03ed6-110">Conectarte por primera vez</span><span class="sxs-lookup"><span data-stu-id="03ed6-110">Connecting for the first time</span></span>

<span data-ttu-id="03ed6-111">La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="03ed6-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="03ed6-112">Si tienes problemas para conectarte a una red Wi-Fi durante la instalación, asegúrate de que tu red es una red abierta protegida con contraseña o una red de portales cautivos.</span><span class="sxs-lookup"><span data-stu-id="03ed6-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="03ed6-113">Asegúrate de que la red no requiera que uses un certificado para conectarte.</span><span class="sxs-lookup"><span data-stu-id="03ed6-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="03ed6-114">Tras la configuración, puedes conectarte a otros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="03ed6-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="03ed6-115">Conexión a una red Wi-Fi después de la configuración</span><span class="sxs-lookup"><span data-stu-id="03ed6-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="03ed6-116">Realiza el **gesto Inicio** y selecciona **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-116">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="03ed6-117">La aplicación Configuración se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="03ed6-117">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="03ed6-118">Selecciona **Red e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="03ed6-119">Asegúrate de que la conexión Wi-Fi está activada.</span><span class="sxs-lookup"><span data-stu-id="03ed6-119">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="03ed6-120">Si no ves la red, desplázate hacia abajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="03ed6-120">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="03ed6-121">Selecciona una red y, a continuación, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-121">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="03ed6-122">Si se te pide una contraseña de red, escríbela y, a continuación, selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-122">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="03ed6-123">HoloLens contiene una radio Wi-Fi 2x2 compatible con 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="03ed6-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="03ed6-124">Conectar HoloLens a una red Wi-Fi es similar a conectar un dispositivo móvil o Windows 10 Desktop a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="03ed6-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configuración de Wi-Fi de HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="03ed6-126">También puedes confirmar que estás conectado a una red Wi-Fi comprobando el estado de Wi-Fi en el menú **Inicio**:</span><span class="sxs-lookup"><span data-stu-id="03ed6-126">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="03ed6-127">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-127">Open the **Start** menu.</span></span>
1. <span data-ttu-id="03ed6-128">Mira el estado de la Wi-Fi en la parte superior izquierda del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-128">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="03ed6-129">Se mostrará el estado de la Wi-Fi y del SSID de la red conectada.</span><span class="sxs-lookup"><span data-stu-id="03ed6-129">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="03ed6-130">Solución de problemas de la conexión a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="03ed6-130">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="03ed6-131">Si tiene problemas para conectarse a una conexión Wi-Fi, consulte [No puedo conectarme a Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="03ed6-131">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="03ed6-132">Cuando inicia sesión en una cuenta de empresa u organización en el dispositivo, también puede aplicar la directiva de Administración de dispositivos móviles (MDM), si su administrador de TI configura la directiva.</span><span class="sxs-lookup"><span data-stu-id="03ed6-132">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="03ed6-133">VPN</span><span class="sxs-lookup"><span data-stu-id="03ed6-133">VPN</span></span>
<span data-ttu-id="03ed6-134">Una conexión VPN puede ayudar a proporcionar una conexión más segura y acceso a la red de su compañía y a Internet.</span><span class="sxs-lookup"><span data-stu-id="03ed6-134">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="03ed6-135">HoloLens 2 es compatible con el cliente VPN integrado y el complemento VPN de la Plataforma universal de Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="03ed6-135">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="03ed6-136">Protocolos VPN integrados compatibles:</span><span class="sxs-lookup"><span data-stu-id="03ed6-136">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="03ed6-137">IKEv2</span><span class="sxs-lookup"><span data-stu-id="03ed6-137">IKEv2</span></span>
- <span data-ttu-id="03ed6-138">L2TP</span><span class="sxs-lookup"><span data-stu-id="03ed6-138">L2TP</span></span>
- <span data-ttu-id="03ed6-139">PPTP</span><span class="sxs-lookup"><span data-stu-id="03ed6-139">PPTP</span></span>

<span data-ttu-id="03ed6-140">Si se usa un certificado para la autenticación del cliente de VPN integrado, el certificado de cliente necesario se debe agregar al almacén de certificados de usuario.</span><span class="sxs-lookup"><span data-stu-id="03ed6-140">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="03ed6-141">Para averiguar si un complemento VPN de terceros es compatible con HoloLens 2, vaya a Store para localizar la aplicación VPN y compruebe si HoloLens se muestra como un dispositivo compatible y en la página de Requisitos del sistema la aplicación es compatible con la arquitectura de ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="03ed6-141">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="03ed6-142">HoloLens solo admite aplicaciones de la Plataforma universal de Windows para VPN de terceros.</span><span class="sxs-lookup"><span data-stu-id="03ed6-142">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="03ed6-143">La VPN no está habilita de forma predeterminada, pero puede habilitarse de forma manual abriendo la aplicación de **Configuración** y yendo a **Red e Internet > VPN**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-143">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="03ed6-144">MDM puede administrar la red privada virtual con [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), y configurada a través de la [directiva Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="03ed6-144">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="03ed6-145">Obtenga más información sobre [cómo configurar la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [estas guías](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="03ed6-145">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="03ed6-146">Deshabilitar Wi-Fi en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="03ed6-146">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="03ed6-147">Usar la aplicación Configuración en HoloLens</span><span class="sxs-lookup"><span data-stu-id="03ed6-147">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="03ed6-148">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-148">Open the **Start** menu.</span></span>
1. <span data-ttu-id="03ed6-149">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-149">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="03ed6-150">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="03ed6-150">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="03ed6-151">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-151">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="03ed6-152">Selecciona el interruptor del control deslizante de Wi-Fi para moverlo a la posición **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-152">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="03ed6-153">Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y deshabilitará todas las características de Wi-Fi en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="03ed6-153">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="03ed6-154">Cuando la radio de Wi-Fi está deshabilitada, HoloLens no podrá cargar automáticamente sus [espacios](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="03ed6-154">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="03ed6-155">Mueve el interruptor del control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="03ed6-155">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="03ed6-156">El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.</span><span class="sxs-lookup"><span data-stu-id="03ed6-156">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="03ed6-157">Identificación de la dirección IP de HoloLens en la red Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="03ed6-157">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="03ed6-158">Mediante la aplicación Configuración</span><span class="sxs-lookup"><span data-stu-id="03ed6-158">By using the Settings app</span></span>

1. <span data-ttu-id="03ed6-159">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-159">Open the **Start** menu.</span></span>
1. <span data-ttu-id="03ed6-160">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-160">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="03ed6-161">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="03ed6-161">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="03ed6-162">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-162">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="03ed6-163">Desplázate hasta debajo de la lista de redes Wi-Fi disponibles y selecciona **Propiedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-163">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propiedades de hardware en configuración de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="03ed6-165">La dirección IP aparece junto a **Dirección IPv4**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-165">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="03ed6-166">Mediante comandos de voz</span><span class="sxs-lookup"><span data-stu-id="03ed6-166">By using voice commands</span></span>

<span data-ttu-id="03ed6-167">Según la compilación de los dispositivos, puede usar los comandos de voz integrados o Cortana para mostrar su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="03ed6-167">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="03ed6-168">En compilaciones posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), di "¿Cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="03ed6-168">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="03ed6-169">y se mostrará.</span><span class="sxs-lookup"><span data-stu-id="03ed6-169">and it will be displayed.</span></span> <span data-ttu-id="03ed6-170">Para compilaciones anteriores o HoloLens (1.ª gen), di "Hola Cortana, ¿cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="03ed6-170">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="03ed6-171">y Cortana mostrará y leerá tu dirección IP.</span><span class="sxs-lookup"><span data-stu-id="03ed6-171">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="03ed6-172">Con el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="03ed6-172">By using Windows Device Portal</span></span>

1. <span data-ttu-id="03ed6-173">En un explorador web de tu PC, abre el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="03ed6-173">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="03ed6-174">Ve a la sección **Redes**.</span><span class="sxs-lookup"><span data-stu-id="03ed6-174">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="03ed6-175">Esta sección muestra tu dirección IP y otra información de la red.</span><span class="sxs-lookup"><span data-stu-id="03ed6-175">This section displays your IP address and other network information.</span></span> <span data-ttu-id="03ed6-176">Con este método, puedes copiar y pegar de la dirección IP en tu PC de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="03ed6-176">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
