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
# <span data-ttu-id="f97c8-103">Control de aplicaciones de Windows Defender: WDAC</span><span class="sxs-lookup"><span data-stu-id="f97c8-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="f97c8-104">WDAC permite a un administrador de TI configurar sus dispositivos para bloquear el inicio de aplicaciones en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f97c8-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="f97c8-105">Esto es diferente de los métodos de restricción de dispositivos, como el modo de pantalla completa, donde se presenta al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero aún se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="f97c8-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="f97c8-106">Mientras se implementa WDAC, las aplicaciones siguen estando visibles en la lista Todas las aplicaciones, pero WDAC impide que el usuario del dispositivo pueda iniciar esas aplicaciones y procesos.</span><span class="sxs-lookup"><span data-stu-id="f97c8-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="f97c8-107">Un dispositivo puede tener asignada más de una directiva WDAC.</span><span class="sxs-lookup"><span data-stu-id="f97c8-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="f97c8-108">Si se establecen varias directivas WDAC en un sistema, las más restrictivas tienen efecto.</span><span class="sxs-lookup"><span data-stu-id="f97c8-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="f97c8-109">Cuando los usuarios finales intenten iniciar una aplicación bloqueada por WDAC, en HoloLens no recibirán una notificación sobre no poder iniciar esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="f97c8-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="f97c8-110">La siguiente es una guía para que los usuarios aprendan a usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en [dispositivos HoloLens 2 con Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)</span><span class="sxs-lookup"><span data-stu-id="f97c8-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="f97c8-111">Cuando los usuarios buscan aplicaciones instaladas en su pc con Windows 10 con el primer paso de ejemplo, es posible que deban realizar algunos intentos para restringir los resultados.</span><span class="sxs-lookup"><span data-stu-id="f97c8-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="f97c8-112">Si no conoces el nombre completo del paquete, es posible que debas ejecutar "Get-AppxPackage -name \*YourBestGuess\*" varias veces para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="f97c8-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="f97c8-113">A continuación, una vez que tenga el nombre, ejecute '$package 1 = Get-AppxPackage -name Actual.PackageName'</span><span class="sxs-lookup"><span data-stu-id="f97c8-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="f97c8-114">Por ejemplo, ejecutar lo siguiente para Microsoft Edge devolverá más de un resultado, pero en esa lista puede identificar que el nombre completo que necesita es Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="f97c8-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="f97c8-115">Nombres de familia de paquete para aplicaciones en HoloLens</span><span class="sxs-lookup"><span data-stu-id="f97c8-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="f97c8-116">En la guía vinculada anteriormente, puedes editar manualmente newPolicy.xml y agregar reglas para las aplicaciones que solo están instaladas en HoloLens con sus nombres de familia de paquetes.</span><span class="sxs-lookup"><span data-stu-id="f97c8-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="f97c8-117">A veces hay aplicaciones que puedes usar y que no están en el equipo de escritorio que quieres agregar a la directiva.</span><span class="sxs-lookup"><span data-stu-id="f97c8-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="f97c8-118">Esta es una lista de aplicaciones de In-Box para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f97c8-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="f97c8-119">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f97c8-119">App Name</span></span>                   | <span data-ttu-id="f97c8-120">Nombre de familia de paquete</span><span class="sxs-lookup"><span data-stu-id="f97c8-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="f97c8-121">Visor 3D</span><span class="sxs-lookup"><span data-stu-id="f97c8-121">3D Viewer</span></span>                  | <span data-ttu-id="f97c8-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="f97c8-123">Instalador de aplicación</span><span class="sxs-lookup"><span data-stu-id="f97c8-123">App Installer</span></span>              | <span data-ttu-id="f97c8-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="f97c8-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="f97c8-125">Calendario</span><span class="sxs-lookup"><span data-stu-id="f97c8-125">Calendar</span></span>                   | <span data-ttu-id="f97c8-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="f97c8-127">Cámara</span><span class="sxs-lookup"><span data-stu-id="f97c8-127">Camera</span></span>                     | <span data-ttu-id="f97c8-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f97c8-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="f97c8-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="f97c8-129">Cortana</span></span>                    | <span data-ttu-id="f97c8-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="f97c8-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="f97c8-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="f97c8-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="f97c8-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="f97c8-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="f97c8-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="f97c8-135">Centro de opiniones</span><span class="sxs-lookup"><span data-stu-id="f97c8-135">Feedback Hub</span></span>               | <span data-ttu-id="f97c8-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="f97c8-137">Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="f97c8-137">File Explorer</span></span>              | <span data-ttu-id="f97c8-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f97c8-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="f97c8-139">Correo</span><span class="sxs-lookup"><span data-stu-id="f97c8-139">Mail</span></span>                       | <span data-ttu-id="f97c8-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="f97c8-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f97c8-141">Microsoft Store</span></span>            | <span data-ttu-id="f97c8-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="f97c8-143">Películas y TV</span><span class="sxs-lookup"><span data-stu-id="f97c8-143">Movies & TV</span></span>                | <span data-ttu-id="f97c8-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="f97c8-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f97c8-145">OneDrive</span></span>                   | <span data-ttu-id="f97c8-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="f97c8-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="f97c8-147">Photos</span></span>                     | <span data-ttu-id="f97c8-148">Microsoft.Windows.Fotos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="f97c8-149">Configuración</span><span class="sxs-lookup"><span data-stu-id="f97c8-149">Settings</span></span>                   | <span data-ttu-id="f97c8-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f97c8-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="f97c8-151">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="f97c8-151">Tips</span></span>                       | <span data-ttu-id="f97c8-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f97c8-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="f97c8-153">1- Bloquear el Instalador de aplicación solo bloqueará la aplicación Instalador de aplicación y no las aplicaciones instaladas desde otros orígenes, como Microsoft Store o desde la solución MDM.</span><span class="sxs-lookup"><span data-stu-id="f97c8-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="f97c8-154">Cómo encontrar un nombre de familia de paquete</span><span class="sxs-lookup"><span data-stu-id="f97c8-154">How to find a Package Family Name</span></span>

<span data-ttu-id="f97c8-155">Si una aplicación no está en esta lista, un usuario puede usar Device Portal, conectado a un HoloLens 2 que ha instalado la aplicación para bloquearse, para determinar el PackageRelativeID y, desde allí, obtener packageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="f97c8-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="f97c8-156">Instala la aplicación en el dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f97c8-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="f97c8-157">Abra Configuración -> actualizaciones & Seguridad -> Para desarrolladores, habilite el modo de desarrollador **y,** a continuación, **Device Portal.**</span><span class="sxs-lookup"><span data-stu-id="f97c8-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="f97c8-158">Aquí encontrará más instrucciones detalladas sobre [la configuración y el uso del portal de dispositivos.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="f97c8-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="f97c8-159">Una vez conectado Device Portal, vaya a **Vistas y,** a continuación, **a Aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="f97c8-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="f97c8-160">En el panel Aplicaciones instaladas, usa la lista desplegable para seleccionar la aplicación instalada.</span><span class="sxs-lookup"><span data-stu-id="f97c8-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="f97c8-161">Busque packageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="f97c8-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="f97c8-162">Copia los caracteres de la aplicación antes de !, estos caracteres serán tu PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="f97c8-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


