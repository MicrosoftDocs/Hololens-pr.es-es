---
title: Actualizar HoloLens
description: Consulta el número de compilación, la actualización y la reversión de las actualizaciones de HoloLens.
keywords: procedimientos, actualizar, revertir, HoloLens, comprobar compilación, número de compilación
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828595"
---
# <span data-ttu-id="8bc95-104">Actualizar HoloLens</span><span class="sxs-lookup"><span data-stu-id="8bc95-104">Update HoloLens</span></span>

<span data-ttu-id="8bc95-105">HoloLens usa Windows Update, como otros dispositivos de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8bc95-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="8bc95-106">HoloLens descargará e instalará automáticamente actualizaciones del sistema siempre que se conecten a Internet y se conecten a Internet, incluso cuando esté en modo de suspensión.</span><span class="sxs-lookup"><span data-stu-id="8bc95-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="8bc95-107">Este artículo le guiará a través de las herramientas de HoloLens para:</span><span class="sxs-lookup"><span data-stu-id="8bc95-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="8bc95-108">visualización de la versión del sistema operativo actual (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="8bc95-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="8bc95-109">comprobando actualizaciones</span><span class="sxs-lookup"><span data-stu-id="8bc95-109">checking for updates</span></span>
- <span data-ttu-id="8bc95-110">actualización manual de HoloLens</span><span class="sxs-lookup"><span data-stu-id="8bc95-110">manually updating HoloLens</span></span>
- <span data-ttu-id="8bc95-111">volver a una actualización anterior</span><span class="sxs-lookup"><span data-stu-id="8bc95-111">rolling back to an older update</span></span>

## <span data-ttu-id="8bc95-112">Comprobar la versión del sistema operativo (número de compilación)</span><span class="sxs-lookup"><span data-stu-id="8bc95-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="8bc95-113">Puede comprobar el número de versión del sistema (número de compilación) abriendo la aplicación configuración y seleccionando **sistema**  >  **acerca de**.</span><span class="sxs-lookup"><span data-stu-id="8bc95-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="8bc95-114">Comprobar si hay actualizaciones y actualizar manualmente</span><span class="sxs-lookup"><span data-stu-id="8bc95-114">Check for updates and manually update</span></span>

<span data-ttu-id="8bc95-115">Puede comprobar si hay actualizaciones en cualquier momento en configuración.</span><span class="sxs-lookup"><span data-stu-id="8bc95-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="8bc95-116">Para ver las actualizaciones disponibles y comprobar si hay nuevas actualizaciones:</span><span class="sxs-lookup"><span data-stu-id="8bc95-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="8bc95-117">Abra la aplicación **configuración** .</span><span class="sxs-lookup"><span data-stu-id="8bc95-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="8bc95-118">Vaya a **Actualizar & seguridad**de  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="8bc95-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="8bc95-119">Seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="8bc95-119">Select **Check for updates**.</span></span>

<span data-ttu-id="8bc95-120">Si hay una actualización disponible, empezará a descargar la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="8bc95-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="8bc95-121">Una vez completada la descarga, seleccione el botón **reiniciar ahora** para desencadenar la instalación.</span><span class="sxs-lookup"><span data-stu-id="8bc95-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="8bc95-122">Si tu dispositivo está por debajo del 40% y no conectado, el reinicio no comenzará a instalar la actualización.</span><span class="sxs-lookup"><span data-stu-id="8bc95-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="8bc95-123">Mientras tu HoloLens esté instalando la actualización, mostrará artes de giro y un indicador de progreso.</span><span class="sxs-lookup"><span data-stu-id="8bc95-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="8bc95-124">No apagues tu HoloLens durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="8bc95-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="8bc95-125">Se reiniciará automáticamente una vez completada la instalación.</span><span class="sxs-lookup"><span data-stu-id="8bc95-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="8bc95-126">HoloLens aplica una actualización a la vez.</span><span class="sxs-lookup"><span data-stu-id="8bc95-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="8bc95-127">Si tu HoloLens es más de una versión que se encuentra detrás de lo más reciente, es posible que tengas que ejecutar el proceso de actualización varias veces para que quede completamente actualizado.</span><span class="sxs-lookup"><span data-stu-id="8bc95-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="8bc95-128">Volver a una versión anterior: HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8bc95-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="8bc95-129">En algunos casos, es posible que desee volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8bc95-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="8bc95-130">Puedes hacerlo usando el Asistente de recuperación avanzada para restablecer tu HoloLens a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="8bc95-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc95-131">Al volver a una versión anterior, se eliminan los archivos personales y la configuración.</span><span class="sxs-lookup"><span data-stu-id="8bc95-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="8bc95-132">Para volver a una versión anterior de HoloLens 2, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8bc95-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="8bc95-133">Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado a su PC.</span><span class="sxs-lookup"><span data-stu-id="8bc95-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="8bc95-134">En su equipo, descargue el [complemento de recuperación avanzada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) desde Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="8bc95-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="8bc95-135">Descarga la [versión más reciente de HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="8bc95-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="8bc95-136">Cuando hayas terminado estas descargas, abre descargas del **Explorador de archivos**  >  **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="8bc95-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="8bc95-137">Haz clic con el botón derecho en la carpeta comprimida que acabas de descargar y selecciona **Extraer todo** > **Extraer** para descomprimirlo.</span><span class="sxs-lookup"><span data-stu-id="8bc95-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="8bc95-138">Conecta tu HoloLens a tu PC con un cable USB-a a USB-C.</span><span class="sxs-lookup"><span data-stu-id="8bc95-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="8bc95-139">(Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).</span><span class="sxs-lookup"><span data-stu-id="8bc95-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="8bc95-140">El Asistente de recuperación avanzada detecta automáticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8bc95-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="8bc95-141">Selecciona el icono de **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="8bc95-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="8bc95-142">En la siguiente pantalla, seleccione **selección de paquetes manual** y, a continuación, seleccione el archivo de instalación contenido en la carpeta que descomprime en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="8bc95-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="8bc95-143">(Busque un archivo con la extensión. FFU).</span><span class="sxs-lookup"><span data-stu-id="8bc95-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="8bc95-144">Seleccione **instalar software**y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8bc95-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="8bc95-145">Volver a una versión anterior: HoloLens (1ª generación)</span><span class="sxs-lookup"><span data-stu-id="8bc95-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="8bc95-146">En algunos casos, es posible que desee volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8bc95-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="8bc95-147">Puedes hacerlo usando la herramienta de recuperación de dispositivos de Windows para restablecer tu HoloLens a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="8bc95-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc95-148">Al volver a una versión anterior, se eliminan los archivos personales y la configuración.</span><span class="sxs-lookup"><span data-stu-id="8bc95-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="8bc95-149">Para volver a una versión anterior de HoloLens 1, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8bc95-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="8bc95-150">Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado a su PC.</span><span class="sxs-lookup"><span data-stu-id="8bc95-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="8bc95-151">En su equipo, descargue la [herramienta de recuperación de dispositivos de Windows (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="8bc95-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="8bc95-152">Descarga el [paquete de recuperación](https://aka.ms/hololensrecovery)de la actualización de aniversario de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8bc95-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="8bc95-153">Cuando finalicen las descargas, abra el **Explorador de archivos**  >  **descargas**.</span><span class="sxs-lookup"><span data-stu-id="8bc95-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="8bc95-154">Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **extraer todos los**  >  **extractos** para descomprimirlo.</span><span class="sxs-lookup"><span data-stu-id="8bc95-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="8bc95-155">Conecta tu HoloLens a tu equipo con el cable micro-USB con el que venía.</span><span class="sxs-lookup"><span data-stu-id="8bc95-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="8bc95-156">(Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).</span><span class="sxs-lookup"><span data-stu-id="8bc95-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="8bc95-157">WDRT detectará automáticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8bc95-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="8bc95-158">Selecciona el icono de **Microsoft HoloLens** .</span><span class="sxs-lookup"><span data-stu-id="8bc95-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="8bc95-159">En la siguiente pantalla, seleccione **selección manual de paquetes** y elija el archivo de instalación contenido en la carpeta que descomprime en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="8bc95-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="8bc95-160">(Busque un archivo con la extensión. FFU).</span><span class="sxs-lookup"><span data-stu-id="8bc95-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="8bc95-161">Seleccione **instalar software**y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8bc95-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="8bc95-162">Si el WDRT no detecta HoloLens, intenta reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="8bc95-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="8bc95-163">Si eso no funciona, **no se detectó seleccionar mi dispositivo**, seleccione **Microsoft HoloLens**y, a continuación, siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8bc95-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="8bc95-164">Programa Windows Insider en HoloLens</span><span class="sxs-lookup"><span data-stu-id="8bc95-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="8bc95-165">¿Quieres ver las características más recientes de HoloLens?</span><span class="sxs-lookup"><span data-stu-id="8bc95-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="8bc95-166">Si es así, Únete al programa Windows Insider; Obtendrá acceso a versiones preliminares de las actualizaciones del software HoloLens antes de que estén disponibles para el público en general.</span><span class="sxs-lookup"><span data-stu-id="8bc95-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="8bc95-167">[Obtén Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="8bc95-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
