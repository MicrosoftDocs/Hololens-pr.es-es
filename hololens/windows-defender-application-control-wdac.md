---
title: Control de aplicaciones de Windows Defender (WDAC)
description: Información general sobre Windows Defender application control y cómo usarlo para administrar HoloLens dispositivos de realidad mixta.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/21/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: efdc57b5e045c1669587ffc46dbe2132b6de6600
ms.sourcegitcommit: 52ed453cace3851fbec0cfcc228fa2a79f1a2fec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2021
ms.locfileid: "128075392"
---
# <a name="windows-defender-application-control---wdac"></a>Control de aplicaciones de Microsoft Defender: WDAC

## <a name="overview"></a>Información general

WDAC le permite configurar HoloLens bloquear el inicio de aplicaciones. Es diferente del modo quiosco, donde la interfaz de usuario oculta las aplicaciones, pero todavía se pueden iniciar. Con WDAC, puede ver las aplicaciones, pero no se pueden iniciar.

> [!NOTE]
> Cuando los usuarios finales intenten iniciar una aplicación bloqueada por WDAC en HoloLens, no se les notificará si no pueden iniciar la aplicación.

Se puede asignar más de una directiva WDAC a un dispositivo. Si se establecen varias directivas WDAC en un sistema, las más restrictivas tienen efecto.

La siguiente es una guía para que los usuarios aprendan a usar [WDAC](/mem/intune/configuration/custom-profile-hololens)y Windows PowerShell para permitir o bloquear aplicaciones en dispositivos HoloLens 2 con Microsoft Intune .

Cuando los usuarios buscan aplicaciones instaladas en su equipo Windows 10 mediante el primer paso de ejemplo, es posible que deban realizar algunos intentos para restringir los resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
```

Si no conoce el nombre completo del paquete, es posible que tenga que ejecutar "Get-AppxPackage -name \* YourBestGuess" varias veces para \* encontrarlo. Después, una vez que tenga el nombre, ejecute "$package 1 = Get-AppxPackage -name Actual.PackageName"

Por ejemplo, al ejecutar el código siguiente para Microsoft Edge se devolverá más de un resultado, pero en esa lista puede identificar que el nombre completo que necesita es Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
```

## <a name="package-family-names-for-apps-on-hololens"></a>Nombres de familia de paquetes para aplicaciones en HoloLens

En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para aplicaciones que solo se instalan en HoloLens con sus nombres de familia de paquetes. A veces hay aplicaciones que puede usar que no están en el equipo de escritorio que desea agregar a la directiva.

Esta es una lista de aplicaciones de uso frecuente In-Box aplicaciones para HoloLens 2 dispositivos.

| Nombre de la aplicación                   | Nombre de familia del paquete                                |
|----------------------------|----------------------------------------------------|
| Visor 3D                  | `Microsoft.Microsoft3DViewer_8wekyb3d8bbwe`          |
| Instalador de aplicación              | `Microsoft.DesktopAppInstaller_8wekyb3d8bbwe` <sup>1</sup>         |
| Calendario                   | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Cámara                     | `HoloCamera_cw5n1h2txyewy`                          |
| Cortana                    | `Microsoft.549981C3F5F10_8wekyb3d8bbwe`              |
| Dynamics 365 Guides        | `Microsoft.Dynamics365.Guides_8wekyb3d8bbwe`         |
| Dynamics 365 Remote Assist | `Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe`      |
| Centro de opiniones               | `Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe`         |
| Explorador de archivos              | `c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy` |
| Correo                       | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Microsoft Store            | `Microsoft.WindowsStore_8wekyb3d8bbwe`               |
| Películas y TV                | `Microsoft.ZuneVideo_8wekyb3d8bbwe`                  |
| OneDrive                   | `microsoft.microsoftskydrive_8wekyb3d8bbwe`          |
| Fotos                     | `Microsoft.Windows.Photos_8wekyb3d8bbwe`             |
| Configuración                   | `HolographicSystemSettings_cw5n1h2txyewy`            |
| Sugerencias                       | `Microsoft.HoloLensTips_8wekyb3d8bbwe`               |

- 1 - El bloqueo de Instalador de aplicación solo bloqueará la aplicación Instalador de aplicación y no las aplicaciones instaladas desde otros orígenes, como el Microsoft Store o desde la solución MDM.

### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso de WDAC para bloquear la nueva versión de Microsoft Edge

Para los administradores de TI que buscan actualizar su directiva [WDAC](windows-defender-application-control-wdac.md) para bloquear la nueva [aplicación Microsoft Edge](hololens-new-edge.md), deberá agregar lo siguiente a la directiva.

```xml
<Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" />
```

### <a name="how-to-find-a-package-family-name"></a>Cómo buscar un nombre de familia de paquetes

Si una aplicación no está en esta lista, un usuario puede usar Portal de dispositivos, conectado a un HoloLens 2 que ha instalado la aplicación que desea que se bloquee, para determinar packageRelativeID y, a partir de ahí, obtener PackageFamilyName.

1. Instale la aplicación en el HoloLens 2 dispositivo.

1. Abra Configuración -> Actualizaciones & Seguridad -> Para desarrolladores, habilite  el modo Desarrollador y, a continuación, **Portal de dispositivos.**

   Para obtener más detalles e instrucciones, consulte [Configuración y uso del portal de dispositivos aquí.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Una Portal de dispositivos conexión, vaya a **Vistas y,** a continuación, **a Aplicaciones.**

1. En el panel Aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada.

1. Busque PackageRelativeID.

1. Copie los caracteres de la aplicación antes `!` de , estos caracteres serán packageFamilyName.
