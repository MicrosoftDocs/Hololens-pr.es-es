---
title: Control de aplicaciones de Windows Defender (WDAC)
description: Información general sobre qué es WDAC y cómo usar para administrar dispositivos HoloLens.
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
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135580"
---
# Control de aplicaciones de Windows Defender (WDAC)

WDAC permite que un administrador de ti Configure sus dispositivos para bloquear el inicio de aplicaciones en dispositivos. Esto es diferente a los métodos de restricción de dispositivo, como el modo de pantalla completa, en los que se muestra al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero que aún se pueden iniciar. Aunque se implementa WDAC, las aplicaciones siguen estando visibles en la lista de todas las aplicaciones, pero WDAC evita que el usuario del dispositivo pueda iniciar dichas aplicaciones y procesos.

> [!NOTE]
> Cuando los usuarios finales intentan iniciar una aplicación que está bloqueada por WDAC, en HoloLens no recibirán una notificación acerca de que no se puede iniciar esa aplicación.

La siguiente es una guía para que los usuarios aprendan a [usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en dispositivos HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Cuando los usuarios buscan aplicaciones instaladas en su equipo con Windows 10 con el primer ejemplo de paso, es posible que tengan que realizar algunos intentos para restringir los resultados.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Si no conoces el nombre completo del paquete, es posible que tengas que ejecutar "Get-AppxPackage-Name \ * YourBestGuess \ *" unas cuantas veces para encontrarlo. Después, cuando tenga el nombre, ejecute ' $package 1 = Get-AppxPackage-Name real. PackageName '

Por ejemplo, ejecutar lo siguiente para Edge devolverá más de un resultado, pero a partir de esa lista puede identificar que el nombre completo que necesita es Microsoft. MicrosoftEdge. 

```powershell
Get-AppxPackage -name *edge*
``` 

## Nombres de familia de paquetes para las aplicaciones en HoloLens

En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para aplicaciones que solo se instalan en HoloLens con sus nombres de familia de paquetes. A veces, hay aplicaciones que puede usar y que no se encuentran en su equipo de escritorio y que desea agregar a la Directiva. 

Esta es una lista de aplicaciones de uso frecuente y In-Box para dispositivos HoloLens 2.

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
| Fotos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Configuración                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Sugerencias                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1: el instalador de la aplicación de bloqueo solo bloqueará la aplicación de instalación de la aplicación y no las aplicaciones instaladas desde otros orígenes, como Microsoft Store o desde la solución MDM.

### Cómo buscar un nombre de familia de paquete

Si una aplicación no se encuentra en esta lista, es posible que un usuario Use Device portal, conectado a HoloLens 2 que ha instalado la aplicación que se ha bloqueado, para determinar el PackageRelativeID y desde allí obtener el PackageFamilyName.

1. Instala la aplicación en tu dispositivo HoloLens 2. 
1. Abra configuración-> actualizaciones & securtiy-> para desarrolladores y habilitar el **modo de desarrollador** y, a continuación, **Device portal**. 
    1. Más instrucciones para obtener más información sobre la [configuración y el uso de Device portal aquí](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Una vez conectado el portal de dispositivos, vaya a **vistas** y después a **aplicaciones**. 
1. En el panel aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada. 
1. Busque el PackageRelativeID. 
1. Copia los caracteres de la aplicación antes de la!, será tu PackageFamilyName.

## Ejemplo de instalador de la aplicación de bloqueo

Como ejemplo, es posible que desee bloquear la aplicación de [instalación de aplicaciones](app-deploy-app-installer.md) . Hemos incluido código de ejemplo para este ejemplo. Descarga estas [muestras de código para este ejemplo](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer). En el archivo zip, encontrarás lo siguiente:

| Archivo | Usar |
|-|-|
| compiledPolicy. bin | [Creado en el paso 9, que se usó en el paso final 10.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| mergedPolicy.xml | [Creado en el paso 6.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| WDAC_Set. SyncML | No se usa en WDAC, pero puede usarse para el [CSP EnterpriseModernAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) |

Si desea intentar bloquear inmediatamente una aplicación, en este caso la aplicación de instalación de aplicaciones, use el archivo compiledPolicy. bin y vaya al paso 10 del vínculo anterior. Esto le permitirá probar la directiva personalizada y asegurarse de que las asignaciones de grupo y la configuración de directivas sean correctas. 

Si desea combinar la Directiva de WDAC para bloquear el instalador de la aplicación con otras aplicaciones de la lista anterior o cualquier otra aplicación, puede usar el mergedPolicy.xml archivo y continuar con la combinación de nuevas directivas. Como se indica anteriormente, las directivas de WDAC son aditivas, por lo que no es necesario. 

Puesto que la aplicación de instalación de aplicaciones se inicia mediante el intento de abrir un archivo, se le presentará una pregunta. Tal como se indicó anteriormente, las aplicaciones bloqueadas por WDAC no presentan un aviso de que están bloqueadas, sin embargo, dado que el usuario está intentando abrir un archivo en su dispositivo, se le presenta un error para abrir el archivo. 

![Instalación de aplicaciones bloqueada de WDAC](images\wdac-app-installer-no-launch.jpg)

Si no desea usar WDAC, puede usar como alternativa [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) para quitar la experiencia del instalador de aplicaciones, que es una aplicación después de todo. El resultado es que la aplicación de instalación de aplicaciones se desinstalará del dispositivo. . appx,. msix,. msixbundle y otras extensiones de archivo, así como el protocolo para el inicio de web a aplicaciones, la aplicación de instalación de aplicaciones dejará de administrarlos. El usuario recibirá un mensaje para buscar un controlador para la extensión de archivo/protocolo en la tienda y no encontrará la aplicación porque no está en la lista.