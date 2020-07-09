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
# Conectar HoloLens a una red

Para hacer la mayoría de las cosas en HoloLens, debes estar conectado a una red. Esta guía te ayudará a:

- Conéctate a una red con Wi-Fi o (solo para HoloLens 2) Ethernet a través de USB-C
- Deshabilitar y volver a habilitar Wi-Fi

Más información sobre cómo [usar HoloLens sin conexión](hololens-offline.md).

## Conectarte por primera vez

La primera vez que uses HoloLens, se te orientará para realizar la conexión a una red Wi-Fi. Si tienes problemas para conectarte a una red Wi-Fi durante la instalación, asegúrate de que tu red es una red abierta protegida con contraseña o una red de portales cautivos. Asegúrate de que la red no requiera que uses un certificado para conectarte. Tras la configuración, puedes conectarte a otros tipos de redes Wi-Fi.

## Conexión a una red Wi-Fi después de la configuración

1. Selecciona **Inicio** > **Configuración**.
   - *Solo HoloLens (1.ª generación)*: usa la mirada para colocar la aplicación Configuración y, a continuación, mantenla pulsada en el aire para colocarla o di "Colocar".
1. Selecciona **Red e Internet** > **Wi-Fi**. Si no ves la red, desplázate hacia abajo de la lista.
1. Selecciona una red y, a continuación, **Conectar**.
1. Si se te pide una contraseña de red, escríbela y, a continuación, selecciona **Siguiente**.

## Conectarte a Wi-Fi en HoloLens (1.ª generación)

HoloLens contiene una radio Wi-Fi 2x2 compatible con 802.11ac. Conectar HoloLens a una red Wi-Fi es similar a conectar un dispositivo móvil o Windows 10 Desktop a una red Wi-Fi.

![Configuración de Wi-Fi de HoloLens](./images/wifi-hololens-600px.jpg)

1. Abre el menú **Inicio**.
1. Selecciona la aplicación Configuración en **Inicio** o en la lista **Todas las aplicaciones** a la derecha del menú **Inicio**. La aplicación Configuración se colocará automáticamente delante de ti.
1. Selecciona **Red e Internet**.
1. Asegúrate de que la conexión Wi-Fi está activada.
1. Selecciona una red Wi-Fi en la lista.
1. Si es necesario, escribe la contraseña de la red Wi-Fi.

También puedes confirmar que estás conectado a una red Wi-Fi comprobando el estado de Wi-Fi en el menú **Inicio**:

1. Abre el menú **Inicio**.
1. Mira el estado de la Wi-Fi en la parte superior izquierda del menú **Inicio**. Se mostrará el estado de la Wi-Fi y del SSID de la red conectada.

## Solución de problemas de la conexión a Wi-Fi

Si tiene problemas para conectarse a una conexión Wi-Fi, consulte [No puedo conectarme a Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Cuando inicia sesión en una cuenta de empresa u organización en el dispositivo, también puede aplicar la directiva de Administración de dispositivos móviles (MDM), si su administrador de TI configura la directiva.

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

### Con Cortana

Di "Hola Cortana, ¿cuál es mi dirección IP?" y Cortana mostrará y leerá tu dirección IP.

### Con el Portal de dispositivos Windows

1. En un explorador web de tu PC, abre el [portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Ve a la sección **Redes**.  
   Esta sección muestra tu dirección IP y otra información de la red. Con este método, puedes copiar y pegar de la dirección IP en tu PC de desarrollo.
