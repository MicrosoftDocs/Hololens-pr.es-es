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
ms.openlocfilehash: f1968afe7d450425776bac24532f2d84c4dc3c62
ms.sourcegitcommit: 9f79ed9f76b930b8ceb97844d5f9eace9316b8a3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442601"
---
# <a name="connect-hololens-to-a-network"></a>Conectar HoloLens a una red

Para hacer la mayoría de las cosas en HoloLens, debes estar conectado a una red. HoloLens contiene una radio 2x2 Wi-Fi compatible con 802.11ac y la conexión a una red es similar a conectar un dispositivo de escritorio o móvil de Windows 10 a una red Wi-Fi. Esta guía te ayudará a:

- Conéctate a una red con Wi-Fi o (solo para HoloLens 2) Ethernet a través de USB-C
- Deshabilitar y volver a habilitar Wi-Fi

Más información sobre cómo [usar HoloLens sin conexión](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>Conectarte por primera vez

La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi. Si tienes problemas para conectarte a una red Wi-Fi durante la instalación, asegúrate de que tu red es una red abierta protegida con contraseña o una red de portales cautivos. Además, confirma que la red no requiere que uses un certificado para conectarte. Tras la configuración, puedes conectarte a otros tipos de redes Wi-Fi.

En dispositivos HoloLens 2, un usuario también puede [usar un adaptador USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectarse directamente a Wi-Fi para ayudar a configurar el dispositivo. Una vez configurado el dispositivo, un usuario puede seguir usando el adaptador o puede desconectar el dispositivo del adaptador y [conectarse a una red Wi-Fi después de configurarlo](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Conexión a una red Wi-Fi después de la configuración

1. Realiza el **gesto Inicio** y selecciona **Configuración**. La aplicación Configuración se colocará automáticamente delante de ti.
1. Selecciona **Red e Internet** > **Wi-Fi**. Asegúrate de que la conexión Wi-Fi está activada. Si no ves la red, desplázate hacia abajo de la lista.
1. Selecciona una red y, a continuación, **Conectar**.
1. Si se te pide una contraseña de red, escríbela y, a continuación, selecciona **Siguiente**.

![Configuración de Wi-Fi de HoloLens](./images/hololens-2-wifi-settings.jpg)

Para confirmar que estás conectado a una Wi-Fi, comprueba el estado Wi-Fi en el **menú** Inicio:

1. Abre el menú **Inicio**.
1. Mira el estado de la Wi-Fi en la parte superior izquierda del menú **Inicio**. Se mostrará el estado de la Wi-Fi y del SSID de la red conectada.

> [!TIP]
> Si la conexión Wi-Fi no está disponible, también puedes conectarte a redes de telefonía [móvil y 5G.](https://docs.microsoft.com/hololens/hololens-cellular)

> [!IMPORTANT]
> Por diseño, los usuarios no pueden ajustar el comportamiento de movilidad de Wi-Fi de HoloLens 2: **la única forma de actualizar la lista Wi-Fi es alternar las opciones Wi-Fi desactivado y activado**. Esto evita muchos problemas, como cuando un dispositivo puede permanecer "atascado" en una AP una vez que está fuera del rango.

## <a name="troubleshooting-your-connection-to-wi-fi"></a>Solución de problemas de la conexión a Wi-Fi

Si tiene problemas para conectarse a una conexión Wi-Fi, consulte [No puedo conectarme a Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Cuando inicia sesión en una cuenta de empresa u organización en el dispositivo, también puede aplicar la directiva de Administración de dispositivos móviles (MDM), si su administrador de TI configura la directiva.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Conectar HoloLens a la red de Wi-Fi empresarial

Los perfiles de Wi-Fi empresarial usan el Protocolo de Autenticación Extensible (EAP) para autenticar las conexiones Wi-Fi. El perfil de Wi-Fi empresarial de HoloLens se puede configurar a través de MDM o del paquete de aprovisionamiento creado por el [Diseñador de configuración de Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Para los dispositivos administrados de Microsoft Intune, consulta [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) para ver las instrucciones de configuración.

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


Según el tipo de EAP, es posible que debas aprovisionar el certificado raíz de la entidad emisora del servidor y el certificado del cliente en el dispositivo.

Recursos adicionales:

- Esquema de WLANv1Profile: [[MS-GPWL]: esquema de Perfil de LAN inalámbrico v1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Esquema EAP-TLS: [[MS-GPWL]: esquema EAP TLS de Microsoft | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### <a name="eap-troubleshooting"></a>Solución de problemas de EAP

1. Asegúrate de que el perfil de Wi-Fi tiene la configuración adecuada. Verifica lo siguiente:
   1. El tipo de EAP está configurado correctamente, tipos comunes de EAP: EAP-TLS (13), EAP-TTLS (21) y PEAP (25).
   1. El nombre de Wi-Fi SSID es correcto y está en formato hexadecimal.
   1. Para EAP-TLS, TrustedRootCA contiene el hash SHA-1 del certificado de CA raíz de confianza del servidor. En Windows PC, el comando &quot;certutil.exe -dump cert\_file\_name&quot; mostrará una cadena con el hash SHA-1 del certificado.
1. Recopila captura de paquetes de red en el punto de acceso o controladora o en los registros del servidor AAA para averiguar dónde se produce un error en la sesión de EAP.
   1. Si la identidad de EAP proporcionada por HoloLens no es la esperada, comprueba si la identidad se ha aprovisionado correctamente mediante el perfil de Wi-Fi o el certificado de cliente.
   1. Si el servidor rechaza el certificado de cliente de HoloLens, comprueba si el certificado de cliente necesario se ha aprovisionado en el dispositivo.
   1. Si HoloLens rechaza el certificado de servidor, comprueba si el certificado CA raíz del servidor se ha aprovisionado en HoloLens.
1. Si el perfil de empresa se aprovisiona mediante el paquete de aprovisionamiento Wi-Fi, plantéate aplicar el paquete de aprovisionamiento en un equipo con Windows 10. Si el error se produce incluso en un PC con Windows 10, sigue la [Guía de solución de problemas de autenticación en 802.1X en cliente de Windows](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).
1. Envíanos tus comentarios a través del [Centro de opiniones](https://docs.microsoft.com/hololens/hololens-feedback).

### <a name="additional-resources"></a>Recursos adicionales:
- [Exportar la configuración de Wi-Fi desde un dispositivo de Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="vpn"></a>VPN
Una conexión VPN puede ayudar a proporcionar una conexión más segura y acceso a la red de su compañía y a Internet. HoloLens 2 es compatible con el cliente VPN integrado y el complemento VPN de la Plataforma universal de Windows (UWP). 

Protocolos VPN integrados compatibles:
- IKEv2
- L2TP
- PPTP

Si se usa un certificado para la autenticación del cliente de VPN integrado, el certificado de cliente necesario se debe agregar al almacén de certificados de usuario. Para averiguar si un complemento VPN de terceros es compatible con HoloLens 2, vaya a Store para localizar la aplicación VPN y compruebe si HoloLens se muestra como un dispositivo compatible y en la página de Requisitos del sistema la aplicación es compatible con la arquitectura de ARM o ARM64. HoloLens solo admite aplicaciones de la Plataforma universal de Windows para VPN de terceros.

 MDM puede administrar una VPN con [Configuración/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), y se puede configurar a través de la [directiva Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

Obtén más información sobre [cómo configurar la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [estas guías](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN a través de la IU

La VPN no está habilita de forma predeterminada, pero puede habilitarse de forma manual abriendo la aplicación de **Configuración** y yendo a **Red e Internet > VPN**.
1. Selecciona un proveedor de VPN.
1. Crea un nombre de conexión. 
1. Escribe el nombre o la dirección del servidor.
1. Selecciona el tipo de VPN.
1. Selecciona el tipo de información de inicio de sesión. 
1. Opcionalmente, puedes agregar un nombre de usuario y contraseña.
1. Aplica la configuración de VPN. 

![Configuración de VPN de HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Configurar una VPN mediante el paquete de aprovisionamiento

> [!TIP] 
> En nuestra versión 20H2 de Windows Holographic hemos corregido un problema de configuración de proxy para la conexión VPN. Si tienes previsto usar este flujo, considera la posibilidad de actualizar los dispositivos de esta compilación.

1. Inicia el Diseñador de configuración de Windows.
1. Haz clic en **Aprovisionar dispositivos HoloLens**, selecciona el dispositivo de destino y, luego, **Siguiente**.
1. Escribe el nombre y la ruta del paquete.
1. Haz clic en **Cambiar a editor avanzado**.
1. Abre **Configuración de tiempo de ejecución** -> **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.
1. Configura VPNProfileName
1. Selecciona ProfileType: **Nativo** o de **Tercero**.
    1. En perfil Nativo, selecciona **NativeProtocolType** y, a continuación, configura el servidor, la directiva de enrutamiento, el tipo de autenticación y otras opciones.
    1. Para el perfil "Tercero", configura la dirección URL del servidor, el nombre de familia del paquete de la aplicación del complemento VPN (solo 3 predefinidos) y las configuraciones personalizadas.
1. Exporta el paquete.
1. Conecta tu HoloLens y copia el archivo .ppkg en el dispositivo. 
1. En HoloLens, aplica el .ppkg de VPN abriendo el menú Inicio y seleccionando **Configuración** -> **Cuenta** -> **Acceder a trabajo o escuela** -> **Agregar o quitar el paquete de aprovisionamiento** -> Selecciona tu paquete de VPN.


### <a name="setting-up-vpn-via-intune"></a>Configuración de VPN a través de Intune
Solo tienes que seguir los documentos de Intune para comenzar. Cuando sigas estos pasos debes tener en cuenta los protocolos VPN integrados que admiten los dispositivos HoloLens. 

[Crear perfiles de VPN para conectarse a servidores VPN en Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).

[Configuración de dispositivos con Windows 10 y Windows Holographic para agregar conexiones VPN mediante Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).

Cuando termines, recuerda [asignar el perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN a través de soluciones MDM de terceros
Ejemplo de conexión VPN de terceros:
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

Ejemplo de VPN IKEv2 nativa:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Deshabilitar Wi-Fi en HoloLens (1.ª generación)

### <a name="using-the-settings-app-on-hololens"></a>Usar la aplicación Configuración en HoloLens

1. Abre el menú **Inicio**.
1. Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación **Configuración** se colocará automáticamente delante de ti.
1. Selecciona **Red e Internet**.
1. Selecciona el interruptor del control deslizante de Wi-Fi para moverlo a la posición **Desactivado**. Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y deshabilitará todas las características de Wi-Fi en HoloLens.

    > [!WARNING]
    > Cuando la radio de Wi-Fi está deshabilitada, HoloLens no podrá cargar automáticamente sus [espacios](hololens-spaces.md).

1. Mueve el interruptor del control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens. El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identificación de la dirección IP de HoloLens en la red Wi-Fi

### <a name="by-using-the-settings-app"></a>Mediante la aplicación Configuración

1. Abre el menú **Inicio**.
1. Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación **Configuración** se colocará automáticamente delante de ti.
1. Selecciona **Red e Internet**.
1. Desplázate hasta debajo de la lista de redes Wi-Fi disponibles y selecciona **Propiedades de hardware**.

    ![Propiedades de hardware en configuración de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   La dirección IP aparece junto a **Dirección IPv4**.

### <a name="by-using-voice-commands"></a>Mediante comandos de voz

Según la compilación de los dispositivos, puede usar los comandos de voz integrados o Cortana para mostrar su dirección IP. En compilaciones posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), di "¿Cuál es mi dirección IP?" y se mostrará. Para compilaciones anteriores o HoloLens (1.ª gen), di "Hola Cortana, ¿cuál es mi dirección IP?" y Cortana mostrará y leerá tu dirección IP.

### <a name="by-using-windows-device-portal"></a>Con el Portal de dispositivos Windows

1. En un explorador web de tu PC, abre el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Ve a la sección **Redes**.  
   Esta sección muestra tu dirección IP y otra información de la red. Con este método, puedes copiar y pegar de la dirección IP en tu PC de desarrollo.
