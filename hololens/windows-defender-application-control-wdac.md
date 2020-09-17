---
title: Control de aplicaciones de Windows Defender-WDAC
description: Información general sobre qué es WDAC y cómo usar para administrar dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016808"
---
# Control de aplicaciones de Windows Defender-WDAC

WDAC permite que un administrador de ti Configure sus dispositivos para bloquear el inicio de aplicaciones en dispositivos. Esto es diferente a los métodos de restricción de dispositivo, como el modo de pantalla completa, en los que se muestra al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero que aún se pueden iniciar. Aunque se implementa WDAC, las aplicaciones siguen estando visibles en la lista de todas las aplicaciones, pero WDAC evita que el usuario del dispositivo pueda iniciar dichas aplicaciones y procesos.

> [!NOTE]
> Cuando los usuarios finales intentan iniciar una aplicación que está bloqueada por WDAC, en HoloLens no recibirán una notificación acerca de que no se puede iniciar esa aplicación.

La siguiente es una guía para que los usuarios aprendan a [usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en dispositivos HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Cuando los usuarios buscan aplicaciones instaladas en su equipo con Windows 10 con el primer ejemplo de paso, es posible que tengan que realizar algunos intentos para restringir los resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si no conoces el nombre completo del paquete, es posible que tengas que ejecutar "Get-AppxPackage-Name \ * YourBestGuess \ *" unas cuantas veces para encontrarlo. Después, cuando tenga el nombre, ejecute ' $package 1 = get-AppxPackage-Name real. PackageName '

Por ejemplo, ejecutar lo siguiente para Edge devolverá más de un resultado, pero a partir de esa lista puede identificar que el nombre completo que necesita es Microsoft. MicrosoftEdge. 

```powershell
Get-AppxPackage -name *edge*
``` 

## Nombres de familia de paquetes para las aplicaciones en HoloLens

En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para aplicaciones que solo se instalan en HoloLens con sus nombres de familia de paquetes. A veces, hay aplicaciones que puede usar y que no se encuentran en su equipo de escritorio y que desea agregar a la Directiva. 

A continuación se muestra una lista de las aplicaciones usadas con más frecuencia para los dispositivos HoloLens 2.

| Nombre de la aplicación                   | Nombre de familia de paquete                                |
|----------------------------|----------------------------------------------------|
| Visor 3D                  | Microsoft. Microsoft3DViewer_8wekyb3d8bbwe          |
| Calendario                   | Microsoft. windowscommunicationsapps_8wekyb3d8bbwe  |
| Cámara                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft. 549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft. Dynamics365. Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Centro de opiniones               | Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe         |
| Explorador de archivos              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Correo                       | Microsoft. windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft. WindowsStore_8wekyb3d8bbwe               |
| Películas y TV                | Microsoft. ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | Microsoft. microsoftskydrive_8wekyb3d8bbwe          |
| Fotos                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Configuración                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Sugerencias                       | Microsoft. HoloLensTips_8wekyb3d8bbwe               |

Si una aplicación no se encuentra en esta lista, es posible que un usuario Use Device portal, conectado a HoloLens 2 que ha instalado la aplicación que se ha bloqueado, para determinar el PackageRelativeID y desde allí obtener el PackageFamilyName.

1. Instala la aplicación en tu dispositivo HoloLens 2. 
1. Abra configuración-> actualizaciones & securtiy-> para desarrolladores y habilitar el **modo de desarrollador** y, a continuación, **Device portal**. 
    1. Más instrucciones para obtener más información sobre la [configuración y el uso de Device portal aquí](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Una vez conectado el portal de dispositivos, vaya a **vistas** y después a **aplicaciones**. 
1. En el panel aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada. 
1. Busque el PackageRelativeID. 
1. Copia los caracteres de la aplicación antes de la!, será tu PackageFamilyName.

