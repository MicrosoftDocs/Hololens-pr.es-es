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
# <span data-ttu-id="90e52-103">Control de aplicaciones de Windows Defender-WDAC</span><span class="sxs-lookup"><span data-stu-id="90e52-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="90e52-104">WDAC permite que un administrador de ti Configure sus dispositivos para bloquear el inicio de aplicaciones en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="90e52-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="90e52-105">Esto es diferente a los métodos de restricción de dispositivo, como el modo de pantalla completa, en los que se muestra al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero que aún se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="90e52-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="90e52-106">Aunque se implementa WDAC, las aplicaciones siguen estando visibles en la lista de todas las aplicaciones, pero WDAC evita que el usuario del dispositivo pueda iniciar dichas aplicaciones y procesos.</span><span class="sxs-lookup"><span data-stu-id="90e52-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="90e52-107">Cuando los usuarios finales intentan iniciar una aplicación que está bloqueada por WDAC, en HoloLens no recibirán una notificación acerca de que no se puede iniciar esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="90e52-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="90e52-108">La siguiente es una guía para que los usuarios aprendan a [usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en dispositivos HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span><span class="sxs-lookup"><span data-stu-id="90e52-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="90e52-109">Cuando los usuarios buscan aplicaciones instaladas en su equipo con Windows 10 con el primer ejemplo de paso, es posible que tengan que realizar algunos intentos para restringir los resultados.</span><span class="sxs-lookup"><span data-stu-id="90e52-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="90e52-110">Si no conoces el nombre completo del paquete, es posible que tengas que ejecutar "Get-AppxPackage-Name \ \* YourBestGuess \ \*" unas cuantas veces para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="90e52-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="90e52-111">Después, cuando tenga el nombre, ejecute ' $package 1 = get-AppxPackage-Name real. PackageName '</span><span class="sxs-lookup"><span data-stu-id="90e52-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="90e52-112">Por ejemplo, ejecutar lo siguiente para Edge devolverá más de un resultado, pero a partir de esa lista puede identificar que el nombre completo que necesita es Microsoft. MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="90e52-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="90e52-113">Nombres de familia de paquetes para las aplicaciones en HoloLens</span><span class="sxs-lookup"><span data-stu-id="90e52-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="90e52-114">En la guía vinculada anteriormente, puede editar manualmente newPolicy.xml y agregar reglas para aplicaciones que solo se instalan en HoloLens con sus nombres de familia de paquetes.</span><span class="sxs-lookup"><span data-stu-id="90e52-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="90e52-115">A veces, hay aplicaciones que puede usar y que no se encuentran en su equipo de escritorio y que desea agregar a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="90e52-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="90e52-116">A continuación se muestra una lista de las aplicaciones usadas con más frecuencia para los dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="90e52-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="90e52-117">Nombre de la aplicación</span><span class="sxs-lookup"><span data-stu-id="90e52-117">App Name</span></span>                   | <span data-ttu-id="90e52-118">Nombre de familia de paquete</span><span class="sxs-lookup"><span data-stu-id="90e52-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="90e52-119">Visor 3D</span><span class="sxs-lookup"><span data-stu-id="90e52-119">3D Viewer</span></span>                  | <span data-ttu-id="90e52-120">Microsoft. Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="90e52-121">Calendario</span><span class="sxs-lookup"><span data-stu-id="90e52-121">Calendar</span></span>                   | <span data-ttu-id="90e52-122">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="90e52-123">Cámara</span><span class="sxs-lookup"><span data-stu-id="90e52-123">Camera</span></span>                     | <span data-ttu-id="90e52-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="90e52-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="90e52-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="90e52-125">Cortana</span></span>                    | <span data-ttu-id="90e52-126">Microsoft. 549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="90e52-127">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="90e52-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="90e52-128">Microsoft. Dynamics365. Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="90e52-129">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="90e52-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="90e52-130">Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="90e52-131">Centro de opiniones</span><span class="sxs-lookup"><span data-stu-id="90e52-131">Feedback Hub</span></span>               | <span data-ttu-id="90e52-132">Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="90e52-133">Explorador de archivos</span><span class="sxs-lookup"><span data-stu-id="90e52-133">File Explorer</span></span>              | <span data-ttu-id="90e52-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="90e52-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="90e52-135">Correo</span><span class="sxs-lookup"><span data-stu-id="90e52-135">Mail</span></span>                       | <span data-ttu-id="90e52-136">Microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="90e52-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="90e52-137">Microsoft Store</span></span>            | <span data-ttu-id="90e52-138">Microsoft. WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="90e52-139">Películas y TV</span><span class="sxs-lookup"><span data-stu-id="90e52-139">Movies & TV</span></span>                | <span data-ttu-id="90e52-140">Microsoft. ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="90e52-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="90e52-141">OneDrive</span></span>                   | <span data-ttu-id="90e52-142">Microsoft. microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="90e52-143">Fotos</span><span class="sxs-lookup"><span data-stu-id="90e52-143">Photos</span></span>                     | <span data-ttu-id="90e52-144">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="90e52-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="90e52-145">Settings</span></span>                   | <span data-ttu-id="90e52-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="90e52-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="90e52-147">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="90e52-147">Tips</span></span>                       | <span data-ttu-id="90e52-148">Microsoft. HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="90e52-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="90e52-149">Si una aplicación no se encuentra en esta lista, es posible que un usuario Use Device portal, conectado a HoloLens 2 que ha instalado la aplicación que se ha bloqueado, para determinar el PackageRelativeID y desde allí obtener el PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="90e52-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="90e52-150">Instala la aplicación en tu dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="90e52-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="90e52-151">Abra configuración-> actualizaciones & securtiy-> para desarrolladores y habilitar el **modo de desarrollador** y, a continuación, **Device portal**.</span><span class="sxs-lookup"><span data-stu-id="90e52-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="90e52-152">Más instrucciones para obtener más información sobre la [configuración y el uso de Device portal aquí](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="90e52-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="90e52-153">Una vez conectado el portal de dispositivos, vaya a **vistas** y después a **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="90e52-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="90e52-154">En el panel aplicaciones instaladas, use la lista desplegable para seleccionar la aplicación instalada.</span><span class="sxs-lookup"><span data-stu-id="90e52-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="90e52-155">Busque el PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="90e52-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="90e52-156">Copia los caracteres de la aplicación antes de la!, será tu PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="90e52-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

