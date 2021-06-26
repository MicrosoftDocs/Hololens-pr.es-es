---
title: Actualizar HoloLens 2
description: Obtenga información sobre cómo comprobar el número de compilación de HoloLens, mantenerse al día con las actualizaciones del dispositivo, unirse al programa Insiders y revertir las actualizaciones.
keywords: cómo, actualizar, revertir, HoloLens, comprobar compilación, número de compilación
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924118"
---
# <a name="update-hololens-2"></a><span data-ttu-id="6d55e-104">Actualizar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6d55e-104">Update HoloLens 2</span></span>

<span data-ttu-id="6d55e-105">HoloLens usa Windows Update, al igual que otros Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6d55e-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="6d55e-106">HoloLens descargará e instalará automáticamente las actualizaciones del sistema cada vez que esté conectado a la alimentación y conectado a Internet, incluso cuando esté en espera.</span><span class="sxs-lookup"><span data-stu-id="6d55e-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="6d55e-107">En este artículo se leen las herramientas de HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="6d55e-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="6d55e-108">ver la versión actual del sistema operativo (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="6d55e-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="6d55e-109">comprobar si hay actualizaciones</span><span class="sxs-lookup"><span data-stu-id="6d55e-109">checking for updates</span></span>
- <span data-ttu-id="6d55e-110">actualización manual de HoloLens</span><span class="sxs-lookup"><span data-stu-id="6d55e-110">manually updating HoloLens</span></span>
- <span data-ttu-id="6d55e-111">revertir a una actualización anterior</span><span class="sxs-lookup"><span data-stu-id="6d55e-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="6d55e-112">Comprobación de la versión del sistema operativo (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="6d55e-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="6d55e-113">Puede comprobar el número de versión del sistema (número de compilación) abriendo la aplicación Configuración y **seleccionando Sistema**  >  **acerca de**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="6d55e-114">Buscar actualizaciones y actualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="6d55e-114">Check for updates and manually update</span></span>

<span data-ttu-id="6d55e-115">Puede buscar actualizaciones en cualquier momento en la configuración.</span><span class="sxs-lookup"><span data-stu-id="6d55e-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="6d55e-116">Para ver las actualizaciones disponibles y buscar nuevas actualizaciones:</span><span class="sxs-lookup"><span data-stu-id="6d55e-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="6d55e-117">Abra la aplicación **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="6d55e-118">Vaya **a Actualizar & seguridad**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="6d55e-119">Haga clic en **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-119">Select **Check for updates**.</span></span>

<span data-ttu-id="6d55e-120">Si hay una actualización disponible, comenzará a descargar la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="6d55e-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="6d55e-121">Una vez completada la descarga, seleccione el **botón Reiniciar** ahora para desencadenar la instalación.</span><span class="sxs-lookup"><span data-stu-id="6d55e-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="6d55e-122">Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no iniciará la instalación de la actualización.</span><span class="sxs-lookup"><span data-stu-id="6d55e-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="6d55e-123">Mientras HoloLens instala la actualización, mostrará engranajes giratorios y un indicador de progreso.</span><span class="sxs-lookup"><span data-stu-id="6d55e-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="6d55e-124">No apague HoloLens durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="6d55e-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="6d55e-125">Se reiniciará automáticamente una vez que haya completado la instalación.</span><span class="sxs-lookup"><span data-stu-id="6d55e-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="6d55e-126">HoloLens aplica una actualización a la vez.</span><span class="sxs-lookup"><span data-stu-id="6d55e-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="6d55e-127">Si HoloLens tiene más de una versión detrás de la versión más reciente, es posible que deba ejecutar el proceso de actualización varias veces para actualizarlo por completo.</span><span class="sxs-lookup"><span data-stu-id="6d55e-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="6d55e-128">Volver a una versión anterior</span><span class="sxs-lookup"><span data-stu-id="6d55e-128">Go back to a previous version</span></span>

<span data-ttu-id="6d55e-129">En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6d55e-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6d55e-130">Los pasos recomendados son:</span><span class="sxs-lookup"><span data-stu-id="6d55e-130">The recommended steps are:</span></span>

1. <span data-ttu-id="6d55e-131">Póngase en contacto con el soporte técnico para ver si puede corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="6d55e-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="6d55e-132">Asegúrese de **que la** **telemetría** opcional o completa está habilitada, lo que hace que el error sea más fácil de diagnosticar para los ingenieros.</span><span class="sxs-lookup"><span data-stu-id="6d55e-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="6d55e-133">[Los comentarios de archivo](hololens-feedback.md) son tan descriptivos como sea posible.</span><span class="sxs-lookup"><span data-stu-id="6d55e-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="6d55e-134">Tome nota del título o use la característica de uso compartido para poder compartir el error con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="6d55e-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="6d55e-135">Póngase en [contacto con el soporte técnico.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="6d55e-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="6d55e-136">Si el problema es uno que debe resolverse volviendo a una versión anterior, pueden proporcionar la FFU para que el dispositivo se flashee.</span><span class="sxs-lookup"><span data-stu-id="6d55e-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="6d55e-137">Si esto no funciona, restablezca o vuelva a actualizar el [HoloLens 2 con el complemento de recuperación avanzada](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="6d55e-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="6d55e-138">En el equipo, descargue advanced [recovery companion (Complemento de](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) recuperación avanzada) desde Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="6d55e-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="6d55e-139">Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado al equipo.</span><span class="sxs-lookup"><span data-stu-id="6d55e-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="6d55e-140">Elija la versión a la que desea flash:</span><span class="sxs-lookup"><span data-stu-id="6d55e-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="6d55e-141">Puede descargar la [versión de HoloLens 2 más reciente.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="6d55e-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="6d55e-142">Puede usar la compilación predeterminada que hospeda ARC.</span><span class="sxs-lookup"><span data-stu-id="6d55e-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="6d55e-143">(Si elige esta opción, omita el paso siguiente).</span><span class="sxs-lookup"><span data-stu-id="6d55e-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="6d55e-144">Puede usar una compatibilidad de compilación proporcionada con .</span><span class="sxs-lookup"><span data-stu-id="6d55e-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="6d55e-145">Cuando haya terminado estas descargas, abra **Explorador de archivos**  >  **descargas.**</span><span class="sxs-lookup"><span data-stu-id="6d55e-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="6d55e-146">Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.</span><span class="sxs-lookup"><span data-stu-id="6d55e-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="6d55e-147">Conecte HoloLens al equipo mediante un cable USB-A a USB-C.</span><span class="sxs-lookup"><span data-stu-id="6d55e-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="6d55e-148">(Incluso si ha estado usando otros cables para conectar holoLens, este funciona mejor).</span><span class="sxs-lookup"><span data-stu-id="6d55e-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="6d55e-149">Advanced Recovery Companion detecta automáticamente holoLens.</span><span class="sxs-lookup"><span data-stu-id="6d55e-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="6d55e-150">Seleccione el **icono Microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="6d55e-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="6d55e-151">En la siguiente pantalla, seleccione **Selección** manual del paquete y, a continuación, seleccione el archivo de instalación contenido en la carpeta que descomprimió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="6d55e-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="6d55e-152">(Busque un archivo con la extensión .ffu).</span><span class="sxs-lookup"><span data-stu-id="6d55e-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="6d55e-153">Seleccione **Instalar software** y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6d55e-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="6d55e-154">Al volver a una versión anterior, se eliminan los archivos personales y la configuración.</span><span class="sxs-lookup"><span data-stu-id="6d55e-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6d55e-155">Además, si desea permanecer en la versión instalada actualmente, también puede pausar manualmente [las actualizaciones](hololens-updates.md#pause-updates-via-device).</span><span class="sxs-lookup"><span data-stu-id="6d55e-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="6d55e-156">Esto dará tiempo al equipo de ingeniería para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="6d55e-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="6d55e-157">Programa Windows Insider en HoloLens</span><span class="sxs-lookup"><span data-stu-id="6d55e-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="6d55e-158">¿Quiere ver las características más recientes de HoloLens?</span><span class="sxs-lookup"><span data-stu-id="6d55e-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="6d55e-159">Si es así, una el Programa Windows Insider; Tendrá acceso a las compilaciones de versión preliminar de las actualizaciones de software de HoloLens antes de que estén disponibles para el público general.</span><span class="sxs-lookup"><span data-stu-id="6d55e-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="6d55e-160">[Obtenga Windows Insider vista previa de Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="6d55e-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
