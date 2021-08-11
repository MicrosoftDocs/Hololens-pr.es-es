---
title: 'Control de aplicaciones de Microsoft Defender: WDAC'
description: Información general sobre Windows Defender application control y cómo usarlo para administrar HoloLens dispositivos de realidad mixta.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ab05f1bbe1570d4966932d6f8ac857e5bd2d8a7d3a8f5b93aaba0335eda05b01
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665563"
---
# <a name="windows-defender-application-control---wdac"></a>Control de aplicaciones de Microsoft Defender: WDAC

WDAC permite a un administrador de TI configurar sus dispositivos para bloquear el inicio de aplicaciones en los dispositivos. Esto es diferente de los métodos de restricción de dispositivos, como el modo de pantalla completa, donde el usuario se presenta con una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero todavía se pueden iniciar. Mientras se implementa WDAC, las aplicaciones siguen estando visibles en la lista Todas las aplicaciones, pero WDAC impide que el usuario del dispositivo pueda iniciar esas aplicaciones y procesos.

Se puede asignar más de una directiva WDAC a un dispositivo. Si se establecen varias directivas WDAC en un sistema, las más restrictivas tienen efecto. 

> [!NOTE]
> Cuando los usuarios finales intentan iniciar una aplicación bloqueada por WDAC, en HoloLens no recibirán una notificación sobre cómo no poder iniciar esa aplicación.

La siguiente es una guía para que los usuarios aprendan a usar [WDAC](/mem/intune/configuration/custom-profile-hololens)y Windows PowerShell para permitir o bloquear aplicaciones en HoloLens 2 dispositivos con Microsoft Intune .

Cuando los usuarios buscan aplicaciones instaladas en su equipo Windows 10 mediante el primer paso de ejemplo, es posible que deban realizar algunos intentos para restringir los resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si no conoce el nombre completo del paquete, es posible que tenga que ejecutar "Get-AppxPackage -name \* YourBestGuess" varias veces para \* encontrarlo. Después, una vez que tenga el nombre, ejecute "$package 1 = Get-AppxPackage -name Actual.PackageName"

Por ejemplo, si ejecuta lo siguiente para Microsoft Edge devolverá más de un resultado, pero en esa lista puede identificar que el nombre completo que necesita es Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Nombres de familia de paquetes para aplicaciones en HoloLens

En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para aplicaciones que solo se instalan en HoloLens con sus nombres de familia de paquetes. A veces hay aplicaciones que puede usar que no están en el equipo de escritorio que desea agregar a la directiva.

Esta es una lista de aplicaciones de uso frecuente In-Box aplicaciones para HoloLens 2 dispositivos.

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
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Películas y TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Configuración                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Sugerencias                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1- El bloqueo de Instalador de aplicación solo bloqueará la aplicación Instalador de aplicación y no las aplicaciones instaladas desde otros orígenes, como el Microsoft Store o desde la solución MDM.

### <a name="how-to-find-a-package-family-name"></a>Cómo buscar un nombre de familia de paquetes

Si una aplicación no está en esta lista, un usuario puede usar Portal de dispositivos, conectado a un HoloLens 2 que ha instalado la aplicación que desea que se bloquee, para determinar packageRelativeID y, a partir de ahí, obtener packageFamilyName.

1. Instale la aplicación en el HoloLens 2 dispositivo. 
1. Abra Configuración -> Actualizaciones & Seguridad -> Para desarrolladores y habilite  el modo desarrollador y, a continuación, portal **de dispositivos.** 
    1. Puede encontrar más información sobre la [configuración y el uso del portal de dispositivos aquí.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Una Portal de dispositivos conexión, vaya a **Vistas y,** a continuación, **a Aplicaciones.** 
1. En el panel Aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada. 
1. Busque PackageRelativeID. 
1. Copie los caracteres de la aplicación antes de !, estos caracteres serán packageFamilyName.


