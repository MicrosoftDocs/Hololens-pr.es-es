---
title: Conexión de HoloLens a una red
description: Aprenda a configurar el dispositivo HoloLens y a conectarse con él a Internet, y descubra cómo identificar la dirección IP del dispositivo.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, inalámbrico, Internet, IP, dirección IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923608"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="b9586-104">Conexión de HoloLens a una red</span><span class="sxs-lookup"><span data-stu-id="b9586-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="b9586-105">La mayoría de las actividades que se realizan con HoloLens requieren estar conectado a una red.</span><span class="sxs-lookup"><span data-stu-id="b9586-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="b9586-106">HoloLens contiene una radio 2x2 Wi-Fi compatible con 802.11ac; conectarlo este dispositivo a una red es similar a conectar un dispositivo de escritorio o móvil de Windows 10 a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b9586-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="b9586-107">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="b9586-107">This guide will help you:</span></span>

- <span data-ttu-id="b9586-108">Conectarse a una red con Wi-Fi o, solo para HoloLens 2, con Wi-Fi Direct o Ethernet por medio de USB-C.</span><span class="sxs-lookup"><span data-stu-id="b9586-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="b9586-109">Deshabilitar y volver a habilitar la red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b9586-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="b9586-110">Obtenga más información sobre el [uso de HoloLens sin conexión](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="b9586-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="b9586-111">Conexión por primera vez</span><span class="sxs-lookup"><span data-stu-id="b9586-111">Connecting for the first time</span></span>

<span data-ttu-id="b9586-112">La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b9586-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="b9586-113">Si tiene problemas para conectarse a una red Wi-Fi durante la instalación, asegúrese de que se trata de una red abierta, protegida con contraseña o una red de portales cautivos.</span><span class="sxs-lookup"><span data-stu-id="b9586-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="b9586-114">Además, confirme que la red no requiere que use un certificado para conectarse.</span><span class="sxs-lookup"><span data-stu-id="b9586-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="b9586-115">Tras la configuración, puede conectarse a otros tipos de redes Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b9586-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="b9586-116">En los dispositivos HoloLens 2, un usuario también puede usar un [adaptador de USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectarse directamente a la red Wi-Fi como ayuda para configurar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9586-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="b9586-117">Una vez configurado el dispositivo, el usuario puede seguir usando el adaptador o puede desconectar el dispositivo del adaptador y [conectarse a una red Wi-Fi después de la configuración](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="b9586-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="b9586-118">Conexión a una red Wi-Fi después de la configuración</span><span class="sxs-lookup"><span data-stu-id="b9586-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="b9586-119">Haga el **gesto Inicio** y seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="b9586-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="b9586-120">La aplicación Configuración se colocará delante automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b9586-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b9586-121">Seleccione **Red e Internet** > **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="b9586-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="b9586-122">Asegúrese de que la conexión Wi-Fi está activada.</span><span class="sxs-lookup"><span data-stu-id="b9586-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="b9586-123">Si no ve la red, desplácese hacia abajo de la lista.</span><span class="sxs-lookup"><span data-stu-id="b9586-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="b9586-124">Seleccione una red y, a continuación, **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b9586-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="b9586-125">Si se le pide una contraseña de red, escríbala y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b9586-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Configuración de Wi-Fi de HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="b9586-127">Para confirmar que está conectado a una red Wi-Fi, compruebe el estado de la red en el menú **Inicio**:</span><span class="sxs-lookup"><span data-stu-id="b9586-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="b9586-128">Abra el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b9586-129">Consulte el estado de la red Wi-Fi en la parte superior izquierda del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="b9586-130">Se mostrará el estado de la red Wi-Fi y del SSID de la red conectada.</span><span class="sxs-lookup"><span data-stu-id="b9586-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="b9586-131">Si la red Wi-Fi no está disponible, también puede [conectarse a redes de telefonía móvil y 5G](hololens-cellular.md).</span><span class="sxs-lookup"><span data-stu-id="b9586-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9586-132">Por diseño, los usuarios no pueden ajustar el comportamiento de itinerancia de Wi-Fi del dispositivo HoloLens 2; **la única manera de actualizar la lista de redes Wi-Fi es activar y desactivar la conexión a Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="b9586-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="b9586-133">Esto evita muchos problemas, como que un dispositivo se quede "atascado" en una AP cuando está fuera del rango.</span><span class="sxs-lookup"><span data-stu-id="b9586-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="b9586-134">Conexión de HoloLens a la red Wi-Fi empresarial</span><span class="sxs-lookup"><span data-stu-id="b9586-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="b9586-135">Los perfiles de Wi-Fi empresarial usan el protocolo de autenticación extensible (EAP) para autenticar las conexiones Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b9586-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="b9586-136">El perfil de Wi-Fi empresarial de HoloLens se puede configurar por medio de MDM o del paquete de aprovisionamiento creado por [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="b9586-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="b9586-137">En el caso de los dispositivos administrados de Microsoft Intune, consulte las instrucciones de configuración en la información para [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).</span><span class="sxs-lookup"><span data-stu-id="b9586-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="b9586-138">Para crear un paquete de aprovisionamiento de Wi-Fi en WCD, se requiere un archivo de perfil Wi-Fi en formato .xml preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="b9586-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="b9586-139">Este es un ejemplo de perfil de Wi-Fi para WPA2-Enterprise con autenticación EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="b9586-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="b9586-140">Según el tipo de EAP, es posible que deba aprovisionar el certificado de entidad de certificación raíz del servidor y el certificado del cliente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9586-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="b9586-141">Recursos adicionales:</span><span class="sxs-lookup"><span data-stu-id="b9586-141">Additional resources:</span></span>

- <span data-ttu-id="b9586-142">Esquema de perfil WLANv1: [[MS-GPWL]: Esquema de perfil de LAN inalámbrica v1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="b9586-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="b9586-143">Esquema EAP-TLS: [[MS-GPWL]: Esquema TLS de Microsoft EAP | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="b9586-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="b9586-144">Consulte nuestra página de [solución de problemas](hololens2-enterprise-troubleshooting.md#) si tiene problemas para conectarse a la red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b9586-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="b9586-145">Configuración del proxy de red</span><span class="sxs-lookup"><span data-stu-id="b9586-145">Configure Network Proxy</span></span>

<span data-ttu-id="b9586-146">En esta sección se explica la configuración del proxy de red para el sistema operativo de HoloLens y las aplicaciones de la Plataforma universal de Windows (UWP) mediante la pila HTTP de Windows.</span><span class="sxs-lookup"><span data-stu-id="b9586-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="b9586-147">Las aplicaciones que usan una pila HTTP que no es Windows pueden tener su propia configuración y control de proxy.</span><span class="sxs-lookup"><span data-stu-id="b9586-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="b9586-148">Configuraciones de proxy</span><span class="sxs-lookup"><span data-stu-id="b9586-148">Proxy Configurations</span></span> 

- <span data-ttu-id="b9586-149">Script de configuración automática (PAC) de proxy: un [archivo PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (abre un sitio que no es de Microsoft) contiene una función de JavaScript FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="b9586-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="b9586-150">Proxy estático: en forma de Servidor:Puerto.</span><span class="sxs-lookup"><span data-stu-id="b9586-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="b9586-151">Protocolo de detección automática de proxy web (WPAD): proporcione la dirección URL del archivo de configuración de proxy por medio de DHCP o DNS.</span><span class="sxs-lookup"><span data-stu-id="b9586-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="b9586-152">Métodos de aprovisionamiento de proxies</span><span class="sxs-lookup"><span data-stu-id="b9586-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="b9586-153">Hay tres formas de aprovisionar proxies:</span><span class="sxs-lookup"><span data-stu-id="b9586-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="b9586-154">**Interfaz de usuario Configuración:**</span><span class="sxs-lookup"><span data-stu-id="b9586-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="b9586-155">Proxy por usuario (20H2 o anterior):</span><span class="sxs-lookup"><span data-stu-id="b9586-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="b9586-156">Abra el menú Inicio y seleccione Configuración.</span><span class="sxs-lookup"><span data-stu-id="b9586-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="b9586-157">Seleccione Red e Internet y, después, Proxy en el menú izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b9586-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="b9586-158">Desplácese hacia abajo hasta la configuración manual del proxy y active Usar un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="b9586-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="b9586-159">Escriba la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="b9586-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="b9586-160">Escriba el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="b9586-160">Enter the port number.</span></span>
        6. <span data-ttu-id="b9586-161">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b9586-161">Click Save.</span></span>
      1. <span data-ttu-id="b9586-162">Proxy de Wi-Fi (21H1 o posterior):</span><span class="sxs-lookup"><span data-stu-id="b9586-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="b9586-163">Abra el menú Inicio y vaya a la página de propiedades de la red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b9586-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="b9586-164">Desplácese hacia abajo hasta Proxy.</span><span class="sxs-lookup"><span data-stu-id="b9586-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="b9586-165">Cambie a la configuración manual.</span><span class="sxs-lookup"><span data-stu-id="b9586-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="b9586-166">Escriba la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="b9586-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="b9586-167">Escriba el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="b9586-167">Enter the port number.</span></span>
          1. <span data-ttu-id="b9586-168">Haga clic en Aplicar.</span><span class="sxs-lookup"><span data-stu-id="b9586-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="b9586-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="b9586-169">**MDM**</span></span> 
     1. <span data-ttu-id="b9586-170">Intune: siga estos [pasos](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para configurar el proxy en Intune.</span><span class="sxs-lookup"><span data-stu-id="b9586-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="b9586-171">Tendrá que desplazarse hasta la parte inferior de la sección.</span><span class="sxs-lookup"><span data-stu-id="b9586-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="b9586-172">Otras soluciones MDM de terceros: use un [CSP de Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="b9586-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="b9586-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="b9586-173">**PPKG**</span></span> 
    1. <span data-ttu-id="b9586-174">Abra Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="b9586-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="b9586-175">Haga clic en Advanced Provisioning (Aprovisionamiento avanzado), escriba el nombre del nuevo proyecto y haga clic en Next (Siguiente).</span><span class="sxs-lookup"><span data-stu-id="b9586-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="b9586-176">Seleccione Windows Holographic (HoloLens 2) y haga clic en Next (Siguiente).</span><span class="sxs-lookup"><span data-stu-id="b9586-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="b9586-177">Importe el archivo PPKG (opcional) y haga clic en Finish (Finalizar).</span><span class="sxs-lookup"><span data-stu-id="b9586-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="b9586-178">Expanda Runtime Settings (Configuración del entorno de ejecución) -> Connectivity Profiles (Perfiles de conectividad) -> WLAN -> WLAN Proxy (Proxy de WLAN).</span><span class="sxs-lookup"><span data-stu-id="b9586-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="b9586-179">Escriba el SSID de la red Wi-Fi y haga clic en Add (Agregar).</span><span class="sxs-lookup"><span data-stu-id="b9586-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="b9586-180">Seleccione la red Wi-Fi en la ventana izquierda y escriba las personalizaciones deseadas.</span><span class="sxs-lookup"><span data-stu-id="b9586-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="b9586-181">Las personalizaciones habilitadas se mostrarán en negrita en el menú izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b9586-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="b9586-182">Haga clic en Save and Exit (Guardar y salir).</span><span class="sxs-lookup"><span data-stu-id="b9586-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="b9586-183">[Aplique](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) el paquete de aprovisionamiento al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9586-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="b9586-184">Los [CSP](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) están detrás de muchas de las tareas y directivas de administración de Windows 10, tanto en Microsoft Intune como en proveedores de servicios de MDM que no son de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9586-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="b9586-185">También puede usar [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) para crear un [paquete de aprovisionamiento](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) y aplicarlo al dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b9586-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="b9586-186">Los CSP que se aplicarán con más probabilidad al dispositivo HoloLens 2 son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9586-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="b9586-187">[CSP de Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): proxy de Wi-Fi por perfil</span><span class="sxs-lookup"><span data-stu-id="b9586-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="b9586-188">Otros CSP admitidos en dispositivos HoloLens</span><span class="sxs-lookup"><span data-stu-id="b9586-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="b9586-189">VPN</span><span class="sxs-lookup"><span data-stu-id="b9586-189">VPN</span></span>
<span data-ttu-id="b9586-190">Una conexión VPN puede ayudar a proporcionar una conexión más segura y acceso a la red de su compañía y a Internet.</span><span class="sxs-lookup"><span data-stu-id="b9586-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="b9586-191">HoloLens 2 es compatible con el cliente VPN integrado y el complemento VPN de la Plataforma universal de Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="b9586-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="b9586-192">Protocolos VPN integrados compatibles:</span><span class="sxs-lookup"><span data-stu-id="b9586-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="b9586-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="b9586-193">IKEv2</span></span>
- <span data-ttu-id="b9586-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="b9586-194">L2TP</span></span>
- <span data-ttu-id="b9586-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="b9586-195">PPTP</span></span>

<span data-ttu-id="b9586-196">Si se usa un certificado para la autenticación del cliente de VPN integrado, el certificado de cliente necesario se debe agregar al almacén de certificados de usuario.</span><span class="sxs-lookup"><span data-stu-id="b9586-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="b9586-197">Para averiguar si un complemento VPN de terceros es compatible con HoloLens 2, vaya a Store para localizar la aplicación VPN, compruebe si HoloLens se muestra como un dispositivo compatible y si en la página de requisitos del sistema se indica que la aplicación es compatible con la arquitectura de ARM o ARM64.</span><span class="sxs-lookup"><span data-stu-id="b9586-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="b9586-198">HoloLens solo admite aplicaciones de la Plataforma universal de Windows para VPN de terceros.</span><span class="sxs-lookup"><span data-stu-id="b9586-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="b9586-199">LA VPN se puede administrar mediante MDM por medio de [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) y se puede establecer por medio de la [directiva Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="b9586-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="b9586-200">Obtenga más información sobre [cómo configurar VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [estas guías](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="b9586-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="b9586-201">VPN por medio de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b9586-201">VPN via UI</span></span>

<span data-ttu-id="b9586-202">La opción de VPN no está habilita de forma predeterminada, pero puede habilitarse de forma manual abriendo la aplicación **Configuración** y yendo a **Red e Internet -> VPN**.</span><span class="sxs-lookup"><span data-stu-id="b9586-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="b9586-203">Seleccione un proveedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="b9586-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="b9586-204">Cree un nombre de conexión.</span><span class="sxs-lookup"><span data-stu-id="b9586-204">Create a connection name.</span></span> 
1. <span data-ttu-id="b9586-205">Escriba el nombre o la dirección del servidor.</span><span class="sxs-lookup"><span data-stu-id="b9586-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="b9586-206">Seleccione el tipo de VPN.</span><span class="sxs-lookup"><span data-stu-id="b9586-206">Select the VPN type.</span></span>
1. <span data-ttu-id="b9586-207">Seleccione el tipo de información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b9586-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="b9586-208">Opcionalmente, puede agregar un nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="b9586-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="b9586-209">Aplique la configuración de VPN.</span><span class="sxs-lookup"><span data-stu-id="b9586-209">Apply the VPN settings.</span></span> 

![Configuración de VPN de HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="b9586-211">Configuración de una VPN mediante el paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="b9586-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="b9586-212">En Windows Holographic, versión 20H2, hemos corregido un problema de configuración de proxy para la conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="b9586-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="b9586-213">Si tiene previsto usar este flujo, considere la posibilidad de actualizar los dispositivos a esta compilación.</span><span class="sxs-lookup"><span data-stu-id="b9586-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="b9586-214">Inicie Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="b9586-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="b9586-215">Haga clic en **Provision HoloLens devices** (Aprovisionar dispositivos HoloLens) y, a continuación, seleccione el dispositivo de destino y **Next** (Siguiente).</span><span class="sxs-lookup"><span data-stu-id="b9586-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="b9586-216">Escribe el nombre y la ruta del paquete.</span><span class="sxs-lookup"><span data-stu-id="b9586-216">Enter package name and path.</span></span>
1. <span data-ttu-id="b9586-217">Haga clic en **Switch to advanced editor** (Cambiar al editor avanzado).</span><span class="sxs-lookup"><span data-stu-id="b9586-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="b9586-218">Abra **Runtime settings (Configuración del entorno de ejecución)**  -> **ConnectivityProfiles** -> **VPN** -> **VPNSetting**.</span><span class="sxs-lookup"><span data-stu-id="b9586-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="b9586-219">Configure el nombre de perfil de VPN.</span><span class="sxs-lookup"><span data-stu-id="b9586-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="b9586-220">Seleccione el valor de ProfileType: **Native** (Nativo) o **Third Party** (Terceros).</span><span class="sxs-lookup"><span data-stu-id="b9586-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="b9586-221">En el perfil nativo, seleccione **NativeProtocolType** y, a continuación, configure el servidor, la directiva de enrutamiento, el tipo de autenticación y otras opciones.</span><span class="sxs-lookup"><span data-stu-id="b9586-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="b9586-222">En el perfil de terceros, configure la dirección URL del servidor, el nombre de familia del paquete de la aplicación del complemento VPN (solo 3 predefinidos) y las configuraciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b9586-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="b9586-223">Exporte el paquete.</span><span class="sxs-lookup"><span data-stu-id="b9586-223">Export your package.</span></span>
1. <span data-ttu-id="b9586-224">Conéctese al dispositivo HoloLens y copie en él el archivo .ppkg.</span><span class="sxs-lookup"><span data-stu-id="b9586-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="b9586-225">En HoloLens, aplique el archivo .ppkg de VPN; para ello, abra el menú Inicio y seleccione **Configuración** -> **Cuenta** -> **Obtener acceso a trabajo o escuela** -> **Agregar o quitar un paquete de aprovisionamiento** -> Seleccione el paquete de VPN.</span><span class="sxs-lookup"><span data-stu-id="b9586-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="b9586-226">Configuración de VPN por medio de Intune</span><span class="sxs-lookup"><span data-stu-id="b9586-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="b9586-227">Solo tiene que seguir los documentos de Intune para comenzar.</span><span class="sxs-lookup"><span data-stu-id="b9586-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="b9586-228">Cuando siga esos pasos, debe tener en cuenta los protocolos VPN integrados compatibles con los dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9586-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="b9586-229">[Creación de perfiles de VPN para conectarse a servidores VPN en Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="b9586-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="b9586-230">[Configuración de dispositivos con Windows 10 y Windows Holographic para agregar conexiones VPN mediante Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="b9586-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="b9586-231">Cuando haya terminado, recuerde [asignar el perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="b9586-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="b9586-232">VPN por medio de soluciones MDM de terceros</span><span class="sxs-lookup"><span data-stu-id="b9586-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="b9586-233">Ejemplo de conexión de VPN de terceros:</span><span class="sxs-lookup"><span data-stu-id="b9586-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="b9586-234">Ejemplo de VPN de IKEv2 nativa:</span><span class="sxs-lookup"><span data-stu-id="b9586-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="b9586-235">Deshabilitación de Wi-Fi en HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="b9586-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="b9586-236">Uso de la aplicación Configuración en HoloLens</span><span class="sxs-lookup"><span data-stu-id="b9586-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="b9586-237">Abra el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b9586-238">Seleccione la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="b9586-239">La aplicación **Configuración** se colocará delante automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b9586-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b9586-240">Seleccione **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="b9586-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="b9586-241">Seleccione el control deslizante de Wi-Fi para moverlo a la posición **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="b9586-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="b9586-242">Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y todas las características de Wi-Fi del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9586-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="b9586-243">Cuando la radio de Wi-Fi está deshabilitada, HoloLens no puede cargar automáticamente los [espacios](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="b9586-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="b9586-244">Mueva el control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9586-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="b9586-245">El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.</span><span class="sxs-lookup"><span data-stu-id="b9586-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="b9586-246">Identificación de la dirección IP de HoloLens en la red Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b9586-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="b9586-247">Mediante la aplicación Configuración</span><span class="sxs-lookup"><span data-stu-id="b9586-247">By using the Settings app</span></span>

1. <span data-ttu-id="b9586-248">Abra el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b9586-249">Seleccione la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="b9586-250">La aplicación **Configuración** se colocará delante automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b9586-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b9586-251">Seleccione **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="b9586-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="b9586-252">Desplácese hasta debajo de la lista de redes Wi-Fi disponibles y seleccione **Propiedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="b9586-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Propiedades de hardware en la configuración de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="b9586-254">La dirección IP aparece junto a la **dirección IPv4**.</span><span class="sxs-lookup"><span data-stu-id="b9586-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="b9586-255">Mediante comandos de voz</span><span class="sxs-lookup"><span data-stu-id="b9586-255">By using voice commands</span></span>

<span data-ttu-id="b9586-256">Según la compilación del dispositivo, puede usar los comandos de voz integrados o Cortana para mostrar su dirección IP.</span><span class="sxs-lookup"><span data-stu-id="b9586-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="b9586-257">En compilaciones posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), diga "¿Cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="b9586-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="b9586-258">y se mostrará.</span><span class="sxs-lookup"><span data-stu-id="b9586-258">and it will be displayed.</span></span> <span data-ttu-id="b9586-259">En compilaciones anteriores o en HoloLens (1.ª gen), diga "Hola Cortana, ¿cuál es mi dirección IP?"</span><span class="sxs-lookup"><span data-stu-id="b9586-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="b9586-260">y Cortana mostrará y leerá la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="b9586-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="b9586-261">Mediante el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="b9586-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="b9586-262">En un explorador web del equipo, abra el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="b9586-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="b9586-263">Vaya a la sección **Redes**.</span><span class="sxs-lookup"><span data-stu-id="b9586-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="b9586-264">Esta sección muestra la dirección IP y otra información de la red.</span><span class="sxs-lookup"><span data-stu-id="b9586-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="b9586-265">Con este método, puede copiar y pegar de la dirección IP en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b9586-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="b9586-266">Cambio de la dirección IP a una dirección estática</span><span class="sxs-lookup"><span data-stu-id="b9586-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="b9586-267">Mediante Configuración</span><span class="sxs-lookup"><span data-stu-id="b9586-267">By using Settings</span></span>
 
1. <span data-ttu-id="b9586-268">Abra el menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b9586-269">Seleccione la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="b9586-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="b9586-270">La aplicación **Configuración** se colocará delante automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b9586-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b9586-271">Seleccione **Red e Internet**.</span><span class="sxs-lookup"><span data-stu-id="b9586-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="b9586-272">Desplácese hasta debajo de la lista de redes Wi-Fi disponibles y seleccione **Propiedades de hardware**.</span><span class="sxs-lookup"><span data-stu-id="b9586-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="b9586-273">En la ventana **Edit IP settings** (Editar configuración de IP), cambie el primer campo a **Manual**.</span><span class="sxs-lookup"><span data-stu-id="b9586-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="b9586-274">Introduzca la configuración de IP deseada en los campos restantes y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9586-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="b9586-275">Mediante el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="b9586-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="b9586-276">En un explorador web del equipo, abra el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="b9586-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="b9586-277">Vaya a la sección **Redes**.</span><span class="sxs-lookup"><span data-stu-id="b9586-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="b9586-278">Seleccione el botón **IPv4 Configuration** (Configuración de IPv4).</span><span class="sxs-lookup"><span data-stu-id="b9586-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="b9586-279">Seleccione **Usar la siguiente dirección IP** e introduzca la configuración de TCP/IP deseada.</span><span class="sxs-lookup"><span data-stu-id="b9586-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="b9586-280">Seleccione **Usar las siguientes direcciones de servidor DNS** y escriba las direcciones del servidor DNS preferido y alternativo, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b9586-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="b9586-281">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="b9586-281">Click **Save**.</span></span> 
