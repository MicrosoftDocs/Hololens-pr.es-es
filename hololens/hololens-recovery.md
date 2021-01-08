---
title: Reiniciar, restablecer o recuperar HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: Cómo usar el Advanced Recovery Companion para pasar una imagen a la HoloLens 2.
keywords: pasos para, reiniciar, resetear, recuperar, restablecimiento completo, restablecimiento parcial, ciclo de energía, HoloLens, apagado, arc, advanced recovery companion
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
ms.openlocfilehash: 7845a00d1141fb721683c4e3f2a884ed0c37c735
ms.sourcegitcommit: 33911e3b405732d0d31a27039c8f590d52b647c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "11254837"
---
# <span data-ttu-id="bf037-104">Reiniciar, restablecer o recuperar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bf037-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="bf037-105">Cargar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf037-105">Charge the device</span></span>

<span data-ttu-id="bf037-106">Antes de iniciar un procedimiento de resolución de problemas, asegúrese de que la carga de la batería de su dispositivo se sitúe entre el 20 y 40% de capacidad, si es posible.</span><span class="sxs-lookup"><span data-stu-id="bf037-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="bf037-107">Utilice el cargador y los cables USB tipo C que vienen con el dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bf037-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="bf037-108">La fuente de alimentación y el cable USB C a C incluidos con el dispositivo son la mejor forma de cargar tu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bf037-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="bf037-109">El cargador suministra 18W de potencia (9V a 2A).</span><span class="sxs-lookup"><span data-stu-id="bf037-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="bf037-110">Con el cargador de pared suministrado, los dispositivos HoloLens 2 pueden realizar una carga completa de la batería en menos de 65 minutos cuando el dispositivo está en modo de espera.</span><span class="sxs-lookup"><span data-stu-id="bf037-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="bf037-111">Si dichos accesorios no están disponibles, asegúrate de que el cargador disponible admita al menos 15 vatios de potencia.</span><span class="sxs-lookup"><span data-stu-id="bf037-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="bf037-112">Si es posible, evite usar un PC para cargar el dispositivo por USB, pues implica una carga lenta.</span><span class="sxs-lookup"><span data-stu-id="bf037-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="bf037-113">Si el dispositivo se enciende y funciona correctamente, hay tres formas de comprobar la carga de la batería:</span><span class="sxs-lookup"><span data-stu-id="bf037-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="bf037-114">Desde el menú principal de la interfaz de usuario del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bf037-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="bf037-115">Observe el LED cerca del botón de encendido (si la carga de la batería está al 40%, debería ver al menos dos LED fijos).</span><span class="sxs-lookup"><span data-stu-id="bf037-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="bf037-116">Cuando se cargue el dispositivo, se iluminará el indicador de la batería para señalar el nivel de carga actual.</span><span class="sxs-lookup"><span data-stu-id="bf037-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="bf037-117">La última luz aparecerá y desaparecerá gradualmente para indicar la carga activa.</span><span class="sxs-lookup"><span data-stu-id="bf037-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="bf037-118">Cuando HoloLens está activado, el indicador de la batería muestra el nivel de la batería en cinco incrementos.</span><span class="sxs-lookup"><span data-stu-id="bf037-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="bf037-119">Cuando solo está encendida una de las cinco luces, significa que el nivel de batería se encuentra por debajo del 20 por ciento.</span><span class="sxs-lookup"><span data-stu-id="bf037-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="bf037-120">Si el nivel de la batería es críticamente bajo e intentas activar el dispositivo, una luz parpadeará brevemente y después se apagará.</span><span class="sxs-lookup"><span data-stu-id="bf037-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="bf037-121">En su equipo host, abra el **Explorador de archivos** y busque su dispositivo HoloLens 2 en el lado izquierdo bajo **Este equipo**.</span><span class="sxs-lookup"><span data-stu-id="bf037-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="bf037-122">Haga clic con el botón secundario en el dispositivo y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf037-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="bf037-123">Un cuadro de diálogo mostrará el nivel de carga de la batería.</span><span class="sxs-lookup"><span data-stu-id="bf037-123">A dialog box will show the battery charge level.</span></span>

   ![La pantalla de propiedades de HoloLens 2 muestra el nivel de cambio en la carga de batería](images/ResetRecovery2.png)

<span data-ttu-id="bf037-125">Si el dispositivo no puede arrancar en el menú de inicio, observe la apariencia del LED y la enumeración de dispositivos en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="bf037-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="bf037-126">A continuación, siga la [guía de solución de problemas](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="bf037-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="bf037-127">Si el estado del dispositivo no coincide con ninguno de los estados enumerados en la guía de solución de problemas, realice el [procedimiento de restablecimiento completo](hololens-recovery.md#hard-reset-procedure) con el dispositivo conectado a la fuente de alimentación, en lugar de al equipo host.</span><span class="sxs-lookup"><span data-stu-id="bf037-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="bf037-128">Espere al menos una hora para que el dispositivo se cargue.</span><span class="sxs-lookup"><span data-stu-id="bf037-128">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="bf037-129">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf037-129">Reset the device</span></span>

<span data-ttu-id="bf037-130">En determinadas circunstancias, puede que tenga que reiniciar manualmente el dispositivo sin utilizar la UI del software.</span><span class="sxs-lookup"><span data-stu-id="bf037-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="bf037-131">Procedimiento estándar</span><span class="sxs-lookup"><span data-stu-id="bf037-131">Standard procedure</span></span>

1. <span data-ttu-id="bf037-132">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="bf037-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bf037-133">Mantenga pulsado el botón **de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="bf037-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="bf037-134">Todos los LEDs deberían estar apagados.</span><span class="sxs-lookup"><span data-stu-id="bf037-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="bf037-135">Espere de 2 a 3 segundos y, a continuación, pulse el botón de **Inicio/Apagado**.</span><span class="sxs-lookup"><span data-stu-id="bf037-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="bf037-136">Se encenderán los LEDs cercanos al botón de Inicio/Apagado y el dispositivo se iniciará.</span><span class="sxs-lookup"><span data-stu-id="bf037-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="bf037-137">Conecte el dispositivo al equipo host y, después, abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf037-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="bf037-138">(Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf037-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Administrador de dispositivos HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="bf037-140">Procedimiento para hacer un restablecimiento completo</span><span class="sxs-lookup"><span data-stu-id="bf037-140">Hard-reset procedure</span></span>

<span data-ttu-id="bf037-141">Si el procedimiento de reinicio estándar no ha funcionado, utilice el procedimiento de restablecimiento completo:</span><span class="sxs-lookup"><span data-stu-id="bf037-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="bf037-142">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="bf037-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bf037-143">Mantenga presionados los botones de **Bajar volumen** + **Inicio/Apagado** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="bf037-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="bf037-144">El dispositivo se reiniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bf037-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="bf037-145">Conecte el dispositivo al equipo host.</span><span class="sxs-lookup"><span data-stu-id="bf037-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="bf037-146">Abra el Administrador de dispositivos (para Windows 10, presione la tecla de **Windows** y, a continuación, la clave **X** y después seleccione **Administrador de dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="bf037-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="bf037-147">Asegúrese de que el dispositivo se muestre correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf037-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Administrador de dispositivos 2 HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="bf037-149">Reprogramar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf037-149">Clean-reflash the device</span></span>

<span data-ttu-id="bf037-150">En situaciones extraordinarias, puede que tenga que reprogramar el dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bf037-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="bf037-151">Tenga en cuenta que no se espera que restablecer el dispositivo afecte a los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="bf037-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="bf037-152">Mostrar uniformidad de color</span><span class="sxs-lookup"><span data-stu-id="bf037-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="bf037-153">Arranque con sonido pero sin salida de pantalla</span><span class="sxs-lookup"><span data-stu-id="bf037-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="bf037-154">Patrón LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="bf037-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="bf037-155">Sobrecalentamiento</span><span class="sxs-lookup"><span data-stu-id="bf037-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="bf037-156">Bloqueos del sistema operativo (que son distintos de los bloqueos de la aplicación)</span><span class="sxs-lookup"><span data-stu-id="bf037-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="bf037-157">Hay dos formas de reprogramar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf037-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="bf037-158">En ambos casos, primero debe [instalar el complemento de recuperación avanzada desde la Tienda Windows](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="bf037-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="bf037-159">Si reprograma el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM.</span><span class="sxs-lookup"><span data-stu-id="bf037-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="bf037-160">De forma predeterminada, el Asistente de recuperación avanzada está configurado para descargar la compilación de la versión de características más reciente, consulte aquí para leer nuestras [Notas de la versión](hololens-release-notes.md#) y obtener información sobre la última versión de características.</span><span class="sxs-lookup"><span data-stu-id="bf037-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="bf037-161">Para obtener el paquete de actualización completa de Flash (FFU) más reciente de HoloLens 2 para formatear el dispositivo a través del Asistente de recuperación avanzada, [haga clic aquí para descargar la última imagen mensual de HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="bf037-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="bf037-162">Esta versión es la compilación más reciente de la que se dispone de manera general.</span><span class="sxs-lookup"><span data-stu-id="bf037-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="bf037-163">Antes de iniciar el procedimiento de reprogramación, asegúrese de que la aplicación esté instalada y en ejecución en su PC con Windows 10 y de que esté lista para detectar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf037-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="bf037-164">Asegúrate también de que tu HoloLens se cargue al 40 % como mínimo.</span><span class="sxs-lookup"><span data-stu-id="bf037-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Captura de pantalla de la reprogramación de HoloLens 2](images/ARC1.png)

### <span data-ttu-id="bf037-166">Procedimiento normal</span><span class="sxs-lookup"><span data-stu-id="bf037-166">Normal procedure</span></span>

1. <span data-ttu-id="bf037-167">Mientras el dispositivo HoloLens está en funcionamiento, conéctelo al PC con Windows 10 en el que ha abierto previamente la aplicación Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="bf037-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="bf037-168">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="bf037-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla inicial de la reprogramación de HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="bf037-170">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y siga las instrucciones para completar la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="bf037-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="bf037-171">Procedimiento manual</span><span class="sxs-lookup"><span data-stu-id="bf037-171">Manual procedure</span></span>

<span data-ttu-id="bf037-172">Si el dispositivo HoloLens 2 no se inicia correctamente, puede que tenga que poner el dispositivo en modo de recuperación:</span><span class="sxs-lookup"><span data-stu-id="bf037-172">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="bf037-173">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="bf037-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bf037-174">Mantenga pulsado el botón **de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="bf037-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="bf037-175">Todos los LEDs deberían apagarse.</span><span class="sxs-lookup"><span data-stu-id="bf037-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="bf037-176">Mientras mantiene pulsado el botón de **Subir volumen**, pulse y suelte el botón **de Inicio/Apagado** para encender el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf037-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="bf037-177">Espere 15 segundos y suelte el botón de **Subir volumen**.</span><span class="sxs-lookup"><span data-stu-id="bf037-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="bf037-178">De los cinco LED, se encenderá solo el LED del centro.</span><span class="sxs-lookup"><span data-stu-id="bf037-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="bf037-179">Conecte el dispositivo al equipo host y abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf037-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="bf037-180">(Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como Microsoft HoloLens, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf037-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="bf037-182">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="bf037-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla de la reprogramación de HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="bf037-184">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y, a continuación, siga las instrucciones para completar la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="bf037-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="bf037-185">Descargar ARC sin usar la App Store</span><span class="sxs-lookup"><span data-stu-id="bf037-185">Download ARC without using the app store</span></span>

<span data-ttu-id="bf037-186">Si el entorno de TI impide el uso de la aplicación de la Tienda Windows o limita el acceso a la tienda comercial, el administrador de TI puede hacer que esta aplicación esté disponible a través de una ruta de acceso de implementación "sin conexión".</span><span class="sxs-lookup"><span data-stu-id="bf037-186">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="bf037-187">Los administradores de TI también pueden distribuir esta aplicación a través de System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="bf037-187">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="bf037-188">Esta guía se centra en Advanced Recovery Companion, pero el proceso se puede utilizar también para otras aplicaciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="bf037-188">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="bf037-189">Siga estos pasos para habilitar la ruta de acceso de implementación:</span><span class="sxs-lookup"><span data-stu-id="bf037-189">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="bf037-190">Vaya a la [Microsoft Store para Empresas](https://businessstore.microsoft.com) e inicie sesión con una identidad de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bf037-190">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="bf037-191">Vaya a **Administrar – Configuración**.</span><span class="sxs-lookup"><span data-stu-id="bf037-191">Go to **Manage – Settings**.</span></span> <span data-ttu-id="bf037-192">Active **Mostrar las aplicaciones sin conexión** en la **Experiencia de compra**.</span><span class="sxs-lookup"><span data-stu-id="bf037-192">Turn on **Show offline apps** under **Shopping experience**.</span></span>
1. <span data-ttu-id="bf037-193">Vaya a **tienda para mi grupo** y busque el [\**_Asistente de recuperación avanzada_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="bf037-193">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="bf037-194">Cambie el _*Tipo de licencia*\* a \**_sin conexión_*_ y seleccione _\*Administrar\*\*.</span><span class="sxs-lookup"><span data-stu-id="bf037-194">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="bf037-195">En **Descargar el paquete para uso sin conexión**, seleccione el segundo botón azul de **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="bf037-195">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="bf037-196">Asegúrese de que la extensión del archivo sea *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="bf037-196">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="bf037-197">En esta etapa, si el PC de escritorio tiene acceso a Internet, haz doble clic en el paquete para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf037-197">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="bf037-198">Si el PC de destino no tiene conectividad a Internet, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bf037-198">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="bf037-199">Selecciona la licencia sin codificar y, a continuación, selecciona **Generar licencia**.</span><span class="sxs-lookup"><span data-stu-id="bf037-199">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="bf037-200">En **Marcos necesarios**, seleccione **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="bf037-200">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="bf037-201">Use DISM para aplicar el paquete con la dependencia y la licencia.</span><span class="sxs-lookup"><span data-stu-id="bf037-201">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="bf037-202">Desde un símbolo del sistema de administrador, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bf037-202">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="bf037-203">El número de versión en este ejemplo de código puede no coincidir con la versión disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="bf037-203">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="bf037-204">También puede que haya elegido una ubicación de descarga diferente a la del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bf037-204">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="bf037-205">Realice los cambios necesarios en el comando.</span><span class="sxs-lookup"><span data-stu-id="bf037-205">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="bf037-206">Cuando planee usar Advanced Recovery Companion para instalar una FFU sin conexión, puede que resulte útil descargar la imagen flash.</span><span class="sxs-lookup"><span data-stu-id="bf037-206">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="bf037-207">[**Descargar la imagen actual para HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="bf037-207">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>

<span data-ttu-id="bf037-208">Otros recursos:</span><span class="sxs-lookup"><span data-stu-id="bf037-208">Other resources:</span></span>
- [<span data-ttu-id="bf037-209">Distribuir aplicaciones sin conexión</span><span class="sxs-lookup"><span data-stu-id="bf037-209">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="bf037-210">Opciones de línea de comandos de servicio de paquete de aplicación DISM (.appx or .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="bf037-210">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
