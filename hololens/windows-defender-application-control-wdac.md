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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163126"
---
# <span data-ttu-id="f2b90-103">Control de aplicaciones de Windows Defender (WDAC)</span><span class="sxs-lookup"><span data-stu-id="f2b90-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="f2b90-104">WDAC permite que un administrador de ti Configure sus dispositivos para bloquear el inicio de aplicaciones en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f2b90-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="f2b90-105">Esto es diferente a los métodos de restricción de dispositivo, como el modo de pantalla completa, en los que se muestra al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero que aún se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="f2b90-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="f2b90-106">Aunque se implementa WDAC, las aplicaciones siguen estando visibles en la lista de todas las aplicaciones, pero WDAC evita que el usuario del dispositivo pueda iniciar dichas aplicaciones y procesos.</span><span class="sxs-lookup"><span data-stu-id="f2b90-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="f2b90-107">Es posible que se asigne más de una directiva de WDAC a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f2b90-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="f2b90-108">Si se establecen varias directivas de WDAC en un sistema, las más restrictivas se aplican.</span><span class="sxs-lookup"><span data-stu-id="f2b90-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="f2b90-109">Cuando los usuarios finales intentan iniciar una aplicación que está bloqueada por WDAC, en HoloLens no recibirán una notificación acerca de que no se puede iniciar esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2b90-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="f2b90-110">La siguiente es una guía para que los usuarios aprendan a [usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en dispositivos HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="f2b90-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="f2b90-111">Cuando los usuarios buscan aplicaciones instaladas en su equipo con Windows 10 con el primer ejemplo de paso, es posible que tengan que realizar algunos intentos para restringir los resultados.</span><span class="sxs-lookup"><span data-stu-id="f2b90-111">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="f2b90-112">Si no conoces el nombre completo del paquete, es posible que tengas que ejecutar "Get-AppxPackage-Name \ \* YourBestGuess \ \*" unas cuantas veces para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="f2b90-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="f2b90-113">Después, cuando tenga el nombre, ejecute ' $package 1 = Get-AppxPackage-Name real. PackageName '</span><span class="sxs-lookup"><span data-stu-id="f2b90-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="f2b90-114">Por ejemplo, ejecutar lo siguiente para Edge devolverá más de un resultado, pero a partir de esa lista puede identificar que el nombre completo que necesita es Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="f2b90-114">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="f2b90-115">Nombres de familia de paquetes para las aplicaciones en HoloLens</span><span class="sxs-lookup"><span data-stu-id="f2b90-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="f2b90-116">En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para aplicaciones que solo se instalan en HoloLens con sus nombres de familia de paquetes.</span><span class="sxs-lookup"><span data-stu-id="f2b90-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="f2b90-117">A veces, hay aplicaciones que puede usar y que no se encuentran en su equipo de escritorio y que desea agregar a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f2b90-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="f2b90-118">Esta es una lista de aplicaciones de uso frecuente y In-Box para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f2b90-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="f2b90-119">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f2b90-119">App Name</span></span>                   | <span data-ttu-id="f2b90-120">Nombre de familia de paquete</span><span class="sxs-lookup"><span data-stu-id="f2b90-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="f2b90-121">Visor 3D</span><span class="sxs-lookup"><span data-stu-id="f2b90-121">3D Viewer</span></span>                  | <span data-ttu-id="f2b90-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="f2b90-123">Instalador de aplicación</span><span class="sxs-lookup"><span data-stu-id="f2b90-123">App Installer</span></span>              | <span data-ttu-id="f2b90-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="f2b90-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="f2b90-125">Calendario</span><span class="sxs-lookup"><span data-stu-id="f2b90-125">Calendar</span></span>                   | <span data-ttu-id="f2b90-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="f2b90-127">Cámara</span><span class="sxs-lookup"><span data-stu-id="f2b90-127">Camera</span></span>                     | <span data-ttu-id="f2b90-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f2b90-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="f2b90-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="f2b90-129">Cortana</span></span>                    | <span data-ttu-id="f2b90-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="f2b90-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="f2b90-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="f2b90-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="f2b90-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="f2b90-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="f2b90-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="f2b90-135">Centro de opiniones</span><span class="sxs-lookup"><span data-stu-id="f2b90-135">Feedback Hub</span></span>               | <span data-ttu-id="f2b90-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="f2b90-137">Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="f2b90-137">File Explorer</span></span>              | <span data-ttu-id="f2b90-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f2b90-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="f2b90-139">Correo</span><span class="sxs-lookup"><span data-stu-id="f2b90-139">Mail</span></span>                       | <span data-ttu-id="f2b90-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="f2b90-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f2b90-141">Microsoft Store</span></span>            | <span data-ttu-id="f2b90-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="f2b90-143">Películas y TV</span><span class="sxs-lookup"><span data-stu-id="f2b90-143">Movies & TV</span></span>                | <span data-ttu-id="f2b90-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="f2b90-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f2b90-145">OneDrive</span></span>                   | <span data-ttu-id="f2b90-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="f2b90-147">Fotos</span><span class="sxs-lookup"><span data-stu-id="f2b90-147">Photos</span></span>                     | <span data-ttu-id="f2b90-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="f2b90-149">Configuración</span><span class="sxs-lookup"><span data-stu-id="f2b90-149">Settings</span></span>                   | <span data-ttu-id="f2b90-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="f2b90-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="f2b90-151">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="f2b90-151">Tips</span></span>                       | <span data-ttu-id="f2b90-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="f2b90-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="f2b90-153">1: el instalador de la aplicación de bloqueo solo bloqueará la aplicación de instalación de la aplicación y no las aplicaciones instaladas desde otros orígenes, como Microsoft Store o desde la solución MDM.</span><span class="sxs-lookup"><span data-stu-id="f2b90-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="f2b90-154">Cómo buscar un nombre de familia de paquete</span><span class="sxs-lookup"><span data-stu-id="f2b90-154">How to find a Package Family Name</span></span>

<span data-ttu-id="f2b90-155">Si una aplicación no se encuentra en esta lista, es posible que un usuario Use Device portal, conectado a HoloLens 2 que ha instalado la aplicación que se ha bloqueado, para determinar el PackageRelativeID y desde allí obtener el PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="f2b90-155">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="f2b90-156">Instala la aplicación en tu dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f2b90-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="f2b90-157">Abrir configuración: > actualizaciones & seguridad: > para los desarrolladores y habilitar el **modo de desarrollador** y el portal de **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f2b90-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="f2b90-158">Más instrucciones para obtener más información sobre la [configuración y el uso de Device portal aquí](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="f2b90-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="f2b90-159">Una vez conectado el portal de dispositivos, vaya a **vistas** y después a **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f2b90-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="f2b90-160">En el panel aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada.</span><span class="sxs-lookup"><span data-stu-id="f2b90-160">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="f2b90-161">Busque el PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="f2b90-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="f2b90-162">Copia los caracteres de la aplicación antes de la!, será tu PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="f2b90-162">Copy app characters before the !, this will be your PackageFamilyName.</span></span>


