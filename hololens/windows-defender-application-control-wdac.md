---
title: Control de aplicaciones de Windows Defender (WDAC)
description: Información general sobre Windows Defender application control y cómo usarlo para administrar HoloLens de realidad mixta.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033947"
---
# <a name="windows-defender-application-control---wdac"></a>Control de aplicaciones de Microsoft Defender: WDAC

## <a name="overview"></a>Información general

WDAC le permite configurar HoloLens bloquear el inicio de aplicaciones. Es diferente del modo quiosco, donde la interfaz de usuario oculta las aplicaciones, pero todavía se pueden iniciar. Con WDAC, puede ver las aplicaciones, pero no se pueden iniciar.

> [!NOTE]
> Cuando los usuarios finales intentan iniciar una aplicación bloqueada por WDAC en HoloLens, no se les notificará si no pueden iniciar la aplicación.

Un dispositivo puede tener asignada más de una directiva WDAC. Si hay varias directivas WDAC establecidas en un sistema, las más restrictivas tienen efecto. 

La siguiente es una guía para que los usuarios aprendan a usar [WDAC](/mem/intune/configuration/custom-profile-hololens)y Windows PowerShell para permitir o bloquear aplicaciones en HoloLens 2 dispositivos con Microsoft Intune .

Cuando los usuarios buscan aplicaciones instaladas en su equipo Windows 10 mediante el primer paso de ejemplo, es posible que deban realizar algunos intentos para restringir los resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si no conoce el nombre completo del paquete, es posible que tenga que ejecutar "Get-AppxPackage -name \* YourBestGuess" varias veces para \* encontrarlo. Después, una vez que tenga el nombre, ejecute "$package 1 = Get-AppxPackage -name Actual.PackageName"

Por ejemplo, si ejecuta el código siguiente para Microsoft Edge devolverá más de un resultado, pero en esa lista puede identificar que el nombre completo que necesita es Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Nombres de familia de paquetes para aplicaciones HoloLens

En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para las aplicaciones que solo están instaladas en HoloLens con sus nombres de familia de paquetes. A veces hay aplicaciones que puede usar que no están en el equipo de escritorio que desea agregar a la directiva.

Esta es una lista de aplicaciones de uso In-Box para HoloLens 2 dispositivos.

| Nombre de la aplicación                   | Nombre de familia del paquete                                |
|----------------------------|----------------------------------------------------|
| Visor 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalador de aplicación              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendario                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Cámara                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Centro de opiniones               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorador de archivos              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Correo                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Películas y TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Configuración                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Sugerencias                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1- El bloqueo de Instalador de aplicación solo bloqueará la aplicación Instalador de aplicación y no las aplicaciones instaladas desde otros orígenes, como la Microsoft Store o desde la solución MDM.

### <a name="how-to-find-a-package-family-name"></a>Cómo buscar un nombre de familia de paquetes

Si una aplicación no está en esta lista, un usuario puede usar Portal de dispositivos, conectado a un HoloLens 2 que ha instalado la aplicación que desea bloquearse, para determinar packageRelativeID y, a partir de ahí, obtener PackageFamilyName.

1. Instale la aplicación en el HoloLens 2 dispositivo. 
1. Abra Configuración -> Actualizaciones & Seguridad -> Para desarrolladores y habilite  el modo de desarrollador y, a continuación, **portal de dispositivos.** 
    1. Obtenga más instrucciones sobre la configuración y [el uso del portal de dispositivos aquí.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Una Portal de dispositivos conexión, vaya a **Vistas y,** a continuación, **Aplicaciones**. 
1. En el panel Aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada. 
1. Busque PackageRelativeID. 
1. Copie los caracteres de la aplicación antes `!` de , estos caracteres serán packageFamilyName.

