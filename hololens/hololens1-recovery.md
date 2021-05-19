---
title: Reinicie, restablezca o recupere el HoloLens 1
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Cómo usar Windows Device Recovery Tool para flashear una imagen a HoloLens 1 era generación.
keywords: procedimientos para, reiniciar, resetear, recuperar, restablecimiento completo, restablecimiento parcial, ciclo de energía, HoloLens, apagar, wdrt, Windows Device Recovery Tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915966"
---
# <span data-ttu-id="9cb35-104">Reiniciar, restablecer o recuperar HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="9cb35-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="9cb35-105">Si tiene problemas con su HoloLens, puede probar a reiniciar, restablecer o incluso volver a flashearlo con el modo de recuperación del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="9cb35-106">Este artículo le guiará por los pasos de recuperación recomendados.</span><span class="sxs-lookup"><span data-stu-id="9cb35-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="9cb35-107">Si desea recuperar un HoloLens 2, consulte [Recuperar un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), ya que el proceso es distinto.</span><span class="sxs-lookup"><span data-stu-id="9cb35-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="9cb35-108">Este artículo se centra en el dispositivo y el software de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9cb35-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="9cb35-109">Si el holograma no se muestra correctamente, vea **[Consideraciones de entorno de HoloLens](hololens-environment-considerations.md)** para obtener información sobre los factores que mejoran la calidad del holograma.</span><span class="sxs-lookup"><span data-stu-id="9cb35-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <span data-ttu-id="9cb35-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="9cb35-110">Restart</span></span>

### <span data-ttu-id="9cb35-111">Reinicie de manera segura con Cortana</span><span class="sxs-lookup"><span data-stu-id="9cb35-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="9cb35-112">El modo más seguro de reiniciar HoloLens es usando Cortana y, por lo general, es lo primero que puede probar a hacer cuando tenga un problema con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9cb35-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="9cb35-113">Cortana no está disponible para todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9cb35-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="9cb35-114">Cortana está disponible para todos los dispositivos HoloLens (1 era generación).</span><span class="sxs-lookup"><span data-stu-id="9cb35-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="9cb35-115">Cortana está disponible en los dispositivos HoloLens 2 en una versión anterior a la actualización de Windows Holograpic, versión 2004.</span><span class="sxs-lookup"><span data-stu-id="9cb35-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="9cb35-116">Active su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9cb35-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="9cb35-117">Asegúrese de que un usuario haya iniciado sesión y que el dispositivo no esté esperando una contraseña para desbloquearlo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="9cb35-118">Diga "Hey Cortana, reinicio" o "Hey Cortana, reiniciar".</span><span class="sxs-lookup"><span data-stu-id="9cb35-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="9cb35-119">Cortana responderá y le pedirá confirmación.</span><span class="sxs-lookup"><span data-stu-id="9cb35-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="9cb35-120">Espere a que se reproduzca un sonido después de la pregunta y, entonces, diga "sí".</span><span class="sxs-lookup"><span data-stu-id="9cb35-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="9cb35-121">El dispositivo se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="9cb35-121">The device will restart.</span></span>

### <span data-ttu-id="9cb35-122">Usar el botón de encendido para reiniciar de manera segura</span><span class="sxs-lookup"><span data-stu-id="9cb35-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="9cb35-123">Si aún así no puede reiniciar el dispositivo, inténtelo con el botón **de encendido**:</span><span class="sxs-lookup"><span data-stu-id="9cb35-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="9cb35-124">Mantenga pulsado el botón **de encendido** durante 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="9cb35-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="9cb35-125">Al cabo de 1 segundo se iluminarán los cinco LED y, a continuación, se apagarán lentamente de uno en uno y de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="9cb35-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="9cb35-126">Al cabo de 5 segundos, todos los LED estarán apagados, lo que indica que el dispositivo se ha apagado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9cb35-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="9cb35-127">Deje de pulsar el botón inmediatamente después de que todos los LED se hayan apagado.</span><span class="sxs-lookup"><span data-stu-id="9cb35-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="9cb35-128">Espere 1 minuto hasta que se apague por completo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="9cb35-129">El apagado puede estar en curso incluso después de que se apaguen las pantallas.</span><span class="sxs-lookup"><span data-stu-id="9cb35-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="9cb35-130">Encienda el dispositivo de nuevo manteniendo pulsado el botón **de encendido** durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <span data-ttu-id="9cb35-131">Reinicie de manera segura con el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="9cb35-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="9cb35-132">Para este proceso, se tiene que configurar el HoloLens como un dispositivo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="9cb35-133">Obtenga más información en el [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="9cb35-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="9cb35-134">Si no funcionó el procedimiento anterior, puede intentar reiniciar el dispositivo mediante el[Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="9cb35-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="9cb35-135">En la esquina superior derecha, encontrará la opción para reiniciar o apagar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <span data-ttu-id="9cb35-136">Reiniciar de manera forzosa y no segura</span><span class="sxs-lookup"><span data-stu-id="9cb35-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="9cb35-137">Si los métodos anteriores no reiniciaron su HoloLens, fuerce un reinicio.</span><span class="sxs-lookup"><span data-stu-id="9cb35-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="9cb35-138">Este método equivale a quitar y volver a instalar la batería.</span><span class="sxs-lookup"><span data-stu-id="9cb35-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="9cb35-139">Es peligroso porque podría dañar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="9cb35-140">Si eso sucede, tendrá que flashear su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9cb35-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="9cb35-141">Se trata de un método potencialmente nocivo y únicamente se debe utilizar en el caso de que ninguno de los métodos anteriores funcione.</span><span class="sxs-lookup"><span data-stu-id="9cb35-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="9cb35-142">Mantenga presionado el botón **de encendido** por lo menos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="9cb35-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="9cb35-143">Está bien mantener el botón durante más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="9cb35-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="9cb35-144">Es seguro ignorar cualquier actividad de los LED.</span><span class="sxs-lookup"><span data-stu-id="9cb35-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="9cb35-145">Suelte el botón y espere de 2 a 3 segundos.</span><span class="sxs-lookup"><span data-stu-id="9cb35-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="9cb35-146">Mantenga pulsado el botón **de encendido** durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="9cb35-147">Si sigue teniendo problemas, pulse el botón **de encendido** durante 4 segundos, hasta que todos los indicadores de la batería se atenúen y la pantalla deje de mostrar hologramas.</span><span class="sxs-lookup"><span data-stu-id="9cb35-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="9cb35-148">Espere 1 minuto, luego presione de nuevo el botón **de encendido** para encender el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <span data-ttu-id="9cb35-149">Restaurar la configuración de fábrica</span><span class="sxs-lookup"><span data-stu-id="9cb35-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="9cb35-150">La batería necesita al menos un 40 % de carga para reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="9cb35-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="9cb35-151">Si HoloLens sigue teniendo algún problema, pruebe a restablecerlo en estado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="9cb35-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="9cb35-152">Este paso mantiene la versión del software holográfico de Windows que lleva instalado y reinicia todo lo demás a la configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="9cb35-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="9cb35-153">Si restablece el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM.</span><span class="sxs-lookup"><span data-stu-id="9cb35-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="9cb35-154">Si restablece, se instalará únicamente la versión más reciente del software holográfico de Windows.</span><span class="sxs-lookup"><span data-stu-id="9cb35-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="9cb35-155">Tendrá que rehacer todos los pasos de inicialización (calibrar, conectarse a una red Wi-Fi, crear una cuenta de usuario, descargar aplicaciones, etc.).</span><span class="sxs-lookup"><span data-stu-id="9cb35-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="9cb35-156">Abra la aplicación Ajustes y, a continuación, seleccione **Actualizar** > **Recuperación**.</span><span class="sxs-lookup"><span data-stu-id="9cb35-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="9cb35-157">Seleccione la opción**Reiniciar el dispositivo**y lea el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="9cb35-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="9cb35-158">Confirme el restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="9cb35-158">Confirm the reset.</span></span> <span data-ttu-id="9cb35-159">El dispositivo se reiniciará y mostrará un conjunto de engranajes giratorios y una barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="9cb35-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="9cb35-160">Espere unos 30 minutos para que este proceso se complete.</span><span class="sxs-lookup"><span data-stu-id="9cb35-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="9cb35-161">Cuando haya acabado, el dispositivo se reiniciará en la experiencia «listo para usar».</span><span class="sxs-lookup"><span data-stu-id="9cb35-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <span data-ttu-id="9cb35-162">Reinstalar el sistema operativo</span><span class="sxs-lookup"><span data-stu-id="9cb35-162">Reinstall the operating system</span></span>

<span data-ttu-id="9cb35-163">Si el dispositivo sigue teniendo algún problema después de reiniciar y restaurar, puede utilizar una herramienta de recuperación en su ordenador para reinstalar el sistema operativo y el firmware del HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9cb35-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="9cb35-164">Los datos que HoloLens necesita para el restablecimiento se empaquetan en formato Full Flash Update (FFU), que es similar a un archivo ISO, WIM o VHD.</span><span class="sxs-lookup"><span data-stu-id="9cb35-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="9cb35-165">Aprenda sobre los formatos de archivos de imagen FFU.</span><span class="sxs-lookup"><span data-stu-id="9cb35-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="9cb35-166">Puede instalar un sistema operativo nuevo en su HoloLens (1 era generación) con la herramienta de migración para recuperación de copias de seguridad (Windows Device Recovery Tool).</span><span class="sxs-lookup"><span data-stu-id="9cb35-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="9cb35-167">Antes de usar esta herramienta, determine si reiniciando o restableciendo su HoloLens se soluciona el problema.</span><span class="sxs-lookup"><span data-stu-id="9cb35-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="9cb35-168">El proceso de recuperación puede tardar un poco.</span><span class="sxs-lookup"><span data-stu-id="9cb35-168">The recovery process may take a while.</span></span> <span data-ttu-id="9cb35-169">Cuando termine, se instalará la última versión del software holográfico de Windows.</span><span class="sxs-lookup"><span data-stu-id="9cb35-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="9cb35-170">Para usar la herramienta, necesita un ordenador con Windows 10, o posterior, con al menos 4 GB de espacio de almacenamiento libre.</span><span class="sxs-lookup"><span data-stu-id="9cb35-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="9cb35-171">No puede ejecutar esta herramienta en una máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="9cb35-171">You can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="9cb35-172">Recuperar el HoloLens</span><span class="sxs-lookup"><span data-stu-id="9cb35-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="9cb35-173">Descargue e instale [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) en su ordenador.</span><span class="sxs-lookup"><span data-stu-id="9cb35-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="9cb35-174">Utilice el cable Micro USB que viene con HoloLens (1 era generación) para conectarlo a su ordenador.</span><span class="sxs-lookup"><span data-stu-id="9cb35-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="9cb35-175">Abra Windows Device Recovery Tool y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9cb35-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="9cb35-176">Si no se detecta automáticamente el HoloLens (1 era generación), seleccione **Mi dispositivo no fue detectado**.</span><span class="sxs-lookup"><span data-stu-id="9cb35-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="9cb35-177">Después, siga las instrucciones para poner el dispositivo en modo de recuperación.</span><span class="sxs-lookup"><span data-stu-id="9cb35-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <span data-ttu-id="9cb35-178">Modo flasheo manual</span><span class="sxs-lookup"><span data-stu-id="9cb35-178">Manual flashing mode</span></span>

<span data-ttu-id="9cb35-179">Si no se detecta el dispositivo, siga estos pasos para ponerlo manualmente en modo flasheo:</span><span class="sxs-lookup"><span data-stu-id="9cb35-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="9cb35-180">Desconecte el dispositivo de cualquier fuente de energía.</span><span class="sxs-lookup"><span data-stu-id="9cb35-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="9cb35-181">Si el dispositivo está encendido, mantenga pulsado el botón **de encendido** hasta que se apague por completo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="9cb35-182">Mantenga presionado el botón de **subir volumen** y pulse el botón **de encendido**.</span><span class="sxs-lookup"><span data-stu-id="9cb35-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="9cb35-183">El dispositivo debería iniciarse y mostrar solo la luz LED del medio.</span><span class="sxs-lookup"><span data-stu-id="9cb35-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="9cb35-184">Enchufe el dispositivo en su PC.</span><span class="sxs-lookup"><span data-stu-id="9cb35-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="9cb35-185">Abra Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="9cb35-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="9cb35-186">Seleccione **Mi dispositivo no fue detectado** y, a continuación, **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="9cb35-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="9cb35-187">Siga las instrucciones para recuperar su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cb35-187">Follow the instructions to recover your device.</span></span>
