---
title: Presentación de la nueva aplicación Configuración
description: Más información sobre la nueva aplicación Configuración
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, configuración, selector de aplicaciones, volumen
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398939"
---
# <a name="new-settings-app"></a>Nueva aplicación Configuración

Con [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1), presentamos una nueva versión de la aplicación Configuración. Esta nueva aplicación incluye nuevas características y configuraciones expandidas para HoloLens 2 en áreas como Sonido, Inicio/apagado y suspensión, Red e Internet, Aplicaciones, Cuentas o Accesibilidad, entre otras.

> [!NOTE]
> Dado que la nueva aplicación Configuración es distinta de su versión anterior, las ventanas de Configuración que se colocaron anteriormente en el entorno se quitarán tras la actualización.

![Página principal de la nueva aplicación Configuración](images/new-settings-app.png)

**Nuevas características y opciones**
- Búsqueda de opciones: puede buscar opciones en la página principal de Configuración mediante palabras clave o el nombre de la opción.
- Sistema > [Calibración de color](hololens2-display.md#how-to-use-display-color-calibration)
    - Seleccione un perfil de color alternativo para la pantalla de HoloLens 2.
- Sistema > Sonido:
  - Dispositivos de audio de entrada y salida: elija de forma independiente los dispositivos de audio de entrada y salida (por ejemplo, escuche audio a través de auriculares Bluetooth o use un micrófono USB-C para la entrada de audio).
    > [!NOTE]
    > HoloLens 2 no admite micrónfonos Bluetooth.
  - Volumen de la aplicación: puede ajustar el volumen de cada aplicación de forma independiente. Consulte [Control de volumen por aplicación](holographic-home.md#per-app-volume-control).
- Sistema > Inicio/apagado y suspensión: elija si desea que el dispositivo entre en suspensión tras un período de inactividad.
- Sistema > Batería: habilite manualmente el modo de ahorro de batería o establezca un umbral de batería a partir del cual se active automáticamente el modo de ahorro de batería.
- Dispositivos > USB: puede deshabilitar las conexiones USB de forma predeterminada.
- Red e Internet:
  - Ahora los adaptadores Ethernet USB-C aparecerán en Red e Internet.
  - La configuración del adaptador Ethernet USB-C ya está disponible, incluida su dirección IP.
  - Ahora puede habilitar el modo avión en HoloLens 2.
- Aplicaciones: puede restablecer las aplicaciones predeterminadas que se usan para los tipos de archivo y de vínculo. Para obtener más información, consulte [Selector de aplicaciones predeterminadas](holographic-home.md#default-app-picker).
- Cuentas > Otros usuarios: los propietarios de dispositivos pueden agregar usuarios, actualizar usuarios estándar a propietarios de dispositivos, degradar los propietarios de dispositivos a usuarios estándar y quitar usuarios.
- Accesibilidad: se puede cambiar el tamaño del texto y algunos efectos visuales.

**Problemas conocidos**
- Se quitarán las ventanas de Configuración colocadas anteriormente (consulte la nota anterior).
- Ya no puede cambiar el nombre del dispositivo con la aplicación Configuración. Los administradores de TI pueden cambiar el nombre de los dispositivos mediante la plantilla de nombres de dispositivo [Windows Autopilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) o el nodo Ext/Microsoft/DNSComputerName del [CSP DevDetail](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) de MDM.
- La página Ethernet muestra un dispositivo Ethernet virtual ("UsbNcm") en todo momento.
- Puede que la información sobre el uso de batería de la nueva versión de Microsoft Edge no sea precisa, debido a su naturaleza como una aplicación de escritorio Win32 compatible con un nivel de adaptador de UWP (no se prevé ninguna corrección en breve).

