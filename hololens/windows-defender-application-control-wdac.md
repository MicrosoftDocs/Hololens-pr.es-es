---
title: 'Control de aplicaciones de Microsoft Defender: WDAC'
description: Información general sobre Windows Defender application control y cómo usarlo para administrar HoloLens de realidad mixta.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639937"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="fe752-103">Control de aplicaciones de Microsoft Defender: WDAC</span><span class="sxs-lookup"><span data-stu-id="fe752-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="fe752-104">WDAC permite a un administrador de TI configurar sus dispositivos para bloquear el inicio de aplicaciones en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fe752-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="fe752-105">Esto es diferente de los métodos de restricción de dispositivos, como el modo de pantalla completa, donde se presenta al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero todavía se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="fe752-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="fe752-106">Mientras se implementa WDAC, las aplicaciones siguen estando visibles en la lista Todas las aplicaciones, pero WDAC impide que el usuario del dispositivo pueda iniciar esas aplicaciones y procesos.</span><span class="sxs-lookup"><span data-stu-id="fe752-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="fe752-107">Un dispositivo puede tener asignada más de una directiva WDAC.</span><span class="sxs-lookup"><span data-stu-id="fe752-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="fe752-108">Si hay varias directivas WDAC establecidas en un sistema, las más restrictivas tienen efecto.</span><span class="sxs-lookup"><span data-stu-id="fe752-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="fe752-109">Cuando los usuarios finales intentan iniciar una aplicación bloqueada por WDAC, en HoloLens no recibirán una notificación sobre no poder iniciar esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="fe752-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="fe752-110">La siguiente es una guía para que los usuarios aprendan a usar [WDAC](/mem/intune/configuration/custom-profile-hololens)y Windows PowerShell para permitir o bloquear aplicaciones en HoloLens 2 dispositivos con Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="fe752-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="fe752-111">Cuando los usuarios buscan aplicaciones instaladas en su equipo Windows 10 mediante el primer paso de ejemplo, es posible que deban realizar algunos intentos para restringir los resultados.</span><span class="sxs-lookup"><span data-stu-id="fe752-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="fe752-112">Si no conoce el nombre completo del paquete, es posible que tenga que ejecutar "Get-AppxPackage -name \* YourBestGuess" varias veces para \* encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="fe752-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="fe752-113">Después, una vez que tenga el nombre, ejecute "$package 1 = Get-AppxPackage -name Actual.PackageName"</span><span class="sxs-lookup"><span data-stu-id="fe752-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="fe752-114">Por ejemplo, si ejecuta lo siguiente para Microsoft Edge devolverá más de un resultado, pero en esa lista puede identificar que el nombre completo que necesita es Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="fe752-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="fe752-115">Nombres de familia de paquetes para aplicaciones en HoloLens</span><span class="sxs-lookup"><span data-stu-id="fe752-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="fe752-116">En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para aplicaciones que solo se instalan en HoloLens con sus nombres de familia de paquetes.</span><span class="sxs-lookup"><span data-stu-id="fe752-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="fe752-117">A veces hay aplicaciones que puede usar que no están en el equipo de escritorio que desea agregar a la directiva.</span><span class="sxs-lookup"><span data-stu-id="fe752-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="fe752-118">A continuación se muestra una lista de aplicaciones de In-Box para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fe752-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="fe752-119">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="fe752-119">App Name</span></span>                   | <span data-ttu-id="fe752-120">Nombre de familia del paquete</span><span class="sxs-lookup"><span data-stu-id="fe752-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="fe752-121">Visor 3D</span><span class="sxs-lookup"><span data-stu-id="fe752-121">3D Viewer</span></span>                  | <span data-ttu-id="fe752-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="fe752-123">Instalador de aplicación</span><span class="sxs-lookup"><span data-stu-id="fe752-123">App Installer</span></span>              | <span data-ttu-id="fe752-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fe752-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="fe752-125">Calendario</span><span class="sxs-lookup"><span data-stu-id="fe752-125">Calendar</span></span>                   | <span data-ttu-id="fe752-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="fe752-127">Cámara</span><span class="sxs-lookup"><span data-stu-id="fe752-127">Camera</span></span>                     | <span data-ttu-id="fe752-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="fe752-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="fe752-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="fe752-129">Cortana</span></span>                    | <span data-ttu-id="fe752-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="fe752-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="fe752-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="fe752-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="fe752-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="fe752-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="fe752-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="fe752-135">Centro de opiniones</span><span class="sxs-lookup"><span data-stu-id="fe752-135">Feedback Hub</span></span>               | <span data-ttu-id="fe752-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="fe752-137">Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="fe752-137">File Explorer</span></span>              | <span data-ttu-id="fe752-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="fe752-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="fe752-139">Correo</span><span class="sxs-lookup"><span data-stu-id="fe752-139">Mail</span></span>                       | <span data-ttu-id="fe752-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="fe752-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="fe752-141">Microsoft Store</span></span>            | <span data-ttu-id="fe752-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="fe752-143">Películas y TV</span><span class="sxs-lookup"><span data-stu-id="fe752-143">Movies & TV</span></span>                | <span data-ttu-id="fe752-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="fe752-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="fe752-145">OneDrive</span></span>                   | <span data-ttu-id="fe752-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="fe752-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="fe752-147">Photos</span></span>                     | <span data-ttu-id="fe752-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="fe752-149">Configuración</span><span class="sxs-lookup"><span data-stu-id="fe752-149">Settings</span></span>                   | <span data-ttu-id="fe752-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="fe752-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="fe752-151">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="fe752-151">Tips</span></span>                       | <span data-ttu-id="fe752-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="fe752-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="fe752-153">1 - El bloqueo de Instalador de aplicación solo bloqueará la aplicación Instalador de aplicación y no las aplicaciones instaladas desde otros orígenes, como la Microsoft Store o desde la solución MDM.</span><span class="sxs-lookup"><span data-stu-id="fe752-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="fe752-154">Cómo buscar un nombre de familia de paquetes</span><span class="sxs-lookup"><span data-stu-id="fe752-154">How to find a Package Family Name</span></span>

<span data-ttu-id="fe752-155">Si una aplicación no está en esta lista, un usuario puede usar Portal de dispositivos, conectado a un HoloLens 2 que ha instalado la aplicación que desea bloquearse, para determinar packageRelativeID y, a partir de ahí, obtener PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="fe752-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="fe752-156">Instale la aplicación en el HoloLens 2 dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe752-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="fe752-157">Abra Configuración -> Actualizaciones & Seguridad -> Para desarrolladores y habilite  el modo desarrollador y, a continuación, **portal de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="fe752-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="fe752-158">Obtenga más instrucciones sobre la configuración y [el uso del portal de dispositivos aquí.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="fe752-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="fe752-159">Una Portal de dispositivos conexión, vaya a **Vistas y,** a continuación, **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="fe752-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="fe752-160">En el panel Aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada.</span><span class="sxs-lookup"><span data-stu-id="fe752-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="fe752-161">Busque PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="fe752-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="fe752-162">Copie los caracteres de la aplicación antes de !, estos caracteres serán packageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="fe752-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


