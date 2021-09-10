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
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427468"
---
# <a name="connect-hololens-to-a-network"></a>Conexión de HoloLens a una red

La mayoría de las actividades que se realizan con HoloLens requieren estar conectado a una red. HoloLens contiene una radio 2x2 Wi-Fi compatible con 802.11ac; conectarlo este dispositivo a una red es similar a conectar un dispositivo de escritorio o móvil de Windows 10 a una red Wi-Fi. Esta guía le ayudará a:

- Conectarse a una red con Wi-Fi o, solo para HoloLens 2, con Wi-Fi Direct o Ethernet por medio de USB-C.
- Deshabilitar y volver a habilitar la red Wi-Fi.

Obtenga más información sobre el [uso de HoloLens sin conexión](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Conexión por primera vez

La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi. Si tiene problemas para conectarse a una red Wi-Fi durante la instalación, asegúrese de que se trata de una red abierta, protegida con contraseña o una red de portales cautivos. Además, confirme que la red no requiere que use un certificado para conectarse. Tras la configuración, puede conectarse a otros tipos de redes Wi-Fi.

En los dispositivos HoloLens 2, un usuario también puede usar un [adaptador de USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectarse directamente a la red Wi-Fi como ayuda para configurar el dispositivo. Una vez configurado el dispositivo, el usuario puede seguir usando el adaptador o puede desconectar el dispositivo del adaptador y [conectarse a una red Wi-Fi después de la configuración](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Conexión a una red Wi-Fi después de la configuración

1. Haga el **gesto Inicio** y seleccione **Configuración**. La aplicación Configuración se colocará delante automáticamente.
1. Seleccione **Red e Internet** > **Wi-Fi**. Asegúrese de que la conexión Wi-Fi está activada. Si no ve la red, desplácese hacia abajo de la lista.
1. Seleccione una red y, a continuación, **Conectar**.
1. Si se le pide una contraseña de red, escríbala y, a continuación, seleccione **Siguiente**.

![Configuración de Wi-Fi de HoloLens.](./images/hololens-2-wifi-settings.jpg)

Para confirmar que está conectado a una red Wi-Fi, compruebe el estado de la red en el menú **Inicio**:

1. Abra el menú **Inicio**.
1. Consulte el estado de la red Wi-Fi en la parte superior izquierda del menú **Inicio**. Se mostrará el estado de la red Wi-Fi y del SSID de la red conectada.

> [!TIP]
> Si la red Wi-Fi no está disponible, también puede [conectarse a redes de telefonía móvil y 5G](hololens-cellular.md).

> [!IMPORTANT]
> Por diseño, los usuarios no pueden ajustar el comportamiento de itinerancia de Wi-Fi del dispositivo HoloLens 2; **la única manera de actualizar la lista de redes Wi-Fi es activar y desactivar la conexión a Wi-Fi**. Esto evita muchos problemas, como que un dispositivo se quede "atascado" en una AP cuando está fuera del rango.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Conexión de HoloLens a la red Wi-Fi empresarial

Los perfiles de Wi-Fi empresarial usan el protocolo de autenticación extensible (EAP) para autenticar las conexiones Wi-Fi. El perfil de Wi-Fi empresarial de HoloLens se puede configurar por medio de MDM o del paquete de aprovisionamiento creado por [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).

En el caso de los dispositivos administrados de Microsoft Intune, consulte las instrucciones de configuración en la información para [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

Para crear un paquete de aprovisionamiento de Wi-Fi en WCD, se requiere un archivo de perfil Wi-Fi en formato .xml preconfigurado. Este es un ejemplo de perfil de Wi-Fi para WPA2-Enterprise con autenticación EAP-TLS:

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


Según el tipo de EAP, es posible que deba aprovisionar el certificado de entidad de certificación raíz del servidor y el certificado del cliente en el dispositivo.

Recursos adicionales:

- Esquema de perfil WLANv1: [[MS-GPWL]: Esquema de perfil de LAN inalámbrica v1 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Esquema EAP-TLS: [[MS-GPWL]: Esquema TLS de Microsoft EAP | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Consulte nuestra página de [solución de problemas](hololens2-enterprise-troubleshooting.md#) si tiene problemas para conectarse a la red Wi-Fi.

## <a name="configure-network-proxy"></a>Configuración del proxy de red

En esta sección se explica la configuración del proxy de red para el sistema operativo de HoloLens y las aplicaciones de la Plataforma universal de Windows (UWP) mediante la pila HTTP de Windows. Las aplicaciones que usan una pila HTTP que no es Windows pueden tener su propia configuración y control de proxy. 

### <a name="proxy-configurations"></a>Configuraciones de proxy 

- Script de configuración automática (PAC) de proxy: un [archivo PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (abre un sitio que no es de Microsoft) contiene una función de JavaScript FindProxyForURL(url, host). 
- Proxy estático: en forma de Servidor:Puerto.  
- Protocolo de detección automática de proxy web (WPAD): proporcione la dirección URL del archivo de configuración de proxy por medio de DHCP o DNS. 

### <a name="proxy-provisioning-methods"></a>Métodos de aprovisionamiento de proxies 
Hay tres formas de aprovisionar proxies:

 

1.  **Interfaz de usuario Configuración:** 
    1. Proxy por usuario (20H2 o anterior):
        1. Abra el menú Inicio y seleccione Configuración.
        2. Seleccione Red e Internet y, después, Proxy en el menú izquierdo.
        3. Desplácese hacia abajo hasta la configuración manual del proxy y active Usar un servidor proxy.
        4. Escriba la dirección IP del servidor proxy.
        5. Escriba el número de puerto.
        6. Haga clic en Guardar.
      1. Proxy de Wi-Fi (21H1 o posterior):
          1. Abra el menú Inicio y vaya a la página de propiedades de la red Wi-Fi.
          1. Desplácese hacia abajo hasta Proxy.
          1. Cambie a la configuración manual.
          1. Escriba la dirección IP del servidor proxy.
          1. Escriba el número de puerto.
          1. Haga clic en Aplicar.
        
 2. **MDM** 
     1. Intune: siga estos [pasos](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para configurar el proxy en Intune. Tendrá que desplazarse hasta la parte inferior de la sección.
     1. Otras soluciones MDM de terceros: use un [CSP de Wi-Fi](/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. Abra Windows Configuration Designer.
    1. Haga clic en Advanced Provisioning (Aprovisionamiento avanzado), escriba el nombre del nuevo proyecto y haga clic en Next (Siguiente).
    1. Seleccione Windows Holographic (HoloLens 2) y haga clic en Next (Siguiente).
    1. Importe el archivo PPKG (opcional) y haga clic en Finish (Finalizar).
    1. Expanda Runtime Settings (Configuración del entorno de ejecución) -> Connectivity Profiles (Perfiles de conectividad) -> WLAN -> WLAN Proxy (Proxy de WLAN).
    1. Escriba el SSID de la red Wi-Fi y haga clic en Add (Agregar).
    1. Seleccione la red Wi-Fi en la ventana izquierda y escriba las personalizaciones deseadas. Las personalizaciones habilitadas se mostrarán en negrita en el menú izquierdo.
    1. Haga clic en Save and Exit (Guardar y salir).
    1. [Aplique](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) el paquete de aprovisionamiento al dispositivo HoloLens.

Los [CSP](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) están detrás de muchas de las tareas y directivas de administración de Windows 10, tanto en Microsoft Intune como en proveedores de servicios de MDM que no son de Microsoft. También puede usar [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) para crear un [paquete de aprovisionamiento](/windows/configuration/provisioning-packages/provisioning-packages) y aplicarlo al dispositivo HoloLens 2.
Los CSP que se aplicarán con más probabilidad al dispositivo HoloLens 2 son los siguientes:

- [CSP de Wi-Fi](/windows/client-management/mdm/wifi-csp): proxy de Wi-Fi por perfil 

[Otros CSP admitidos en dispositivos HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Una conexión VPN puede ayudar a proporcionar una conexión más segura y acceso a la red de su compañía y a Internet. HoloLens 2 es compatible con el cliente VPN integrado y el complemento VPN de la Plataforma universal de Windows (UWP). 

Protocolos VPN integrados compatibles:
- IKEv2
- L2TP
- PPTP

Si se usa un certificado para la autenticación del cliente de VPN integrado, el certificado de cliente necesario se debe agregar al almacén de certificados de usuario. Para averiguar si un complemento VPN de terceros es compatible con HoloLens 2, vaya a Store para localizar la aplicación VPN, compruebe si HoloLens se muestra como un dispositivo compatible y si en la página de requisitos del sistema se indica que la aplicación es compatible con la arquitectura de ARM o ARM64. HoloLens solo admite aplicaciones de la Plataforma universal de Windows para VPN de terceros.

 LA VPN se puede administrar mediante MDM por medio de [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) y se puede establecer por medio de la [directiva Vpnv2-csp](/windows/client-management/mdm/vpnv2-csp).

Obtenga más información sobre [cómo configurar VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [estas guías](/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN por medio de la interfaz de usuario

La opción de VPN no está habilita de forma predeterminada, pero puede habilitarse de forma manual abriendo la aplicación **Configuración** y yendo a **Red e Internet -> VPN**.
1. Seleccione un proveedor de VPN.
1. Cree un nombre de conexión. 
1. Escriba el nombre o la dirección del servidor.
1. Seleccione el tipo de VPN.
1. Seleccione el tipo de información de inicio de sesión. 
1. Opcionalmente, puede agregar un nombre de usuario y contraseña.
1. Aplique la configuración de VPN. 

![Configuración de VPN de HoloLens.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Configuración de una VPN mediante el paquete de aprovisionamiento

> [!TIP] 
> En Windows Holographic, versión 20H2, hemos corregido un problema de configuración de proxy para la conexión VPN. Si tiene previsto usar este flujo, considere la posibilidad de actualizar los dispositivos a esta compilación.

1. Inicie Windows Configuration Designer.
1. Haga clic en **Provision HoloLens devices** (Aprovisionar dispositivos HoloLens) y, a continuación, seleccione el dispositivo de destino y **Next** (Siguiente).
1. Escribe el nombre y la ruta del paquete.
1. Haga clic en **Switch to advanced editor** (Cambiar al editor avanzado).
1. Abra **Runtime settings (Configuración del entorno de ejecución)**  -> **ConnectivityProfiles** -> **VPN** -> **VPNSetting**.
1. Configure el nombre de perfil de VPN.
1. Seleccione el valor de ProfileType: **Native** (Nativo) o **Third Party** (Terceros).
    1. En el perfil nativo, seleccione **NativeProtocolType** y, a continuación, configure el servidor, la directiva de enrutamiento, el tipo de autenticación y otras opciones.
    1. En el perfil de terceros, configure la dirección URL del servidor, el nombre de familia del paquete de la aplicación del complemento VPN (solo 3 predefinidos) y las configuraciones personalizadas.
1. Exporte el paquete.
1. Conéctese al dispositivo HoloLens y copie en él el archivo .ppkg. 
1. En HoloLens, aplique el archivo .ppkg de VPN; para ello, abra el menú Inicio y seleccione **Configuración** -> **Cuenta** -> **Obtener acceso a trabajo o escuela** -> **Agregar o quitar un paquete de aprovisionamiento** -> Seleccione el paquete de VPN.


### <a name="setting-up-vpn-via-intune"></a>Configuración de VPN por medio de Intune
Solo tiene que seguir los documentos de Intune para comenzar. Cuando siga esos pasos, debe tener en cuenta los protocolos VPN integrados compatibles con los dispositivos HoloLens. 

[Creación de perfiles de VPN para conectarse a servidores VPN en Intune](/mem/intune/configuration/vpn-settings-configure)

[Configuración de dispositivos con Windows 10 y Windows Holographic para agregar conexiones VPN mediante Intune](/mem/intune/configuration/vpn-settings-windows-10)

Cuando haya terminado, recuerde [asignar el perfil](/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN por medio de soluciones MDM de terceros
Ejemplo de conexión de VPN de terceros:
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

Ejemplo de VPN de IKEv2 nativa:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Deshabilitación de Wi-Fi en HoloLens (1.ª generación)

### <a name="using-the-settings-app-on-hololens"></a>Uso de la aplicación Configuración en HoloLens

1. Abra el menú **Inicio**.
1. Seleccione la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación **Configuración** se colocará delante automáticamente.
1. Seleccione **Red e Internet**.
1. Seleccione el control deslizante de Wi-Fi para moverlo a la posición **Desactivado**. Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y todas las características de Wi-Fi del dispositivo HoloLens.

    > [!WARNING]
    > Cuando la radio de Wi-Fi está deshabilitada, HoloLens no puede cargar automáticamente los [espacios](hololens-spaces.md).

1. Mueva el control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens. El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identificación de la dirección IP de HoloLens en la red Wi-Fi

### <a name="by-using-the-settings-app"></a>Mediante la aplicación Configuración

1. Abra el menú **Inicio**.
1. Seleccione la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación **Configuración** se colocará delante automáticamente.
1. Seleccione **Red e Internet**.
1. Desplácese hasta debajo de la lista de redes Wi-Fi disponibles y seleccione **Propiedades de hardware**.

    ![Propiedades de hardware en la configuración de Wi-Fi.](./images/wifi-hololens-hwdetails.jpg)

   La dirección IP aparece junto a la **dirección IPv4**.

### <a name="by-using-voice-commands"></a>Mediante comandos de voz

Según la compilación del dispositivo, puede usar los comandos de voz integrados o Cortana para mostrar su dirección IP. En compilaciones posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), diga "¿Cuál es mi dirección IP?" y se mostrará. En compilaciones anteriores o en HoloLens (1.ª gen), diga "Hola Cortana, ¿cuál es mi dirección IP?" y Cortana mostrará y leerá la dirección IP.

### <a name="by-using-windows-device-portal"></a>Mediante el Portal de dispositivos Windows

1. En un explorador web del equipo, abra el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Vaya a la sección **Redes**.  
   Esta sección muestra la dirección IP y otra información de la red. Con este método, puede copiar y pegar de la dirección IP en el equipo de desarrollo.

## <a name="change-ip-address-to-static-address"></a>Cambio de la dirección IP a una dirección estática
### <a name="by-using-settings"></a>Mediante Configuración
 
1. Abra el menú **Inicio**.
1. Seleccione la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación **Configuración** se colocará delante automáticamente.
1. Seleccione **Red e Internet**.
1. Desplácese hasta debajo de la lista de redes Wi-Fi disponibles y seleccione **Propiedades de hardware**.
1. En la ventana **Edit IP settings** (Editar configuración de IP), cambie el primer campo a **Manual**.
1. Introduzca la configuración de IP deseada en los campos restantes y, a continuación, haga clic en **Guardar**.

### <a name="by-using-windows-device-portal"></a>Mediante el Portal de dispositivos Windows

1. En un explorador web del equipo, abra el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Vaya a la sección **Redes**.
1. Seleccione el botón **IPv4 Configuration** (Configuración de IPv4).
1. Seleccione **Usar la siguiente dirección IP** e introduzca la configuración de TCP/IP deseada.
1. Seleccione **Usar las siguientes direcciones de servidor DNS** y escriba las direcciones del servidor DNS preferido y alternativo, si es necesario.
1. Haga clic en **Save**(Guardar). 
