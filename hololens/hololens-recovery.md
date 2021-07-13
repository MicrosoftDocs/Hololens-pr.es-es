---
title: Reinicio, restablecimiento o recuperación de HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Cómo usar Advanced Recovery Companion para instalar una imagen en HoloLens 2.
keywords: procedimientos, reiniciar, restablecer, recuperar, restablecimiento completo, restablecimiento parcial, reinicio, HoloLens, apagado, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923642"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="52218-104">Reinicio, restablecimiento o recuperación de HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="52218-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="52218-105">Antes de iniciar cualquier procedimiento de solución de problemas, asegúrese de que el dispositivo tenga entre un **20 y un 40 por ciento** de batería, si es posible.</span><span class="sxs-lookup"><span data-stu-id="52218-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="52218-106">Las [luces indicadoras de batería](hololens2-setup.md#lights-that-indicate-the-battery-level) que se encuentran debajo del botón de encendido son una manera rápida de comprobar la capacidad de la batería sin iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52218-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="52218-107">Use el [cable y cargador USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) incluidos con HoloLens 2, ya que esa es la mejor manera de cargar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52218-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="52218-108">El cargador suministra 18 W de potencia (9 V a 2 A).</span><span class="sxs-lookup"><span data-stu-id="52218-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="52218-109">Con el cargador de pared suministrado, los dispositivos HoloLens 2 pueden realizar una carga completa de la batería en menos de 65 minutos cuando el dispositivo está en modo de espera.</span><span class="sxs-lookup"><span data-stu-id="52218-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="52218-110">Si esos accesorios no están disponibles, asegúrese de que el cargador disponible admita al menos 15 W de potencia.</span><span class="sxs-lookup"><span data-stu-id="52218-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="52218-111">Si es posible, evite usar un equipo para cargar el dispositivo por USB, ya que eso es lento.</span><span class="sxs-lookup"><span data-stu-id="52218-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="52218-112">Si el dispositivo se ha encendido correctamente y está en funcionamiento, hay tres formas de comprobar el nivel de carga de la batería:</span><span class="sxs-lookup"><span data-stu-id="52218-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="52218-113">Desde el menú principal de la interfaz de usuario del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="52218-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="52218-114">Los LED situados junto al botón de encendido (para una carga de un 40 %, debería ver al menos dos LED fijos).</span><span class="sxs-lookup"><span data-stu-id="52218-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="52218-115">Cuando el dispositivo se está cargando, se ilumina el indicador de la batería para señalar el nivel de carga actual.</span><span class="sxs-lookup"><span data-stu-id="52218-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="52218-116">La última luz parpadea para indicar que se está cargando.</span><span class="sxs-lookup"><span data-stu-id="52218-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="52218-117">Cuando HoloLens está encendido, el indicador de la batería muestra el nivel de esta en cinco incrementos.</span><span class="sxs-lookup"><span data-stu-id="52218-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="52218-118">Si solo hay encendida una de las cinco luces, el nivel de la batería está por debajo del 20 por ciento.</span><span class="sxs-lookup"><span data-stu-id="52218-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="52218-119">Si el nivel de la batería es demasiado bajo y se intenta encender el dispositivo, una luz parpadea brevemente y después se apaga.</span><span class="sxs-lookup"><span data-stu-id="52218-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="52218-120">En el equipo host, abra **Explorador de archivos** y busque el dispositivo HoloLens 2 en el lado izquierdo, en **Este equipo**.</span><span class="sxs-lookup"><span data-stu-id="52218-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="52218-121">Haga clic con el botón derecho en el dispositivo y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="52218-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="52218-122">Un cuadro de diálogo muestra el nivel de carga de la batería.</span><span class="sxs-lookup"><span data-stu-id="52218-122">A dialog box will show the battery charge level.</span></span>

   ![Una pantalla de propiedades de HoloLens 2 muestra el nivel de carga de la batería](images/ResetRecovery2.png)

<span data-ttu-id="52218-124">Si el dispositivo no puede arrancar en el menú de inicio, observe la apariencia del LED y la enumeración de dispositivos en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="52218-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="52218-125">A continuación, siga la [guía de solución de problemas](hololens-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="52218-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="52218-126">Si el estado del dispositivo no coincide con ninguno de los estados indicados en la guía de solución de problemas, realice el [procedimiento de restablecimiento completo](hololens-recovery.md#hard-reset-procedure) con el dispositivo conectado a la fuente de alimentación, en lugar de al equipo host.</span><span class="sxs-lookup"><span data-stu-id="52218-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="52218-127">Espere al menos una hora para que el dispositivo se cargue.</span><span class="sxs-lookup"><span data-stu-id="52218-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="52218-128">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="52218-128">Reset the device</span></span>

<span data-ttu-id="52218-129">En determinadas circunstancias, puede que tenga que reiniciar manualmente el dispositivo sin utilizar la interfaz de usuario del software.</span><span class="sxs-lookup"><span data-stu-id="52218-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="52218-130">Procedimiento estándar</span><span class="sxs-lookup"><span data-stu-id="52218-130">Standard procedure</span></span>

1. <span data-ttu-id="52218-131">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="52218-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="52218-132">Mantenga presionado el botón de **encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="52218-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="52218-133">Deberían apagarse todas las luces LED.</span><span class="sxs-lookup"><span data-stu-id="52218-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="52218-134">Espere de 2 a 3 segundos y, a continuación, presione el botón de **encendido**.</span><span class="sxs-lookup"><span data-stu-id="52218-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="52218-135">Se encenderán las luces LED cercanas al botón de encendido y el dispositivo se iniciará.</span><span class="sxs-lookup"><span data-stu-id="52218-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="52218-136">Conecte el dispositivo al equipo host y, después, abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52218-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="52218-137">(En Windows 10, presione la tecla **Windows**, luego la tecla **X** y, a continuación, seleccione **Administrador de dispositivos**). Asegúrese de que el dispositivo aparece correctamente en la lista como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="52218-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Administrador de dispositivos para la recuperación de un dispositivo Microsoft HoloLens 2](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="52218-139">Procedimiento de restablecimiento completo</span><span class="sxs-lookup"><span data-stu-id="52218-139">Hard-reset procedure</span></span>

<span data-ttu-id="52218-140">Si el procedimiento de reinicio estándar no ha funcionado, utilice el procedimiento de restablecimiento completo:</span><span class="sxs-lookup"><span data-stu-id="52218-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="52218-141">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="52218-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="52218-142">Mantenga presionados los botones de **bajar volumen** + **encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="52218-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="52218-143">El dispositivo se reiniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="52218-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="52218-144">Conecte el dispositivo al equipo host.</span><span class="sxs-lookup"><span data-stu-id="52218-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="52218-145">Abra Administrador de dispositivos (en Windows 10, presione la tecla **Windows**, luego la tecla **X** y, a continuación, seleccione **Administrador de dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="52218-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="52218-146">Asegúrese de que el dispositivo aparece correctamente en la lista como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="52218-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Administrador de dispositivos 2 para la recuperación de un dispositivo Microsoft HoloLens 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="52218-148">Nueva instalación de la imagen del dispositivo</span><span class="sxs-lookup"><span data-stu-id="52218-148">Clean-reflash the device</span></span>

<span data-ttu-id="52218-149">En situaciones extraordinarias, puede que tenga que instalar de nuevo la imagen del dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="52218-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="52218-150">Tenga en cuenta que no se espera que esta opción solucione los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="52218-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="52218-151">Uniformidad de color de la pantalla</span><span class="sxs-lookup"><span data-stu-id="52218-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="52218-152">Arranque con sonido pero sin salida de pantalla</span><span class="sxs-lookup"><span data-stu-id="52218-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="52218-153">Patrón de LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="52218-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="52218-154">Overheating</span><span class="sxs-lookup"><span data-stu-id="52218-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="52218-155">Bloqueos del sistema operativo (distintos de los bloqueos de la aplicación)</span><span class="sxs-lookup"><span data-stu-id="52218-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="52218-156">Hay dos formas de volver a instalar la imagen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52218-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="52218-157">En ambas, antes debe [instalar Advanced Recovery Companion desde Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="52218-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="52218-158">Si vuelve a instalar la imagen del dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM.</span><span class="sxs-lookup"><span data-stu-id="52218-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="52218-159">De forma predeterminada, Advanced Recovery Companion está configurado para descargar la compilación de la versión de actualización de características más reciente; consulte las [notas de la versión](hololens-release-notes.md#) para obtener información sobre ella.</span><span class="sxs-lookup"><span data-stu-id="52218-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="52218-160">Para obtener el paquete en formato Full Flash Update (FFU) de HoloLens 2 más reciente y volver a instalar la imagen del dispositivo por medio de Advanced Recovery Companion, [haga clic aquí para descargar la imagen de actualización mensual de HoloLens 2 más reciente](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="52218-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="52218-161">Esta versión es la compilación más reciente disponible con carácter general.</span><span class="sxs-lookup"><span data-stu-id="52218-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="52218-162">Antes de iniciar el procedimiento de instalación de la imagen, asegúrese de que la aplicación esté instalada y en ejecución en su PC con Windows 10 y de que esté lista para detectar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52218-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="52218-163">Asegúrese también de que el dispositivo HoloLens está cargado al 40 % como mínimo.</span><span class="sxs-lookup"><span data-stu-id="52218-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Captura de pantalla de nueva instalación de la imagen de HoloLens 2](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="52218-165">Procedimiento normal</span><span class="sxs-lookup"><span data-stu-id="52218-165">Normal procedure</span></span>

1. <span data-ttu-id="52218-166">Con el dispositivo HoloLens está en funcionamiento, conéctelo al PC con Windows 10 en el que ha abierto previamente la aplicación Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="52218-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="52218-167">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="52218-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla inicial de la nueva instalación de la imagen de HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="52218-169">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y siga las instrucciones para completar la instalación de la imagen.</span><span class="sxs-lookup"><span data-stu-id="52218-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="52218-170">Procedimiento manual</span><span class="sxs-lookup"><span data-stu-id="52218-170">Manual procedure</span></span>

<span data-ttu-id="52218-171">Si el dispositivo HoloLens 2 no se inicia correctamente o si Advanced Recovery Companion no puede detectarlo, es posible que tenga que poner el dispositivo en modo de recuperación:</span><span class="sxs-lookup"><span data-stu-id="52218-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="52218-172">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="52218-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="52218-173">Mantenga presionado el botón de **encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="52218-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="52218-174">Todos los LED deberían apagarse.</span><span class="sxs-lookup"><span data-stu-id="52218-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="52218-175">Mientras presiona el botón para **subir volumen**, presione y suelte el botón de **encendido** para iniciar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52218-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="52218-176">Espere 15 segundos y, a continuación, suelte el botón para **subir volumen**.</span><span class="sxs-lookup"><span data-stu-id="52218-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="52218-177">De los cinco LED, se encenderá solo el LED del centro.</span><span class="sxs-lookup"><span data-stu-id="52218-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="52218-178">Conecte el dispositivo al equipo host y abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52218-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="52218-179">(En Windows 10, presione la tecla **Windows**, luego la tecla **X** y, a continuación, seleccione **Administrador de dispositivos**). Asegúrese de que el dispositivo aparece correctamente en la lista como Microsoft HoloLens, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="52218-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![Recuperación de Microsoft HoloLens 2](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="52218-181">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="52218-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla de nueva instalación de la imagen de HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="52218-183">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y, a continuación, siga las instrucciones para completar la nueva instalación de la imagen.</span><span class="sxs-lookup"><span data-stu-id="52218-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="52218-184">Solución de problemas de Advanced Recovery Companion</span><span class="sxs-lookup"><span data-stu-id="52218-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="52218-185">Asegúrese de que el dispositivo está cargado como mínimo al 40 % antes de intentar instalar la imagen.</span><span class="sxs-lookup"><span data-stu-id="52218-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="52218-186">Compruebe que el dispositivo está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="52218-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="52218-187">Si ARC no detecta el dispositivo, asegúrese de que puede conectarse a él desde el Explorador de archivos en el equipo.</span><span class="sxs-lookup"><span data-stu-id="52218-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="52218-188">Si no puede:</span><span class="sxs-lookup"><span data-stu-id="52218-188">If you cannot;</span></span>

    1.  <span data-ttu-id="52218-189">Es posible que el dispositivo tenga directivas USB que deshabiliten esa conexión.</span><span class="sxs-lookup"><span data-stu-id="52218-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="52218-190">Si es así, pruebe el [procedimiento manual](hololens-recovery.md#manual-procedure) para instalar la imagen.</span><span class="sxs-lookup"><span data-stu-id="52218-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="52218-191">Si no hay directivas, pruebe con otro cable USB.</span><span class="sxs-lookup"><span data-stu-id="52218-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="52218-192">Compruebe que el dispositivo no muestra un [patrón de LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).</span><span class="sxs-lookup"><span data-stu-id="52218-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="52218-193">Descarga de ARC sin usar la tienda de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="52218-193">Download ARC without using the app store</span></span>

<span data-ttu-id="52218-194">Si el entorno de TI impide el uso de la aplicación de Windows Store o limita el acceso a la tienda comercial, el administrador de TI puede hacer que esta aplicación esté disponible por medio de una ruta de acceso de implementación "sin conexión".</span><span class="sxs-lookup"><span data-stu-id="52218-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="52218-195">Los administradores de TI también pueden distribuir esta aplicación por medio de System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="52218-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="52218-196">Esta guía se centra en Advanced Recovery Companion, pero el proceso se puede utilizar también con otras aplicaciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="52218-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="52218-197">Siga estos pasos para habilitar la ruta de acceso de implementación:</span><span class="sxs-lookup"><span data-stu-id="52218-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="52218-198">Vaya a [Microsoft Store para Empresas](https://businessstore.microsoft.com) e inicie sesión con una identidad de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52218-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="52218-199">Vaya a **Administrar > Configuración**.</span><span class="sxs-lookup"><span data-stu-id="52218-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="52218-200">Active **Show offline apps** (Mostrar aplicaciones sin conexión) en **Shopping experience** (Experiencia de compra).</span><span class="sxs-lookup"><span data-stu-id="52218-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="52218-201">Vaya a **Comprar para mi grupo** y busque [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="52218-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="52218-202">Cambie **Tipo de licencia** a **_Sin conexión_ *_ y seleccione _* Administrar**.</span><span class="sxs-lookup"><span data-stu-id="52218-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="52218-203">En **Descargar el paquete para usar sin conexión**, seleccione el segundo botón azul **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="52218-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="52218-204">Asegúrese de que la extensión del archivo sea *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="52218-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="52218-205">En esta etapa, si el equipo de escritorio tiene acceso a Internet, haga doble clic en el paquete para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="52218-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="52218-206">Si el equipo de destino no tiene conectividad a Internet, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="52218-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="52218-207">Seleccione la licencia no codificada y, a continuación, **Generar licencia**.</span><span class="sxs-lookup"><span data-stu-id="52218-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="52218-208">En **Marcos necesarios**, seleccione **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="52218-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="52218-209">Use DISM para aplicar el paquete con la dependencia y la licencia.</span><span class="sxs-lookup"><span data-stu-id="52218-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="52218-210">Desde un símbolo del sistema de administrador, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="52218-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="52218-211">Puede que el número de versión de este ejemplo de código no coincida con la versión disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="52218-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="52218-212">También puede que haya elegido una ubicación de descarga diferente a la del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="52218-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="52218-213">Realice los cambios necesarios en el comando.</span><span class="sxs-lookup"><span data-stu-id="52218-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="52218-214">Cuando planee usar Advanced Recovery Companion para instalar una FFU sin conexión, puede que resulte útil descargar la imagen flash.</span><span class="sxs-lookup"><span data-stu-id="52218-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="52218-215">[**Descargue la imagen actual para HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="52218-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="52218-216">Otros recursos:</span><span class="sxs-lookup"><span data-stu-id="52218-216">Other resources:</span></span>
- [<span data-ttu-id="52218-217">Distribuir aplicaciones sin conexión</span><span class="sxs-lookup"><span data-stu-id="52218-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="52218-218">Opciones de línea de comandos de mantenimiento del paquete de la aplicación DISM (.appx o .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="52218-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
