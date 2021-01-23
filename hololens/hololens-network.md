---
title: Conectar HoloLens a una red
description: Aprende a configurar y conectar a Internet HoloLens y descubre cómo identificar la dirección IP del dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, inalámbrico, Internet, IP, dirección IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 6d11ae0907aa82df71d7c86bb37996dcce71d845
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283981"
---
# <span data-ttu-id="616ee-104">Conectar HoloLens a una red</span><span class="sxs-lookup"><span data-stu-id="616ee-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="616ee-105">Para hacer la mayoría de las cosas en HoloLens, debes estar conectado a una red.</span><span class="sxs-lookup"><span data-stu-id="616ee-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="616ee-106">Esta guía te ayudará a:</span><span class="sxs-lookup"><span data-stu-id="616ee-106">This guide will help you:</span></span>

- <span data-ttu-id="616ee-107">Conéctate a una red con Wi-Fi o (solo para HoloLens 2) Ethernet a través de USB-C</span><span class="sxs-lookup"><span data-stu-id="616ee-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="616ee-108">Deshabilitar y volver a habilitar Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="616ee-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="616ee-109">Más información sobre cómo [usar HoloLens sin conexión](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="616ee-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="616ee-110">Conectarte por primera vez</span><span class="sxs-lookup"><span data-stu-id="616ee-110">Connecting for the first time</span></span>

<span data-ttu-id="616ee-111">La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="616ee-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="616ee-112">Si tienes problemas para conectarte a una red Wi-Fi durante la instalación, asegúrate de que tu red es una red abierta protegida con contraseña o una red de portales cautivos.</span><span class="sxs-lookup"><span data-stu-id="616ee-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="616ee-113">Asegúrate de que la red no requiera que uses un certificado para conectarte.</span><span class="sxs-lookup"><span data-stu-id="616ee-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="616ee-114">Tras la configuración, puedes conectarte a otros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="616ee-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="616ee-115">En los dispositivos HoloLens 2, un usuario también puede [usar un adaptador USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectarse directamente a la red Wi-Fi para ayudar a configurar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="616ee-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="616ee-116">Una vez que se configure el dispositivo, el usuario puede seguir usando el adaptador, o bien puede desconectar el dispositivo del adaptador y [conectarse a una red Wi-Fi después de configurarlo](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="616ee-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="616ee-117">Conexión a una red Wi-Fi después de la configuración</span><span class="sxs-lookup"><span data-stu-id="616ee-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="616ee-118">Realiza el **gesto Inicio** y selecciona **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="616ee-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="616ee-119">La aplicación Configuración se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="616ee-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="616ee-120">Selecciona **Red e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="616ee-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="616ee-121">Asegúrate de que la conexión Wi-Fi está activada.</span><span class="sxs-lookup"><span data-stu-id="616ee-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="616ee-122">Si no ves la red, desplázate hacia abajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="616ee-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="616ee-123">Selecciona una red y, a continuación, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="616ee-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="616ee-124">Si se te pide una contraseña de red, escríbela y, a continuación, selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="616ee-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="616ee-125">HoloLens contiene una radio Wi-Fi 2x2 compatible con 802.11ac.</span><span class="sxs-lookup"><span data-stu-id="616ee-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="616ee-126">Conectar HoloLens a una red Wi-Fi es similar a conectar un dispositivo móvil o Windows 10 Desktop a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="616ee-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![Configuración de Wi-Fi de HoloLens](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="616ee-128">También puedes confirmar que estás conectado a una red Wi-Fi comprobando el estado de Wi-Fi en el menú **Inicio**:</span><span class="sxs-lookup"><span data-stu-id="616ee-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="616ee-129">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="616ee-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="616ee-130">Mira el estado de la Wi-Fi en la parte superior izquierda del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="616ee-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="616ee-131">Se mostrará el estado de la Wi-Fi y del SSID de la red conectada.</span><span class="sxs-lookup"><span data-stu-id="616ee-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="616ee-132">Solución de problemas de la conexión a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="616ee-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="616ee-133">Si tiene problemas para conectarse a una conexión Wi-Fi, consulte [No puedo conectarme a Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="616ee-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="616ee-134">Cuando inicia sesión en una cuenta de empresa u organización en el dispositivo, también puede aplicar la directiva de Administración de dispositivos móviles (MDM), si su administrador de TI configura la directiva.</span><span class="sxs-lookup"><span data-stu-id="616ee-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="616ee-135">Conectar HoloLens a la red de Wi-Fi empresarial</span><span class="sxs-lookup"><span data-stu-id="616ee-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="616ee-136">Los perfiles de Wi-Fi empresarial usan el Protocolo de Autenticación Extensible (EAP) para autenticar las conexiones Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="616ee-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="616ee-137">El perfil de Wi-Fi empresarial de HoloLens se puede configurar a través de MDM o del paquete de aprovisionamiento creado por el [Diseñador de configuración de Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="616ee-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="616ee-138">Para los dispositivos administrados de Microsoft Intune, consulta [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para ver las instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="616ee-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="616ee-139">Para crear un paquete de aprovisionamiento de Wi-Fi en WCD, se requiere un archivo de perfil Wi-Fi en formato .xml preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="616ee-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="616ee-140">Este es un ejemplo de perfil de Wi-Fi para WPA2-Enterprise con autenticación EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="616ee-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="616ee-141">Según el tipo de EAP, es posible que debas aprovisionar el certificado raíz de la entidad emisora del servidor y el certificado del cliente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="616ee-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="616ee-142">Recursos adicionales:</span><span class="sxs-lookup"><span data-stu-id="616ee-142">Additional resources:</span></span>

- <span data-ttu-id="616ee-143">Esquema de WLANv1Profile: [[MS-GPWL]: esquema de Perfil de LAN inalámbrico v1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="616ee-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="616ee-144">Esquema EAP-TLS: [[MS-GPWL]: esquema EAP TLS de Microsoft | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="616ee-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="616ee-145">Solución de problemas de EAP</span><span class="sxs-lookup"><span data-stu-id="616ee-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="616ee-146">Asegúrate de que el perfil de Wi-Fi tiene la configuración adecuada. Verifica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="616ee-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="616ee-147">El tipo de EAP está configurado correctamente, tipos comunes de EAP: EAP-TLS (13), EAP-TTLS (21) y PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="616ee-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="616ee-148">El nombre de Wi-Fi SSID es correcto y está en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="616ee-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="616ee-149">Para EAP-TLS, TrustedRootCA contiene el hash SHA-1 del certificado de CA raíz de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="616ee-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="616ee-150">En Windows PC, el comando &quot;certutil.exe -dump cert\_file\_name&quot; mostrará una cadena con el hash SHA-1 del certificado.</span><span class="sxs-lookup"><span data-stu-id="616ee-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="616ee-151">Recopila captura de paquetes de red en el punto de acceso o controladora o en los registros del servidor AAA para averiguar dónde se produce un error en la sesión de EAP.</span><span class="sxs-lookup"><span data-stu-id="616ee-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="616ee-152">Si la identidad de EAP proporcionada por HoloLens no es la esperada, comprueba si la identidad se ha aprovisionado correctamente mediante el perfil de Wi-Fi o el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="616ee-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="616ee-153">Si el servidor rechaza el certificado de cliente de HoloLens, comprueba si el certificado de cliente necesario se ha aprovisionado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="616ee-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="616ee-154">Si HoloLens rechaza el certificado de servidor, comprueba si el certificado CA raíz del servidor se ha aprovisionado en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="616ee-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="616ee-155">Si el perfil de empresa se aprovisiona mediante el paquete de aprovisionamiento Wi-Fi, plantéate aplicar el paquete de aprovisionamiento en un equipo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="616ee-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="616ee-156">Si el error se produce incluso en un PC con Windows 10, sigue la [Guía de solución de problemas de autenticación en 802.1X en cliente de Windows](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="616ee-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="616ee-157">Envíanos tus comentarios a través del [Centro de opiniones](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="616ee-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="616ee-158">Recursos adicionales:</span><span class="sxs-lookup"><span data-stu-id="616ee-158">Additional resources:</span></span>
- [<span data-ttu-id="616ee-159">Exportar la configuración de Wi-Fi desde un dispositivo de Windows.</span><span class="sxs-lookup"><span data-stu-id="616ee-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="616ee-160">VPN</span><span class="sxs-lookup"><span data-stu-id="616ee-160">VPN</span></span>
<span data-ttu-id="616ee-161">Una conexión VPN puede ayudar a proporcionar una conexión más segura y acceso a la red de su compañía y a Internet.</span><span class="sxs-lookup"><span data-stu-id="616ee-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="616ee-162">HoloLens 2 es compatible con el cliente VPN integrado y el complemento VPN de la Plataforma universal de Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="616ee-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="616ee-163">Protocolos VPN integrados compatibles:</span><span class="sxs-lookup"><span data-stu-id="616ee-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="616ee-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="616ee-164">IKEv2</span></span>
- <span data-ttu-id="616ee-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="616ee-165">L2TP</span></span>
- <span data-ttu-id="616ee-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="616ee-166">PPTP</span></span>

<span data-ttu-id="616ee-167">Si se usa un certificado para la autenticación del cliente de VPN integrado, el certificado de cliente necesario se debe agregar al almacén de certificados de usuario.</span><span class="sxs-lookup"><span data-stu-id="616ee-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="616ee-168">Para averiguar si un complemento VPN de terceros es compatible con HoloLens 2, vaya a Store para localizar la aplicación VPN y compruebe si HoloLens se muestra como un dispositivo compatible y en la página de Requisitos del sistema la aplicación es compatible con la arquitectura de ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="616ee-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="616ee-169">HoloLens solo admite aplicaciones de la Plataforma universal de Windows para VPN de terceros.</span><span class="sxs-lookup"><span data-stu-id="616ee-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="616ee-170">MDM puede administrar una VPN con [Configuración/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), y se puede configurar a través de la [directiva Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="616ee-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="616ee-171">Obtén más información sobre [cómo configurar la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [estas guías](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="616ee-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="616ee-172">VPN a través de la IU</span><span class="sxs-lookup"><span data-stu-id="616ee-172">VPN via UI</span></span>

<span data-ttu-id="616ee-173">La VPN no está habilita de forma predeterminada, pero puede habilitarse de forma manual abriendo la aplicación de **Configuración** y yendo a **Red e Internet > VPN**.</span><span class="sxs-lookup"><span data-stu-id="616ee-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="616ee-174">Selecciona un proveedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="616ee-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="616ee-175">Crea un nombre de conexión.</span><span class="sxs-lookup"><span data-stu-id="616ee-175">Create a connection name.</span></span> 
1. <span data-ttu-id="616ee-176">Escribe el nombre o la dirección del servidor.</span><span class="sxs-lookup"><span data-stu-id="616ee-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="616ee-177">Selecciona el tipo de VPN.</span><span class="sxs-lookup"><span data-stu-id="616ee-177">Select the VPN type.</span></span>
1. <span data-ttu-id="616ee-178">Selecciona el tipo de información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="616ee-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="616ee-179">Opcionalmente, puedes agregar un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="616ee-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="616ee-180">Aplica la configuración de VPN.</span><span class="sxs-lookup"><span data-stu-id="616ee-180">Apply the VPN settings.</span></span> 

![Configuración de VPN de HoloLens](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="616ee-182">Configurar una VPN mediante el paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="616ee-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="616ee-183">En nuestra versión 20H2 de Windows Holographic hemos corregido un problema de configuración de proxy para la conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="616ee-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="616ee-184">Si tienes previsto usar este flujo, considera la posibilidad de actualizar los dispositivos de esta compilación.</span><span class="sxs-lookup"><span data-stu-id="616ee-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="616ee-185">Inicia el Diseñador de configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="616ee-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="616ee-186">Haz clic en **Aprovisionar dispositivos HoloLens**, selecciona el dispositivo de destino y, luego, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="616ee-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="616ee-187">Escribe el nombre y la ruta del paquete.</span><span class="sxs-lookup"><span data-stu-id="616ee-187">Enter package name and path.</span></span>
1. <span data-ttu-id="616ee-188">Haz clic en **Cambiar a editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="616ee-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="616ee-189">Abre **Configuración de tiempo de ejecución** -> **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="616ee-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="616ee-190">Configura VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="616ee-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="616ee-191">Selecciona ProfileType: **Nativo** o de **Tercero**.</span><span class="sxs-lookup"><span data-stu-id="616ee-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="616ee-192">En perfil Nativo, selecciona **NativeProtocolType** y, a continuación, configura el servidor, la directiva de enrutamiento, el tipo de autenticación y otras opciones.</span><span class="sxs-lookup"><span data-stu-id="616ee-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="616ee-193">Para el perfil "Tercero", configura la dirección URL del servidor, el nombre de familia del paquete de la aplicación del complemento VPN (solo 3 predefinidos) y las configuraciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="616ee-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="616ee-194">Exporta el paquete.</span><span class="sxs-lookup"><span data-stu-id="616ee-194">Export your package.</span></span>
1. <span data-ttu-id="616ee-195">Conecta tu HoloLens y copia el archivo .ppkg en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="616ee-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="616ee-196">En HoloLens, aplica el .ppkg de VPN abriendo el menú Inicio y seleccionando **Configuración** -> **Cuenta** -> **Acceder a trabajo o escuela** -> **Agregar o quitar el paquete de aprovisionamiento** -> Selecciona tu paquete de VPN.</span><span class="sxs-lookup"><span data-stu-id="616ee-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="616ee-197">Configuración de VPN a través de Intune</span><span class="sxs-lookup"><span data-stu-id="616ee-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="616ee-198">Solo tienes que seguir los documentos de Intune para comenzar.</span><span class="sxs-lookup"><span data-stu-id="616ee-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="616ee-199">Cuando sigas estos pasos debes tener en cuenta los protocolos VPN integrados que admiten los dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="616ee-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="616ee-200">[Crear perfiles de VPN para conectarse a servidores VPN en Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="616ee-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="616ee-201">[Configuración de dispositivos con Windows 10 y Windows Holographic para agregar conexiones VPN mediante Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="616ee-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="616ee-202">Cuando termines, recuerda [asignar el perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="616ee-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="616ee-203">VPN a través de soluciones MDM de terceros</span><span class="sxs-lookup"><span data-stu-id="616ee-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="616ee-204">Ejemplo de conexión VPN de terceros:</span><span class="sxs-lookup"><span data-stu-id="616ee-204">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="616ee-205">Ejemplo de VPN IKEv2 nativa:</span><span class="sxs-lookup"><span data-stu-id="616ee-205">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <span data-ttu-id="616ee-206">Deshabilitar Wi-Fi en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="616ee-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="616ee-207">Usar la aplicación Configuración en HoloLens</span><span class="sxs-lookup"><span data-stu-id="616ee-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="616ee-208">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="616ee-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="616ee-209">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="616ee-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="616ee-210">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="616ee-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="616ee-211">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="616ee-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="616ee-212">Selecciona el interruptor del control deslizante de Wi-Fi para moverlo a la posición **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="616ee-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="616ee-213">Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y deshabilitará todas las características de Wi-Fi en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="616ee-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="616ee-214">Cuando la radio de Wi-Fi está deshabilitada, HoloLens no podrá cargar automáticamente sus [espacios](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="616ee-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="616ee-215">Mueve el interruptor del control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="616ee-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="616ee-216">El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.</span><span class="sxs-lookup"><span data-stu-id="616ee-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="616ee-217">Identificación de la dirección IP de HoloLens en la red Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="616ee-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="616ee-218">Mediante la aplicación Configuración</span><span class="sxs-lookup"><span data-stu-id="616ee-218">By using the Settings app</span></span>

1. <span data-ttu-id="616ee-219">Abre el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="616ee-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="616ee-220">Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="616ee-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="616ee-221">La aplicación **Configuración** se colocará automáticamente delante de ti.</span><span class="sxs-lookup"><span data-stu-id="616ee-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="616ee-222">Selecciona **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="616ee-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="616ee-223">Desplázate hasta debajo de la lista de redes Wi-Fi disponibles y selecciona **Propiedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="616ee-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propiedades de hardware en configuración de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="616ee-225">La dirección IP aparece junto a **Dirección IPv4**.</span><span class="sxs-lookup"><span data-stu-id="616ee-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="616ee-226">Mediante comandos de voz</span><span class="sxs-lookup"><span data-stu-id="616ee-226">By using voice commands</span></span>

<span data-ttu-id="616ee-227">Según la compilación de los dispositivos, puede usar los comandos de voz integrados o Cortana para mostrar su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="616ee-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="616ee-228">En compilaciones posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), di "¿Cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="616ee-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="616ee-229">y se mostrará.</span><span class="sxs-lookup"><span data-stu-id="616ee-229">and it will be displayed.</span></span> <span data-ttu-id="616ee-230">Para compilaciones anteriores o HoloLens (1.ª gen), di "Hola Cortana, ¿cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="616ee-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="616ee-231">y Cortana mostrará y leerá tu dirección IP.</span><span class="sxs-lookup"><span data-stu-id="616ee-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="616ee-232">Con el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="616ee-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="616ee-233">En un explorador web de tu PC, abre el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="616ee-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="616ee-234">Ve a la sección **Redes**.</span><span class="sxs-lookup"><span data-stu-id="616ee-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="616ee-235">Esta sección muestra tu dirección IP y otra información de la red.</span><span class="sxs-lookup"><span data-stu-id="616ee-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="616ee-236">Con este método, puedes copiar y pegar de la dirección IP en tu PC de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="616ee-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
