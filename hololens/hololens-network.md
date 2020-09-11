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
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009528"
---
# <span data-ttu-id="f09c9-104">Conectar HoloLens a una red</span><span class="sxs-lookup"><span data-stu-id="f09c9-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="f09c9-105">Para hacer la mayoría de las cosas en HoloLens, debes estar conectado a una red.</span><span class="sxs-lookup"><span data-stu-id="f09c9-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="f09c9-106">Esta guía te ayudará a:</span><span class="sxs-lookup"><span data-stu-id="f09c9-106">This guide will help you:</span></span>

- <span data-ttu-id="f09c9-107">Conéctate a una red con Wi-Fi o (solo para HoloLens 2) Ethernet a través de USB-C</span><span class="sxs-lookup"><span data-stu-id="f09c9-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="f09c9-108">Deshabilitar y volver a habilitar Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f09c9-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="f09c9-109">Más información sobre cómo [usar HoloLens sin conexión](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="f09c9-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="f09c9-110">Conectarte por primera vez</span><span class="sxs-lookup"><span data-stu-id="f09c9-110">Connecting for the first time</span></span>

<span data-ttu-id="f09c9-111">La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="f09c9-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="f09c9-112">Si tienes problemas para conectarte a una red Wi-Fi durante la instalación, asegúrate de que tu red es una red abierta protegida con contraseña o una red de portales cautivos.</span><span class="sxs-lookup"><span data-stu-id="f09c9-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="f09c9-113">Asegúrate de que la red no requiera que uses un certificado para conectarte.</span><span class="sxs-lookup"><span data-stu-id="f09c9-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="f09c9-114">Tras la configuración, puedes conectarte a otros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="f09c9-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="f09c9-115">En los dispositivos HoloLens 2, un usuario también puede [usar un adaptador USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectarse directamente a la red Wi-Fi para ayudar a configurar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f09c9-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="f09c9-116">Una vez que se configure el dispositivo, el usuario puede seguir usando el adaptador, o bien puede desconectar el dispositivo del adaptador y [conectarse a una red Wi-Fi después de configurarlo](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="f09c9-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="f09c9-117">Conexión a una red Wi-Fi después de la configuración</span><span class="sxs-lookup"><span data-stu-id="f09c9-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="f09c9-118">Realiza el **gesto Inicio** y selecciona **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="f09c9-119">La aplicación Configuración se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="f09c9-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="f09c9-120">Selecciona **Red e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="f09c9-121">Asegúrate de que la conexión Wi-Fi está activada.</span><span class="sxs-lookup"><span data-stu-id="f09c9-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="f09c9-122">Si no ves la red, desplázate hacia abajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="f09c9-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="f09c9-123">Selecciona una red y, a continuación, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="f09c9-124">Si se te pide una contraseña de red, escríbela y, a continuación, selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="f09c9-125">HoloLens contiene una radio Wi-Fi 2x2 compatible con 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="f09c9-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="f09c9-126">Conectar HoloLens a una red Wi-Fi es similar a conectar un dispositivo móvil o Windows 10 Desktop a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="f09c9-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configuración de Wi-Fi de HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="f09c9-128">También puedes confirmar que estás conectado a una red Wi-Fi comprobando el estado de Wi-Fi en el menú **Inicio**:</span><span class="sxs-lookup"><span data-stu-id="f09c9-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="f09c9-129">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="f09c9-130">Mira el estado de la Wi-Fi en la parte superior izquierda del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="f09c9-131">Se mostrará el estado de la Wi-Fi y del SSID de la red conectada.</span><span class="sxs-lookup"><span data-stu-id="f09c9-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="f09c9-132">Solución de problemas de la conexión a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f09c9-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="f09c9-133">Si tiene problemas para conectarse a una conexión Wi-Fi, consulte [No puedo conectarme a Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="f09c9-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="f09c9-134">Cuando inicia sesión en una cuenta de empresa u organización en el dispositivo, también puede aplicar la directiva de Administración de dispositivos móviles (MDM), si su administrador de TI configura la directiva.</span><span class="sxs-lookup"><span data-stu-id="f09c9-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="f09c9-135">VPN</span><span class="sxs-lookup"><span data-stu-id="f09c9-135">VPN</span></span>
<span data-ttu-id="f09c9-136">Una conexión VPN puede ayudar a proporcionar una conexión más segura y acceso a la red de su compañía y a Internet.</span><span class="sxs-lookup"><span data-stu-id="f09c9-136">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="f09c9-137">HoloLens 2 es compatible con el cliente VPN integrado y el complemento VPN de la Plataforma universal de Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="f09c9-137">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="f09c9-138">Protocolos VPN integrados compatibles:</span><span class="sxs-lookup"><span data-stu-id="f09c9-138">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="f09c9-139">IKEv2</span><span class="sxs-lookup"><span data-stu-id="f09c9-139">IKEv2</span></span>
- <span data-ttu-id="f09c9-140">L2TP</span><span class="sxs-lookup"><span data-stu-id="f09c9-140">L2TP</span></span>
- <span data-ttu-id="f09c9-141">PPTP</span><span class="sxs-lookup"><span data-stu-id="f09c9-141">PPTP</span></span>

<span data-ttu-id="f09c9-142">Si se usa un certificado para la autenticación del cliente de VPN integrado, el certificado de cliente necesario se debe agregar al almacén de certificados de usuario.</span><span class="sxs-lookup"><span data-stu-id="f09c9-142">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="f09c9-143">Para averiguar si un complemento VPN de terceros es compatible con HoloLens 2, vaya a Store para localizar la aplicación VPN y compruebe si HoloLens se muestra como un dispositivo compatible y en la página de Requisitos del sistema la aplicación es compatible con la arquitectura de ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="f09c9-143">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="f09c9-144">HoloLens solo admite aplicaciones de la Plataforma universal de Windows para VPN de terceros.</span><span class="sxs-lookup"><span data-stu-id="f09c9-144">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="f09c9-145">La VPN no está habilita de forma predeterminada, pero puede habilitarse de forma manual abriendo la aplicación de **Configuración** y yendo a **Red e Internet > VPN**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-145">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="f09c9-146">MDM puede administrar la red privada virtual con [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), y configurada a través de la [directiva Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="f09c9-146">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="f09c9-147">Obtenga más información sobre [cómo configurar la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [estas guías](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="f09c9-147">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="f09c9-148">Deshabilitar Wi-Fi en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="f09c9-148">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="f09c9-149">Usar la aplicación Configuración en HoloLens</span><span class="sxs-lookup"><span data-stu-id="f09c9-149">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="f09c9-150">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-150">Open the **Start** menu.</span></span>
1. <span data-ttu-id="f09c9-151">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-151">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="f09c9-152">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="f09c9-152">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="f09c9-153">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-153">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="f09c9-154">Selecciona el interruptor del control deslizante de Wi-Fi para moverlo a la posición **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-154">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="f09c9-155">Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y deshabilitará todas las características de Wi-Fi en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f09c9-155">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f09c9-156">Cuando la radio de Wi-Fi está deshabilitada, HoloLens no podrá cargar automáticamente sus [espacios](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="f09c9-156">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="f09c9-157">Mueve el interruptor del control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f09c9-157">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="f09c9-158">El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.</span><span class="sxs-lookup"><span data-stu-id="f09c9-158">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="f09c9-159">Identificación de la dirección IP de HoloLens en la red Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f09c9-159">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="f09c9-160">Mediante la aplicación Configuración</span><span class="sxs-lookup"><span data-stu-id="f09c9-160">By using the Settings app</span></span>

1. <span data-ttu-id="f09c9-161">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-161">Open the **Start** menu.</span></span>
1. <span data-ttu-id="f09c9-162">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-162">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="f09c9-163">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="f09c9-163">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="f09c9-164">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-164">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="f09c9-165">Desplázate hasta debajo de la lista de redes Wi-Fi disponibles y selecciona **Propiedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-165">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propiedades de hardware en configuración de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="f09c9-167">La dirección IP aparece junto a **Dirección IPv4**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-167">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="f09c9-168">Mediante comandos de voz</span><span class="sxs-lookup"><span data-stu-id="f09c9-168">By using voice commands</span></span>

<span data-ttu-id="f09c9-169">Según la compilación de los dispositivos, puede usar los comandos de voz integrados o Cortana para mostrar su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="f09c9-169">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="f09c9-170">En compilaciones posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), di "¿Cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="f09c9-170">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="f09c9-171">y se mostrará.</span><span class="sxs-lookup"><span data-stu-id="f09c9-171">and it will be displayed.</span></span> <span data-ttu-id="f09c9-172">Para compilaciones anteriores o HoloLens (1.ª gen), di "Hola Cortana, ¿cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="f09c9-172">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="f09c9-173">y Cortana mostrará y leerá tu dirección IP.</span><span class="sxs-lookup"><span data-stu-id="f09c9-173">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="f09c9-174">Con el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="f09c9-174">By using Windows Device Portal</span></span>

1. <span data-ttu-id="f09c9-175">En un explorador web de tu PC, abre el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="f09c9-175">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="f09c9-176">Ve a la sección **Redes**.</span><span class="sxs-lookup"><span data-stu-id="f09c9-176">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="f09c9-177">Esta sección muestra tu dirección IP y otra información de la red.</span><span class="sxs-lookup"><span data-stu-id="f09c9-177">This section displays your IP address and other network information.</span></span> <span data-ttu-id="f09c9-178">Con este método, puedes copiar y pegar de la dirección IP en tu PC de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f09c9-178">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
