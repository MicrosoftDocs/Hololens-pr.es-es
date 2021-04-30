---
title: Actualización de HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310166"
---
# <a name="update-hololens"></a><span data-ttu-id="d9f46-104">Actualización de HoloLens</span><span class="sxs-lookup"><span data-stu-id="d9f46-104">Update HoloLens</span></span>

<span data-ttu-id="d9f46-105">HoloLens usa Windows Update, al igual que otros Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d9f46-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="d9f46-106">HoloLens descargará e instalará automáticamente las actualizaciones del sistema cada vez que esté conectado a la alimentación y conectado a Internet, incluso cuando esté en espera.</span><span class="sxs-lookup"><span data-stu-id="d9f46-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="d9f46-107">En este artículo se leen las herramientas de HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="d9f46-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="d9f46-108">ver la versión actual del sistema operativo (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="d9f46-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="d9f46-109">comprobar si hay actualizaciones</span><span class="sxs-lookup"><span data-stu-id="d9f46-109">checking for updates</span></span>
- <span data-ttu-id="d9f46-110">actualización manual de HoloLens</span><span class="sxs-lookup"><span data-stu-id="d9f46-110">manually updating HoloLens</span></span>
- <span data-ttu-id="d9f46-111">revertir a una actualización anterior</span><span class="sxs-lookup"><span data-stu-id="d9f46-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="d9f46-112">Comprobación de la versión del sistema operativo (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="d9f46-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="d9f46-113">Puede comprobar el número de versión del sistema (número de compilación) abriendo la aplicación Configuración y **seleccionando Sistema**  >  **acerca de**.</span><span class="sxs-lookup"><span data-stu-id="d9f46-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="d9f46-114">Buscar actualizaciones y actualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="d9f46-114">Check for updates and manually update</span></span>

<span data-ttu-id="d9f46-115">Puede buscar actualizaciones en cualquier momento en la configuración.</span><span class="sxs-lookup"><span data-stu-id="d9f46-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="d9f46-116">Para ver las actualizaciones disponibles y comprobar si hay nuevas actualizaciones:</span><span class="sxs-lookup"><span data-stu-id="d9f46-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="d9f46-117">Abra la aplicación **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="d9f46-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="d9f46-118">Vaya a **Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="d9f46-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="d9f46-119">Haga clic en **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="d9f46-119">Select **Check for updates**.</span></span>

<span data-ttu-id="d9f46-120">Si hay una actualización disponible, empezará a descargar la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="d9f46-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="d9f46-121">Una vez completada la descarga, seleccione el **botón Reiniciar** ahora para desencadenar la instalación.</span><span class="sxs-lookup"><span data-stu-id="d9f46-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="d9f46-122">Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no iniciará la instalación de la actualización.</span><span class="sxs-lookup"><span data-stu-id="d9f46-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="d9f46-123">Mientras HoloLens instala la actualización, mostrará engranajes giratorios y un indicador de progreso.</span><span class="sxs-lookup"><span data-stu-id="d9f46-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="d9f46-124">No apague HoloLens durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="d9f46-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="d9f46-125">Se reiniciará automáticamente una vez que haya completado la instalación.</span><span class="sxs-lookup"><span data-stu-id="d9f46-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="d9f46-126">HoloLens aplica una actualización a la vez.</span><span class="sxs-lookup"><span data-stu-id="d9f46-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="d9f46-127">Si HoloLens tiene más de una versión detrás de la versión más reciente, es posible que deba ejecutar el proceso de actualización varias veces para actualizarlo por completo.</span><span class="sxs-lookup"><span data-stu-id="d9f46-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="d9f46-128">Vuelva a una versión anterior: HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d9f46-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="d9f46-129">En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d9f46-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="d9f46-130">Para ello, use advanced recovery companion (Complemento de recuperación avanzada) para restablecer HoloLens a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="d9f46-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="d9f46-131">Al volver a una versión anterior, se eliminan los archivos personales y la configuración.</span><span class="sxs-lookup"><span data-stu-id="d9f46-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="d9f46-132">Para volver a una versión anterior de HoloLens 2, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d9f46-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="d9f46-133">Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado al equipo.</span><span class="sxs-lookup"><span data-stu-id="d9f46-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="d9f46-134">En el equipo, descargue el [complemento de recuperación](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) avanzada desde el Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d9f46-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="d9f46-135">Descargue la [versión de HoloLens 2 más reciente.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="d9f46-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="d9f46-136">Cuando haya terminado estas descargas, abra el Explorador **de archivos**  >  **Descargas**.</span><span class="sxs-lookup"><span data-stu-id="d9f46-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="d9f46-137">Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.</span><span class="sxs-lookup"><span data-stu-id="d9f46-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="d9f46-138">Conecte HoloLens al equipo mediante un cable USB-A a USB-C.</span><span class="sxs-lookup"><span data-stu-id="d9f46-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="d9f46-139">(Incluso si ha estado usando otros cables para conectar holoLens, este funciona mejor).</span><span class="sxs-lookup"><span data-stu-id="d9f46-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="d9f46-140">Advanced Recovery Companion detecta automáticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d9f46-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="d9f46-141">Seleccione el **icono Microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="d9f46-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="d9f46-142">En la siguiente pantalla, seleccione **Selección** manual del paquete y, a continuación, seleccione el archivo de instalación contenido en la carpeta que descomprimió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="d9f46-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="d9f46-143">(Busque un archivo con la extensión .ffu).</span><span class="sxs-lookup"><span data-stu-id="d9f46-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="d9f46-144">Seleccione **Instalar software** y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d9f46-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="d9f46-145">Volver a una versión anterior: HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="d9f46-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="d9f46-146">En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d9f46-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="d9f46-147">Para ello, use la Herramienta de recuperación de dispositivos Windows para restablecer HoloLens a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="d9f46-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="d9f46-148">Al volver a una versión anterior, se eliminan los archivos y la configuración personales.</span><span class="sxs-lookup"><span data-stu-id="d9f46-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="d9f46-149">Para volver a una versión anterior de HoloLens 1, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d9f46-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="d9f46-150">Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado al equipo.</span><span class="sxs-lookup"><span data-stu-id="d9f46-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="d9f46-151">En el equipo, descargue la Herramienta [de recuperación de dispositivos Windows (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="d9f46-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="d9f46-152">Descargue el paquete [de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="d9f46-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="d9f46-153">Cuando finalicen las descargas, abra El **Explorador de archivos**  >  **descarga**.</span><span class="sxs-lookup"><span data-stu-id="d9f46-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="d9f46-154">Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer toda**  >  **la extracción** para descomprimirla.</span><span class="sxs-lookup"><span data-stu-id="d9f46-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="d9f46-155">Conecte holoLens al equipo mediante el cable micro USB con el que se incluye.</span><span class="sxs-lookup"><span data-stu-id="d9f46-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="d9f46-156">(Aunque haya estado usando otros cables para conectar HoloLens, este funciona mejor).</span><span class="sxs-lookup"><span data-stu-id="d9f46-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="d9f46-157">WDRT detectará automáticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d9f46-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="d9f46-158">Seleccione el **icono Microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="d9f46-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="d9f46-159">En la siguiente pantalla, seleccione **Selección manual** de paquetes y elija el archivo de instalación incluido en la carpeta que descomprimió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="d9f46-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="d9f46-160">(Busque un archivo con la extensión .ffu).</span><span class="sxs-lookup"><span data-stu-id="d9f46-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="d9f46-161">Seleccione **Instalar software** y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d9f46-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d9f46-162">Si WDRT no detecta HoloLens, intente reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="d9f46-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="d9f46-163">Si eso no funciona, seleccione Mi dispositivo no se detectó, **seleccione** Microsoft HoloLens y, a continuación, siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d9f46-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="d9f46-164">Programa Windows Insider en HoloLens</span><span class="sxs-lookup"><span data-stu-id="d9f46-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="d9f46-165">¿Quiere ver las características más recientes de HoloLens?</span><span class="sxs-lookup"><span data-stu-id="d9f46-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="d9f46-166">Si es así, una el Programa Windows Insider; Tendrá acceso a las compilaciones de versión preliminar de las actualizaciones de software de HoloLens antes de que estén disponibles para el público general.</span><span class="sxs-lookup"><span data-stu-id="d9f46-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="d9f46-167">[Obtenga Windows Insider versión preliminar de Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="d9f46-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
