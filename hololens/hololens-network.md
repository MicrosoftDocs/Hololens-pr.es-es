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
# Conectar HoloLens a una red

Para hacer la mayoría de las cosas en HoloLens, debes estar conectado a una red. Esta guía te ayudará a:

- Conéctate a una red con Wi-Fi o (solo para HoloLens 2) Ethernet a través de USB-C
- Deshabilitar y volver a habilitar Wi-Fi

Más información sobre cómo [usar HoloLens sin conexión](hololens-offline.md).

## Conectarte por primera vez

La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi. Si tienes problemas para conectarte a una red Wi-Fi durante la instalación, asegúrate de que tu red es una red abierta protegida con contraseña o una red de portales cautivos. Asegúrate de que la red no requiera que uses un certificado para conectarte. Tras la configuración, puedes conectarte a otros tipos de redes Wi-Fi.

En los dispositivos HoloLens 2, un usuario también puede [usar un adaptador USB-C a Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) para conectarse directamente a la red Wi-Fi para ayudar a configurar el dispositivo. Una vez que se configure el dispositivo, el usuario puede seguir usando el adaptador, o bien puede desconectar el dispositivo del adaptador y [conectarse a una red Wi-Fi después de configurarlo](hololens-network.md#connecting-to-wi-fi-after-setup). 

## Conexión a una red Wi-Fi después de la configuración

1. Realiza el **gesto Inicio** y selecciona **Configuración**. La aplicación Configuración se colocará automáticamente delante de ti.
1. Selecciona **Red e Internet** > **Wi-Fi**. Asegúrate de que la conexión Wi-Fi está activada. Si no ves la red, desplázate hacia abajo de la lista.
1. Selecciona una red y, a continuación, **Conectar**.
1. Si se te pide una contraseña de red, escríbela y, a continuación, selecciona **Siguiente**.

HoloLens contiene una radio Wi-Fi 2x2 compatible con 802.11ac. Conectar HoloLens a una red Wi-Fi es similar a conectar un dispositivo móvil o Windows 10 Desktop a una red Wi-Fi.

![Configuración de Wi-Fi de HoloLens](./images/wifi-hololens-600px.jpg)

También puedes confirmar que estás conectado a una red Wi-Fi comprobando el estado de Wi-Fi en el menú **Inicio**:

1. Abre el menú **Inicio**.
1. Mira el estado de la Wi-Fi en la parte superior izquierda del menú **Inicio**. Se mostrará el estado de la Wi-Fi y del SSID de la red conectada.

## Solución de problemas de la conexión a Wi-Fi

Si tiene problemas para conectarse a una conexión Wi-Fi, consulte [No puedo conectarme a Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Cuando inicia sesión en una cuenta de empresa u organización en el dispositivo, también puede aplicar la directiva de Administración de dispositivos móviles (MDM), si su administrador de TI configura la directiva.

## VPN
Una conexión VPN puede ayudar a proporcionar una conexión más segura y acceso a la red de su compañía y a Internet. HoloLens 2 es compatible con el cliente VPN integrado y el complemento VPN de la Plataforma universal de Windows (UWP). 

Protocolos VPN integrados compatibles:
- IKEv2
- L2TP
- PPTP

Si se usa un certificado para la autenticación del cliente de VPN integrado, el certificado de cliente necesario se debe agregar al almacén de certificados de usuario. Para averiguar si un complemento VPN de terceros es compatible con HoloLens 2, vaya a Store para localizar la aplicación VPN y compruebe si HoloLens se muestra como un dispositivo compatible y en la página de Requisitos del sistema la aplicación es compatible con la arquitectura de ARM o ARM64. HoloLens solo admite aplicaciones de la Plataforma universal de Windows para VPN de terceros.

La VPN no está habilita de forma predeterminada, pero puede habilitarse de forma manual abriendo la aplicación de **Configuración** y yendo a **Red e Internet > VPN**. MDM puede administrar la red privada virtual con [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), y configurada a través de la [directiva Vpnv2-csp](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).
Obtenga más información sobre [cómo configurar la VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) con [estas guías](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

## Deshabilitar Wi-Fi en HoloLens (1.ª generación)

### Usar la aplicación Configuración en HoloLens

1. Abre el menú **Inicio**.
1. Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación **Configuración** se colocará automáticamente delante de ti.
1. Selecciona **Red e Internet**.
1. Selecciona el interruptor del control deslizante de Wi-Fi para moverlo a la posición **Desactivado**. Esto desactivará los componentes de RF del aparato de la radio de Wi-Fi y deshabilitará todas las características de Wi-Fi en HoloLens.

    > [!WARNING]
    > Cuando la radio de Wi-Fi está deshabilitada, HoloLens no podrá cargar automáticamente sus [espacios](hololens-spaces.md).

1. Mueve el interruptor del control deslizante a la posición **Activado** para activar la radio de Wi-Fi y restaurar la funcionalidad de Wi-Fi en Microsoft HoloLens. El estado de la radio de Wi-Fi seleccionada (**Activado** o **Desactivado**) persistirá en los reinicios.

## Identificación de la dirección IP de HoloLens en la red Wi-Fi

### Mediante la aplicación Configuración

1. Abre el menú **Inicio**.
1. Selecciona la aplicación **Configuración** en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación **Configuración** se colocará automáticamente delante de ti.
1. Selecciona **Red e Internet**.
1. Desplázate hasta debajo de la lista de redes Wi-Fi disponibles y selecciona **Propiedades de hardware**.

    ![Propiedades de hardware en configuración de Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   La dirección IP aparece junto a **Dirección IPv4**.

### Mediante comandos de voz

Según la compilación de los dispositivos, puede usar los comandos de voz integrados o Cortana para mostrar su dirección IP. En compilaciones posteriores a [19041.1103](hololens-release-notes.md#windows-holographic-version-2004), di "¿Cuál es mi dirección IP?" y se mostrará. Para compilaciones anteriores o HoloLens (1.ª gen), di "Hola Cortana, ¿cuál es mi dirección IP?" y Cortana mostrará y leerá tu dirección IP.

### Con el Portal de dispositivos Windows

1. En un explorador web de tu PC, abre el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Ve a la sección **Redes**.  
   Esta sección muestra tu dirección IP y otra información de la red. Con este método, puedes copiar y pegar de la dirección IP en tu PC de desarrollo.
