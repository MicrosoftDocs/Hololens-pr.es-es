---
title: Reinicio, restablecimiento o recuperación de HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Cómo usar la herramienta de recuperación de dispositivos Windows para flashear una imagen en HoloLens 1.ª generación.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923523"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="97ec0-104">Reinicio, restablecimiento o recuperación de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="97ec0-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="97ec0-105">Si tiene problemas con HoloLens, puede que quiera probar un reinicio o un restablecimiento, o incluso volver a actualizar el dispositivo mediante la recuperación de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="97ec0-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="97ec0-106">Este artículo le guía por los pasos de recuperación recomendados en orden.</span><span class="sxs-lookup"><span data-stu-id="97ec0-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="97ec0-107">Si desea recuperar un HoloLens 2, consulte [Recuperación](hololens-recovery.md)de un HoloLens 2 , ya que ese proceso difiere.</span><span class="sxs-lookup"><span data-stu-id="97ec0-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="97ec0-108">Este artículo se centra en el dispositivo y el software de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="97ec0-109">Si los hologramas no son **[correctos,](hololens-environment-considerations.md)** consulte Consideraciones del entorno de HoloLens para obtener información sobre los factores que mejoran la calidad del holograma.</span><span class="sxs-lookup"><span data-stu-id="97ec0-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="97ec0-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="97ec0-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="97ec0-111">Realizar un reinicio seguro mediante Cortana</span><span class="sxs-lookup"><span data-stu-id="97ec0-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="97ec0-112">La manera más segura de reiniciar HoloLens es mediante Cortana, que suele ser lo primero que hay que probar cuando se experimenta un problema con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="97ec0-113">Cortana no está disponible en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="97ec0-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="97ec0-114">Cortana está disponible en todos los dispositivos HoloLens (1.ª generación).</span><span class="sxs-lookup"><span data-stu-id="97ec0-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="97ec0-115">Cortana está disponible en HoloLens 2 en compilaciones anteriores a la actualización de Windows Holograpic, versión 2004.</span><span class="sxs-lookup"><span data-stu-id="97ec0-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="97ec0-116">Active HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="97ec0-117">Asegúrese de que un usuario ha iniciado sesión y que el dispositivo no espera a que una contraseña la desbloquee.</span><span class="sxs-lookup"><span data-stu-id="97ec0-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="97ec0-118">Diga "Hola Cortana, reinicie" o "Hola Cortana, reinicie".</span><span class="sxs-lookup"><span data-stu-id="97ec0-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="97ec0-119">Cortana responderá y le pedirá que lo confirme.</span><span class="sxs-lookup"><span data-stu-id="97ec0-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="97ec0-120">Espere a que se reprodgue un sonido después de la pregunta y, a continuación, diga "Sí".</span><span class="sxs-lookup"><span data-stu-id="97ec0-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="97ec0-121">El dispositivo se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="97ec0-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="97ec0-122">Uso del botón de encendido para realizar un reinicio seguro</span><span class="sxs-lookup"><span data-stu-id="97ec0-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="97ec0-123">Si todavía no puede reiniciar el dispositivo, intente reiniciarlo con el **botón de** encendido:</span><span class="sxs-lookup"><span data-stu-id="97ec0-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="97ec0-124">Mantenga presionado el **botón de** encendido durante 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="97ec0-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="97ec0-125">Después de 1 segundo, los cinco LED se encienden y, a continuación, se apagan lentamente uno a uno de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="97ec0-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="97ec0-126">Después de 5 segundos, todos los LED estarán desactivados, lo que indica un apagado correcto.</span><span class="sxs-lookup"><span data-stu-id="97ec0-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="97ec0-127">Deje de presionar el botón inmediatamente después de que todos los LED se han desactivado.</span><span class="sxs-lookup"><span data-stu-id="97ec0-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="97ec0-128">Espere 1 minuto para que se complete el apagado.</span><span class="sxs-lookup"><span data-stu-id="97ec0-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="97ec0-129">El apagado todavía puede estar en curso incluso después de que las pantallas estén desactivadas.</span><span class="sxs-lookup"><span data-stu-id="97ec0-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="97ec0-130">Vuelva a encender el dispositivo presionando y manteniendo presionado el **botón de** encendido durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="97ec0-131">Realice un reinicio seguro mediante Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="97ec0-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="97ec0-132">Para este proceso, HoloLens debe configurarse como un dispositivo para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="97ec0-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="97ec0-133">Obtenga más información en [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="97ec0-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="97ec0-134">Si el procedimiento anterior no funcionaba, intente reiniciar el dispositivo mediante [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="97ec0-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="97ec0-135">En la esquina superior derecha, busque la opción para reiniciar o apagar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="97ec0-136">Realizar un reinicio forzado no seguro</span><span class="sxs-lookup"><span data-stu-id="97ec0-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="97ec0-137">Si los métodos anteriores no reiniciaron HoloLens, fuerce un reinicio.</span><span class="sxs-lookup"><span data-stu-id="97ec0-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="97ec0-138">Este método equivale a quitar y reinstalar la batería.</span><span class="sxs-lookup"><span data-stu-id="97ec0-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="97ec0-139">Es peligroso porque podría dejar el dispositivo en un estado dañado.</span><span class="sxs-lookup"><span data-stu-id="97ec0-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="97ec0-140">Si esto sucede, tendrá que flashear HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="97ec0-141">Se trata de un método potencialmente perjudicial y solo se debe usar si los métodos mencionados anteriormente no funcionaron.</span><span class="sxs-lookup"><span data-stu-id="97ec0-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="97ec0-142">Mantenga presionado el **botón de** encendido durante al menos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="97ec0-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="97ec0-143">Es correcto mantener presionado el botón durante más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="97ec0-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="97ec0-144">Es seguro omitir cualquier actividad de LED.</span><span class="sxs-lookup"><span data-stu-id="97ec0-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="97ec0-145">Suelte el botón y espere entre 2 y 3 segundos.</span><span class="sxs-lookup"><span data-stu-id="97ec0-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="97ec0-146">Mantenga presionado el **botón de** encendido durante 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="97ec0-147">Si sigue teniendo problemas,  presione el botón de encendido durante 4 segundos, hasta que todos los indicadores de batería se apaguen y la pantalla deje de mostrar hologramas.</span><span class="sxs-lookup"><span data-stu-id="97ec0-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="97ec0-148">Espere 1 minuto y presione de nuevo el **botón de** encendido para activar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="97ec0-149">Volver a una versión anterior: HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="97ec0-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="97ec0-150">En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="97ec0-151">Para ello, use la Herramienta de recuperación de dispositivos Windows para restablecer HoloLens a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="97ec0-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="97ec0-152">Al volver a una versión anterior, se eliminan los archivos y la configuración personales.</span><span class="sxs-lookup"><span data-stu-id="97ec0-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="97ec0-153">Para volver a una versión anterior de HoloLens 1, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="97ec0-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="97ec0-154">Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado al equipo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="97ec0-155">En el equipo, descargue la Herramienta [de recuperación de dispositivos Windows (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="97ec0-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="97ec0-156">Descargue el paquete [de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).</span><span class="sxs-lookup"><span data-stu-id="97ec0-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="97ec0-157">Cuando finalicen las descargas, abra el Explorador **de archivos**  >  **Descargas.**</span><span class="sxs-lookup"><span data-stu-id="97ec0-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="97ec0-158">Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer toda**  >  **la extracción** para descomprimirla.</span><span class="sxs-lookup"><span data-stu-id="97ec0-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="97ec0-159">Conecte holoLens al equipo mediante el cable micro USB con el que viene.</span><span class="sxs-lookup"><span data-stu-id="97ec0-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="97ec0-160">(Aunque haya estado usando otros cables para conectar HoloLens, este funciona mejor).</span><span class="sxs-lookup"><span data-stu-id="97ec0-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="97ec0-161">WDRT detectará automáticamente HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="97ec0-162">Seleccione el **icono Microsoft HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="97ec0-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="97ec0-163">En la siguiente pantalla, seleccione **Selección manual** de paquetes y elija el archivo de instalación incluido en la carpeta que descomprimió en el paso 4.</span><span class="sxs-lookup"><span data-stu-id="97ec0-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="97ec0-164">(Busque un archivo con la extensión .ffu).</span><span class="sxs-lookup"><span data-stu-id="97ec0-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="97ec0-165">Seleccione **Instalar software** y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="97ec0-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="97ec0-166">Si WDRT no detecta HoloLens, intente reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="97ec0-167">Si eso no funciona, seleccione Mi dispositivo no se detectó, **seleccione** Microsoft HoloLens y, a continuación, siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="97ec0-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="97ec0-168">Restablecimiento de la configuración de fábrica</span><span class="sxs-lookup"><span data-stu-id="97ec0-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="97ec0-169">La batería necesita al menos un 40 por ciento de carga para restablecerse.</span><span class="sxs-lookup"><span data-stu-id="97ec0-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="97ec0-170">Si holoLens sigue teniendo un problema, intente restablecerlo al estado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="97ec0-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="97ec0-171">Este paso mantiene la versión del software de Windows Holographic que está instalado en él y devuelve todo lo demás a la configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="97ec0-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="97ec0-172">Si restablece el dispositivo, se borrarán todos los datos personales, las aplicaciones y la configuración, incluida la información de restablecimiento de TPM.</span><span class="sxs-lookup"><span data-stu-id="97ec0-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="97ec0-173">El restablecimiento solo instalará la versión instalada más reciente de Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="97ec0-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="97ec0-174">Tendrá que rehacer todos los pasos de inicialización (calibrar, conectarse a Wi-Fi, crear una cuenta de usuario, descargar aplicaciones, entre otros).</span><span class="sxs-lookup"><span data-stu-id="97ec0-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="97ec0-175">Abra la aplicación Configuración y, a continuación, **seleccione Actualizar**  >  **recuperación.**</span><span class="sxs-lookup"><span data-stu-id="97ec0-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="97ec0-176">Seleccione la opción **Restablecer dispositivo** y lea el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="97ec0-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="97ec0-177">Confirme el restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="97ec0-177">Confirm the reset.</span></span> <span data-ttu-id="97ec0-178">El dispositivo se reiniciará y mostrará un conjunto de engranajes giratorios y una barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="97ec0-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="97ec0-179">Espere unos 30 minutos a que se complete este proceso.</span><span class="sxs-lookup"><span data-stu-id="97ec0-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="97ec0-180">Cuando haya terminado, el dispositivo se reiniciará en la experiencia "lista para su uso".</span><span class="sxs-lookup"><span data-stu-id="97ec0-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="97ec0-181">Reinstalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="97ec0-181">Reinstall the operating system</span></span>

<span data-ttu-id="97ec0-182">Si el dispositivo sigue teniendo un problema después de reiniciar y restablecer, puede usar una herramienta de recuperación en el equipo para volver a instalar el firmware y el sistema operativo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="97ec0-183">Los datos que HoloLens necesita para el restablecimiento se empaquetan en una actualización flash completa (FFU), que es similar a un archivo .iso, .wim o .vhd.</span><span class="sxs-lookup"><span data-stu-id="97ec0-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="97ec0-184">Obtenga información sobre los formatos de archivo de imagen de FFU.</span><span class="sxs-lookup"><span data-stu-id="97ec0-184">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="97ec0-185">Puede instalar un nuevo sistema operativo en HoloLens (1.ª generación) mediante la herramienta de recuperación de dispositivos windows.</span><span class="sxs-lookup"><span data-stu-id="97ec0-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="97ec0-186">Antes de usar esa herramienta, vea si el reinicio o el restablecimiento de HoloLens corrige el problema.</span><span class="sxs-lookup"><span data-stu-id="97ec0-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="97ec0-187">El proceso de recuperación puede tardar un tiempo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-187">The recovery process may take a while.</span></span> <span data-ttu-id="97ec0-188">Cuando haya terminado, se instalará la versión más reciente del software de Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="97ec0-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="97ec0-189">Para usar la herramienta, necesita un equipo que ejecute Windows 10 o posterior con al menos 4 GB de espacio de almacenamiento libre.</span><span class="sxs-lookup"><span data-stu-id="97ec0-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="97ec0-190">No se puede ejecutar esta herramienta en una máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="97ec0-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="97ec0-191">Recuperación de HoloLens</span><span class="sxs-lookup"><span data-stu-id="97ec0-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="97ec0-192">Descargue e instale la [Herramienta de recuperación de dispositivos Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) en el equipo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="97ec0-193">Conecte HoloLens (1.ª generación) al equipo mediante el cable Micro USB que se incluye con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="97ec0-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="97ec0-194">Abra la Herramienta de recuperación de dispositivos Windows y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="97ec0-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="97ec0-195">Si HoloLens (1.ª generación) no se detecta automáticamente, seleccione **Mi dispositivo no se detectó.**</span><span class="sxs-lookup"><span data-stu-id="97ec0-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="97ec0-196">A continuación, siga las instrucciones para poner el dispositivo en modo de recuperación.</span><span class="sxs-lookup"><span data-stu-id="97ec0-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="97ec0-197">Modo de parpadeo manual</span><span class="sxs-lookup"><span data-stu-id="97ec0-197">Manual flashing mode</span></span>

<span data-ttu-id="97ec0-198">Si no se detecta el dispositivo, siga estos pasos para ponerlo en modo de flashing:</span><span class="sxs-lookup"><span data-stu-id="97ec0-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="97ec0-199">Desconecte el dispositivo de cualquier fuente de alimentación.</span><span class="sxs-lookup"><span data-stu-id="97ec0-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="97ec0-200">Si el dispositivo está encendido, mantenga presionado el botón **de** encendido hasta que se apague completamente.</span><span class="sxs-lookup"><span data-stu-id="97ec0-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="97ec0-201">Mantenga presionado **el botón de** volumen y pulse brevemente el botón **de** encendido.</span><span class="sxs-lookup"><span data-stu-id="97ec0-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="97ec0-202">El dispositivo debe iniciarse y mostrar solo el LED central.</span><span class="sxs-lookup"><span data-stu-id="97ec0-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="97ec0-203">Conecte el dispositivo al equipo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="97ec0-204">Abra la Herramienta de recuperación de dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="97ec0-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="97ec0-205">Seleccione **Mi dispositivo no se detectó y,** a **continuación, HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="97ec0-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="97ec0-206">Siga las instrucciones para recuperar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97ec0-206">Follow the instructions to recover your device.</span></span>
