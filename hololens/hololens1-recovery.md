---
title: Reinicie, restablezca o recupere el HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: a52e8e5bae49973d92efa6ea75391dc44d8b8ddb
ms.sourcegitcommit: 357094acfd39f7c59a0a62f1dd7918b58c209ef7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "10861165"
---
# <span data-ttu-id="08a17-104">Reiniciar, restablecer o recuperar HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="08a17-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="08a17-105">Si tiene problemas con su HoloLens, puede probar reiniciar, restablecer o incluso volver a flashear con el modo recuperación del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08a17-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="08a17-106">Aquí tiene algunas cosas que puede probar si su HoloLens no está funcionando bien.</span><span class="sxs-lookup"><span data-stu-id="08a17-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="08a17-107">Este artículo le guiará a través de los pasos de recuperación recomendados en orden.</span><span class="sxs-lookup"><span data-stu-id="08a17-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="08a17-108">Si quiere recuperar un HoloLens 2, por favor visite la página para[Recuperación de un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), ya que hay diferencias en los procesos.</span><span class="sxs-lookup"><span data-stu-id="08a17-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="08a17-109">Este artículo se centra en el dispositivo y el software HoloLens, si sus hologramas no se ven bien,[este artículo](hololens-environment-considerations.md) habla de los factores ambientales que mejoran la calidad de los hologramas.</span><span class="sxs-lookup"><span data-stu-id="08a17-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="08a17-110">Reiniciar</span><span class="sxs-lookup"><span data-stu-id="08a17-110">Restart</span></span>

### <span data-ttu-id="08a17-111">Realizar un reinicio seguro usando Cortana</span><span class="sxs-lookup"><span data-stu-id="08a17-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="08a17-112">La forma más segura de reiniciar el HoloLens es usando Cortana.</span><span class="sxs-lookup"><span data-stu-id="08a17-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="08a17-113">Generalmente este es un primer paso fácil cuando se experimenta un problema con el HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08a17-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="08a17-114">Cortana no está disponible para todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08a17-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="08a17-115">Cortana está disponible para todos los dispositivos HoloLens (1 era generación).</span><span class="sxs-lookup"><span data-stu-id="08a17-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="08a17-116">Cortana está disponible en los dispositivos HoloLens 2 en una versión anterior a la actualización de Windows Holograpic, versión 2004.</span><span class="sxs-lookup"><span data-stu-id="08a17-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="08a17-117">Póngalo en su dispositivo</span><span class="sxs-lookup"><span data-stu-id="08a17-117">Put on your device</span></span>
1. <span data-ttu-id="08a17-118">Asegúrese de que esté encendido, que un usuario haya iniciado sesión y que el dispositivo no esté esperando una contraseña para desbloquearlo.</span><span class="sxs-lookup"><span data-stu-id="08a17-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="08a17-119">Diga "Hey Cortana, reinicio" o "Hey Cortana, reiniciar".</span><span class="sxs-lookup"><span data-stu-id="08a17-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="08a17-120">Cuando lo reconozca, le pedirá una confirmación.</span><span class="sxs-lookup"><span data-stu-id="08a17-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="08a17-121">Espere un segundo después de que termine su pregunta hasta escuchar un sonido, indicando que lo está escuchando y luego diga "Sí".</span><span class="sxs-lookup"><span data-stu-id="08a17-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="08a17-122">El dispositivo se reiniciará ahora.</span><span class="sxs-lookup"><span data-stu-id="08a17-122">The device will now restart.</span></span>

### <span data-ttu-id="08a17-123">Realice un reinicio seguro usando el botón de encendido</span><span class="sxs-lookup"><span data-stu-id="08a17-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="08a17-124">Si aún así no puede reiniciar el dispositivo, puede intentarlo con el botón de encendido:</span><span class="sxs-lookup"><span data-stu-id="08a17-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="08a17-125">Mantenga pulsado el botón de encendido durante cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="08a17-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="08a17-126">Después de un segundo, verá que los cinco LEDs se iluminan, y luego se apagan lentamente de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="08a17-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="08a17-127">Después de cinco segundos, todos los LEDs se apagarán, indicando que el comando de apagado fue emitido con éxito.</span><span class="sxs-lookup"><span data-stu-id="08a17-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="08a17-128">Tenga en cuenta que es importante dejar de pulsar el botón inmediatamente después de que todos los LEDs se hayan apagado.</span><span class="sxs-lookup"><span data-stu-id="08a17-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="08a17-129">Espere un minuto para que el apagado tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="08a17-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="08a17-130">Tenga en cuenta que el apagado puede estar en curso incluso si las pantallas están apagadas.</span><span class="sxs-lookup"><span data-stu-id="08a17-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="08a17-131">Encienda el dispositivo de nuevo presionando y manteniendo el botón de encendido por un segundo.</span><span class="sxs-lookup"><span data-stu-id="08a17-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="08a17-132">Realice un reinicio seguro usando el Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="08a17-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="08a17-133">Para ello, el HoloLens tiene que ser configurado como un dispositivo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="08a17-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="08a17-134">Obtenga más información acerca del [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="08a17-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="08a17-135">Si el procedimiento anterior no funciona, puede intentar reiniciar el dispositivo mediante el[Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="08a17-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="08a17-136">En la esquina superior derecha, hay una opción para reiniciar o apagar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08a17-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="08a17-137">Realice un reinicio forzado inseguro</span><span class="sxs-lookup"><span data-stu-id="08a17-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="08a17-138">Si ninguno de los métodos anteriores es capaz de reiniciar con éxito su dispositivo, puede forzar un reinicio.</span><span class="sxs-lookup"><span data-stu-id="08a17-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="08a17-139">Este método equivale a sacar la batería del HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08a17-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="08a17-140">Es una operación peligrosa que puede dejar su dispositivo en un estado corrupto.</span><span class="sxs-lookup"><span data-stu-id="08a17-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="08a17-141">Si eso sucede, tendrá que flashear su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08a17-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="08a17-142">Se trata de un método potencialmente nocivo y sólo debe utilizarse en caso de que ninguno de los métodos anteriores funcione.</span><span class="sxs-lookup"><span data-stu-id="08a17-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="08a17-143">Mantenga presionado el botón de encendido por lo menos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="08a17-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="08a17-144">Está bien mantener el botón durante más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="08a17-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="08a17-145">Es seguro ignorar cualquier actividad de los LED.</span><span class="sxs-lookup"><span data-stu-id="08a17-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="08a17-146">Suelte el botón y espere dos o tres segundos.</span><span class="sxs-lookup"><span data-stu-id="08a17-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="08a17-147">Encienda el dispositivo de nuevo presionando y manteniendo el botón de encendido por un segundo.</span><span class="sxs-lookup"><span data-stu-id="08a17-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="08a17-148">Si sigue teniendo problemas, pulse el botón de encendido durante 4 segundos, hasta que todos los indicadores de la batería se apaguen y la pantalla deje de mostrar hologramas.</span><span class="sxs-lookup"><span data-stu-id="08a17-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="08a17-149">Espere 1 minuto, luego presione el botón de encendido de nuevo para encender el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08a17-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="08a17-150">Restaurar la configuración de fábrica</span><span class="sxs-lookup"><span data-stu-id="08a17-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="08a17-151">La batería necesita al menos un 40 por ciento de carga para reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="08a17-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="08a17-152">Si su HoloLens sigue experimentando problemas después de reiniciar, intente restablecerlo al estado de fábrica.</span><span class="sxs-lookup"><span data-stu-id="08a17-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="08a17-153">Al reiniciar su HoloLens se mantiene la versión del software holográfico de Windows que está instalado en él y se reinicia todo lo demás a la configuración de fábrica.</span><span class="sxs-lookup"><span data-stu-id="08a17-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="08a17-154">Si restablece el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluido el restablecimiento del TPM.</span><span class="sxs-lookup"><span data-stu-id="08a17-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="08a17-155">Al reiniciar sólo se instalará la última versión instalada de Windows Holographic y tendrá que rehacer todos los pasos de inicialización (calibrar, conectar a Wi-Fi, crear una cuenta de usuario, descargar aplicaciones, etc.).</span><span class="sxs-lookup"><span data-stu-id="08a17-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="08a17-156">Inicie la aplicación Ajustes, y luego seleccione **Actualizar** > **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="08a17-156">Launch the Settings app, and then select **Update** > **Reset**.</span></span>
1. <span data-ttu-id="08a17-157">Seleccione la opción**Reiniciar el dispositivo**y lea el mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="08a17-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="08a17-158">Si acepta reiniciar el dispositivo, éste se reiniciará y mostrará un conjunto de engranajes giratorios con una barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="08a17-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="08a17-159">Espere unos 30 minutos para que este proceso se complete.</span><span class="sxs-lookup"><span data-stu-id="08a17-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="08a17-160">El reinicio se completará y el dispositivo se reiniciará en la experiencia listo para usar.</span><span class="sxs-lookup"><span data-stu-id="08a17-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="08a17-161">Reinstale el sistema operativo</span><span class="sxs-lookup"><span data-stu-id="08a17-161">Re-install the operating system</span></span>

<span data-ttu-id="08a17-162">Si el dispositivo sigue teniendo un problema después de reiniciar y restaurar, puede utilizar una herramienta de recuperación en su ordenador para reinstalar el sistema operativo y el firmware del HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08a17-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="08a17-163">Todos los datos que el HoloLens necesita para reiniciar están empaquetados en una actualización de Full Flash (ffu).</span><span class="sxs-lookup"><span data-stu-id="08a17-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="08a17-164">Esto es similar a un iso, wim o vhd.</span><span class="sxs-lookup"><span data-stu-id="08a17-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="08a17-165">Aprenda sobre los formatos de archivos de imagen FFU.</span><span class="sxs-lookup"><span data-stu-id="08a17-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="08a17-166">Si es necesario, puede instalar un sistema operativo completamente nuevo en su HoloLens (1 era generación) con Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="08a17-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="08a17-167">Antes de usar esta herramienta, determine si reiniciando o restableciendo su HoloLens se soluciona el problema.</span><span class="sxs-lookup"><span data-stu-id="08a17-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="08a17-168">El proceso de recuperación puede llevar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="08a17-168">The recovery process may take some time.</span></span>  <span data-ttu-id="08a17-169">Cuando termine, se instalará la última versión del software holográfico de Windows aprobado para su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08a17-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="08a17-170">Para usar la herramienta, necesitará un ordenador con Windows 10 o posterior, con al menos 4 GB de espacio de almacenamiento libre.</span><span class="sxs-lookup"><span data-stu-id="08a17-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="08a17-171">Tenga en cuenta que no puede ejecutar esta herramienta en una máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="08a17-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="08a17-172">Recupere su HoloLens:</span><span class="sxs-lookup"><span data-stu-id="08a17-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="08a17-173">Descargue e instale [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) en su ordenador.</span><span class="sxs-lookup"><span data-stu-id="08a17-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="08a17-174">Conecte HoloLens (1 era generación) a su ordenador con el cable Micro USB que viene con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="08a17-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="08a17-175">Ejecute Windows Device Recovery Tool y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="08a17-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="08a17-176">Si el HoloLens (1 era generación) no se detecta automáticamente, seleccione \*\*Mi dispositivo no fue detectado \*\*y siga las instrucciones para poner su dispositivo en modo de recuperación.</span><span class="sxs-lookup"><span data-stu-id="08a17-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="08a17-177">Manual del modo flasheo:</span><span class="sxs-lookup"><span data-stu-id="08a17-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="08a17-178">En el caso de que su dispositivo no sea detectado, por favor utilice el siguiente método para colocarlo manualmente en modo intermitente.</span><span class="sxs-lookup"><span data-stu-id="08a17-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="08a17-179">Desconecte el dispositivo de todas las fuentes de energía.</span><span class="sxs-lookup"><span data-stu-id="08a17-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="08a17-180">Si el dispositivo está encendido, por favor mantenga pulsado el botón de encendido hasta que esté completamente apagado.</span><span class="sxs-lookup"><span data-stu-id="08a17-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="08a17-181">Mantenga presionado el botón de **Subir volumen** y pulse el **botón de Inicio/Apagado**.</span><span class="sxs-lookup"><span data-stu-id="08a17-181">Hold the **Volume Up** button, and briefly tap the **Power button**.</span></span> 
1. <span data-ttu-id="08a17-182">El dispositivo debería iniciar y luego mostrar sólo la luz LED del medio.</span><span class="sxs-lookup"><span data-stu-id="08a17-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="08a17-183">Enchufe el dispositivo en su PC.</span><span class="sxs-lookup"><span data-stu-id="08a17-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="08a17-184">Ejecute Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="08a17-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="08a17-185">Tendrá que seleccionar \*Mi dispositivo no fue detectado**, y luego seleccione**HoloLens\*\*.</span><span class="sxs-lookup"><span data-stu-id="08a17-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="08a17-186">Siga las instrucciones para recuperar su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="08a17-186">Follow the instructions to recover your device.</span></span>
