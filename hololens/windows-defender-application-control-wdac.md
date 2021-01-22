---
title: 'Control de aplicaciones de Windows Defender: WDAC'
description: Información general sobre Windows Defender control de aplicaciones y cómo usarlo para administrar dispositivos holoLens de realidad mixta.
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284141"
---
# Control de aplicaciones de Windows Defender: WDAC

WDAC permite a un administrador de TI configurar sus dispositivos para bloquear el inicio de aplicaciones en dispositivos. Esto es diferente de los métodos de restricción de dispositivos, como el modo de pantalla completa, donde se presenta al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero aún se pueden iniciar. Mientras se implementa WDAC, las aplicaciones siguen estando visibles en la lista Todas las aplicaciones, pero WDAC impide que el usuario del dispositivo pueda iniciar esas aplicaciones y procesos.

Un dispositivo puede tener asignada más de una directiva WDAC. Si se establecen varias directivas WDAC en un sistema, las más restrictivas tienen efecto. 

> [!NOTE]
> Cuando los usuarios finales intenten iniciar una aplicación bloqueada por WDAC, en HoloLens no recibirán una notificación sobre no poder iniciar esa aplicación.

La siguiente es una guía para que los usuarios aprendan a usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en [dispositivos HoloLens 2 con Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Cuando los usuarios buscan aplicaciones instaladas en su pc con Windows 10 con el primer paso de ejemplo, es posible que deban realizar algunos intentos para restringir los resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si no conoces el nombre completo del paquete, es posible que debas ejecutar "Get-AppxPackage -name \*YourBestGuess\*" varias veces para encontrarlo. A continuación, una vez que tenga el nombre, ejecute '$package 1 = Get-AppxPackage -name Actual.PackageName'

Por ejemplo, ejecutar lo siguiente para Microsoft Edge devolverá más de un resultado, pero en esa lista puede identificar que el nombre completo que necesita es Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## Nombres de familia de paquete para aplicaciones en HoloLens

En la guía vinculada anteriormente, puedes editar manualmente newPolicy.xml y agregar reglas para las aplicaciones que solo están instaladas en HoloLens con sus nombres de familia de paquetes. A veces hay aplicaciones que puedes usar y que no están en el equipo de escritorio que quieres agregar a la directiva.

Esta es una lista de aplicaciones de In-Box para dispositivos HoloLens 2.

| Nombre de la aplicación                   | Nombre de familia de paquete                                |
|----------------------------|----------------------------------------------------|
| Visor 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalador de aplicación              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| Calendario                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Cámara                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Centro de opiniones               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorador de archivos              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Correo                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Películas y TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft.Windows.Fotos_8wekyb3d8bbwe             |
| Configuración                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Sugerencias                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1- Bloquear el Instalador de aplicación solo bloqueará la aplicación Instalador de aplicación y no las aplicaciones instaladas desde otros orígenes, como Microsoft Store o desde la solución MDM.

### Cómo encontrar un nombre de familia de paquete

Si una aplicación no está en esta lista, un usuario puede usar Device Portal, conectado a un HoloLens 2 que ha instalado la aplicación para bloquearse, para determinar el PackageRelativeID y, desde allí, obtener packageFamilyName.

1. Instala la aplicación en el dispositivo HoloLens 2. 
1. Abra Configuración -> actualizaciones & Seguridad -> Para desarrolladores, habilite el modo de desarrollador **y,** a continuación, **Device Portal.** 
    1. Aquí encontrará más instrucciones detalladas sobre [la configuración y el uso del portal de dispositivos.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Una vez conectado Device Portal, vaya a **Vistas y,** a continuación, **a Aplicaciones.** 
1. En el panel Aplicaciones instaladas, usa la lista desplegable para seleccionar la aplicación instalada. 
1. Busque packageRelativeID. 
1. Copia los caracteres de la aplicación antes de !, estos caracteres serán tu PackageFamilyName.


