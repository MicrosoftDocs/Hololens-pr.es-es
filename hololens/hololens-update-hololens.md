---
title: Actualizar HoloLens
description: Aprende a comprobar el número de compilación de HoloLens, mantenerte al día con las actualizaciones del dispositivo, unirte al Programa Insider y revertir las actualizaciones.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283941"
---
# <span data-ttu-id="ff2d4-104">Actualizar HoloLens</span><span class="sxs-lookup"><span data-stu-id="ff2d4-104">Update HoloLens</span></span>

<span data-ttu-id="ff2d4-105">HoloLens usa Windows Update, al igual que otros dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="ff2d4-106">HoloLens descargará e instalará automáticamente las actualizaciones del sistema siempre que esté conectado a la alimentación y conectado a Internet, incluso cuando esté en modo de espera.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="ff2d4-107">En este artículo se mostrarán las herramientas de HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="ff2d4-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="ff2d4-108">visualización de la versión actual del sistema operativo (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="ff2d4-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="ff2d4-109">buscar actualizaciones</span><span class="sxs-lookup"><span data-stu-id="ff2d4-109">checking for updates</span></span>
- <span data-ttu-id="ff2d4-110">actualización manual de HoloLens</span><span class="sxs-lookup"><span data-stu-id="ff2d4-110">manually updating HoloLens</span></span>
- <span data-ttu-id="ff2d4-111">revertir a una actualización anterior</span><span class="sxs-lookup"><span data-stu-id="ff2d4-111">rolling back to an older update</span></span>

## <span data-ttu-id="ff2d4-112">Comprobar la versión del sistema operativo (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="ff2d4-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="ff2d4-113">Puedes comprobar el número de versión del sistema (número de compilación) abriendo la aplicación Configuración y **seleccionando Sistema**  >  **acerca de**.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="ff2d4-114">Buscar actualizaciones y actualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="ff2d4-114">Check for updates and manually update</span></span>

<span data-ttu-id="ff2d4-115">Puede buscar actualizaciones en cualquier momento en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="ff2d4-116">Para ver las actualizaciones disponibles y buscar actualizaciones nuevas:</span><span class="sxs-lookup"><span data-stu-id="ff2d4-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="ff2d4-117">Abre la **aplicación** Configuración.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="ff2d4-118">Vaya a **Actualización & Seguridad de**Windows  >  **Update**.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="ff2d4-119">Seleccione **Buscar actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="ff2d4-119">Select **Check for updates**.</span></span>

<span data-ttu-id="ff2d4-120">Si hay una actualización disponible, empezará a descargar la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="ff2d4-121">Una vez completada la descarga, seleccione el botón Reiniciar **ahora** para desencadenar la instalación.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="ff2d4-122">Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no empezará a instalar la actualización.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="ff2d4-123">Mientras holoLens instala la actualización, mostrará engranajes giratorios y un indicador de progreso.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="ff2d4-124">No desactives HoloLens durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="ff2d4-125">Se reiniciará automáticamente una vez que haya completado la instalación.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="ff2d4-126">HoloLens aplica una actualización cada vez.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="ff2d4-127">Si su HoloLens tiene más de una versión detrás de la versión más reciente, es posible que deba ejecutar el proceso de actualización varias veces para actualizarlo por completo.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="ff2d4-128">Volver a una versión anterior - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ff2d4-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="ff2d4-129">En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="ff2d4-130">Para ello, usa Advanced Recovery Companion para restablecer HoloLens a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="ff2d4-131">Al volver a una versión anterior, se eliminan los archivos y la configuración personales.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="ff2d4-132">Para volver a una versión anterior de HoloLens 2, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ff2d4-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="ff2d4-133">Asegúrate de que no tienes ningún teléfono o dispositivo Windows conectado a tu equipo.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="ff2d4-134">En el equipo, descarga [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) desde Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="ff2d4-135">Descarga la [versión más reciente de HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="ff2d4-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="ff2d4-136">Cuando haya terminado estas descargas, abra **Descargas del explorador de**  >  **archivos.**</span><span class="sxs-lookup"><span data-stu-id="ff2d4-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="ff2d4-137">Haz clic con el botón derecho en la carpeta comprimida que acabas de descargar y selecciona **Extraer todo** > **Extraer** para descomprimirlo.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="ff2d4-138">Conecta HoloLens a tu PC mediante un cable USB-A a USB-C.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="ff2d4-139">(Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).</span><span class="sxs-lookup"><span data-stu-id="ff2d4-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="ff2d4-140">El Advanced Recovery Companion detecta automáticamente su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="ff2d4-141">Seleccione el icono de **Microsoft HoloLens**</span><span class="sxs-lookup"><span data-stu-id="ff2d4-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="ff2d4-142">En la siguiente pantalla, **seleccione** La selección manual del paquete y, a continuación, seleccione el archivo de instalación incluido en la carpeta que descomprimió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="ff2d4-143">(Busque un archivo con la extensión .ffu).</span><span class="sxs-lookup"><span data-stu-id="ff2d4-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="ff2d4-144">Seleccione **Instalar software**y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="ff2d4-145">Volver a una versión anterior- HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="ff2d4-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="ff2d4-146">En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="ff2d4-147">Para ello, usa la Herramienta de recuperación de dispositivos windows para restablecer HoloLens a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="ff2d4-148">Al volver a una versión anterior, se eliminan los archivos y la configuración personales.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="ff2d4-149">Para volver a una versión anterior de HoloLens 1, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ff2d4-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="ff2d4-150">Asegúrate de que no tienes ningún teléfono o dispositivo Windows conectado a tu equipo.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="ff2d4-151">En el equipo, descarga la Herramienta [de recuperación de dispositivos windows (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="ff2d4-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="ff2d4-152">Descargue el [Paquete de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="ff2d4-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="ff2d4-153">Cuando finalicen las descargas, abra **Descargas del explorador de**  >  **archivos.**</span><span class="sxs-lookup"><span data-stu-id="ff2d4-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="ff2d4-154">Haga clic con el botón secundario en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="ff2d4-155">Conecta tu HoloLens a tu PC con el cable micro USB que viene.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="ff2d4-156">(Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).</span><span class="sxs-lookup"><span data-stu-id="ff2d4-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="ff2d4-157">WdRT detectará automáticamente tu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="ff2d4-158">Seleccione el icono de **Microsoft HoloLens**</span><span class="sxs-lookup"><span data-stu-id="ff2d4-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="ff2d4-159">En la siguiente pantalla, seleccione **Selección manual** del paquete y elija el archivo de instalación incluido en la carpeta que descomprimió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="ff2d4-160">(Busque un archivo con la extensión .ffu).</span><span class="sxs-lookup"><span data-stu-id="ff2d4-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="ff2d4-161">Seleccione **Instalar software**y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="ff2d4-162">Si WDRT no detecta holoLens, intenta reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="ff2d4-163">Si esto no funciona, seleccione **No se ha detectado Mi dispositivo**, **Microsoft HoloLens** y, a continuación, siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="ff2d4-164">Programa Windows Insider en HoloLens</span><span class="sxs-lookup"><span data-stu-id="ff2d4-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="ff2d4-165">¿Quieres ver las últimas características de HoloLens?</span><span class="sxs-lookup"><span data-stu-id="ff2d4-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="ff2d4-166">Si es así, únete al Programa Windows Insider; tendrá acceso a las versiones preliminares de las actualizaciones de software de HoloLens antes de que estén disponibles para el público en general.</span><span class="sxs-lookup"><span data-stu-id="ff2d4-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="ff2d4-167">[Obtener la vista previa de Windows Insider para Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="ff2d4-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
