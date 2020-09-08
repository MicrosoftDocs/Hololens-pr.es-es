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
ms.openlocfilehash: 8c028ed39cf0925ebff18ca69889de2d87f1e7eb
ms.sourcegitcommit: e3056a433aeebb8bc45dc3f6db9a75f212fdf53b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996418"
---
# <span data-ttu-id="2631b-104">Reiniciar, restablecer o recuperar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="2631b-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="2631b-105">Cargar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="2631b-105">Charge the device</span></span>

<span data-ttu-id="2631b-106">Antes de iniciar un procedimiento de resolución de problemas, asegúrese de que la carga de la batería de su dispositivo se sitúe entre el 20 y 40% de capacidad, si es posible.</span><span class="sxs-lookup"><span data-stu-id="2631b-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="2631b-107">Utilice el cargador y los cables USB tipo C que vienen con el dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2631b-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="2631b-108">La fuente de alimentación y el cable USB C a C incluidos con el dispositivo son la mejor forma de cargar tu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2631b-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="2631b-109">El cargador suministra 18W de potencia (9V a 2A).</span><span class="sxs-lookup"><span data-stu-id="2631b-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="2631b-110">Si dichos accesorios no están disponibles, asegúrese de que el cargador disponible admita al menos 15 vatios de potencia.</span><span class="sxs-lookup"><span data-stu-id="2631b-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="2631b-111">Si es posible, evite usar un PC para cargar el dispositivo por USB, pues implica una carga lenta.</span><span class="sxs-lookup"><span data-stu-id="2631b-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="2631b-112">Si el dispositivo se enciende y funciona correctamente, hay tres formas de comprobar la carga de la batería:</span><span class="sxs-lookup"><span data-stu-id="2631b-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="2631b-113">Desde el menú principal de la interfaz de usuario del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2631b-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="2631b-114">Observe el LED cerca del botón de encendido (si la carga de la batería está al 40%, debería ver al menos dos LED fijos).</span><span class="sxs-lookup"><span data-stu-id="2631b-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="2631b-115">Cuando se cargue el dispositivo, se iluminará el indicador de la batería para señalar el nivel de carga actual.</span><span class="sxs-lookup"><span data-stu-id="2631b-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="2631b-116">La última luz aparecerá y desaparecerá gradualmente para indicar la carga activa.</span><span class="sxs-lookup"><span data-stu-id="2631b-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="2631b-117">Cuando HoloLens está activado, el indicador de la batería muestra el nivel de la batería en cinco incrementos.</span><span class="sxs-lookup"><span data-stu-id="2631b-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="2631b-118">Cuando solo está encendida una de las cinco luces, significa que el nivel de batería se encuentra por debajo del 20 por ciento.</span><span class="sxs-lookup"><span data-stu-id="2631b-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="2631b-119">Si el nivel de la batería es críticamente bajo e intentas activar el dispositivo, una luz parpadeará brevemente y después se apagará.</span><span class="sxs-lookup"><span data-stu-id="2631b-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="2631b-120">En su equipo host, abra el **Explorador de archivos** y busque su dispositivo HoloLens 2 en el lado izquierdo bajo **Este equipo**.</span><span class="sxs-lookup"><span data-stu-id="2631b-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="2631b-121">Haga clic con el botón secundario en el dispositivo y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2631b-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="2631b-122">Un cuadro de diálogo mostrará el nivel de carga de la batería.</span><span class="sxs-lookup"><span data-stu-id="2631b-122">A dialog box will show the battery charge level.</span></span>

   ![La pantalla de propiedades de HoloLens 2 muestra el nivel de cambio en la carga de batería](images/ResetRecovery2.png)

<span data-ttu-id="2631b-124">Si el dispositivo no puede arrancar en el menú de inicio, observe la apariencia del LED y la enumeración de dispositivos en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="2631b-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="2631b-125">A continuación, siga la [guía de solución de problemas](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="2631b-125">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="2631b-126">Si el estado del dispositivo no coincide con ninguno de los estados enumerados en la guía de solución de problemas, realice el [procedimiento de restablecimiento completo](hololens-recovery.md#hard-reset-procedure) con el dispositivo conectado a la fuente de alimentación, en lugar de al equipo host.</span><span class="sxs-lookup"><span data-stu-id="2631b-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="2631b-127">Espere al menos una hora para que el dispositivo se cargue.</span><span class="sxs-lookup"><span data-stu-id="2631b-127">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="2631b-128">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="2631b-128">Reset the device</span></span>

<span data-ttu-id="2631b-129">En determinadas circunstancias, puede que tenga que reiniciar manualmente el dispositivo sin utilizar la UI del software.</span><span class="sxs-lookup"><span data-stu-id="2631b-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="2631b-130">Procedimiento estándar</span><span class="sxs-lookup"><span data-stu-id="2631b-130">Standard procedure</span></span>
1. <span data-ttu-id="2631b-131">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="2631b-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="2631b-132">Mantenga pulsado el botón **de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="2631b-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="2631b-133">Todos los LEDs deberían estar apagados.</span><span class="sxs-lookup"><span data-stu-id="2631b-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="2631b-134">Espere de 2 a 3 segundos y, a continuación, pulse el botón de **Inicio/Apagado**.</span><span class="sxs-lookup"><span data-stu-id="2631b-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="2631b-135">Se encenderán los LEDs cercanos al botón de Inicio/Apagado y el dispositivo se iniciará.</span><span class="sxs-lookup"><span data-stu-id="2631b-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="2631b-136">Conecte el dispositivo al equipo host y, después, abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2631b-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="2631b-137">(Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="2631b-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="2631b-139">Procedimiento para hacer un restablecimiento completo</span><span class="sxs-lookup"><span data-stu-id="2631b-139">Hard-reset procedure</span></span>

<span data-ttu-id="2631b-140">Si el procedimiento de reinicio estándar no ha funcionado, utilice el procedimiento de restablecimiento completo:</span><span class="sxs-lookup"><span data-stu-id="2631b-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="2631b-141">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="2631b-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="2631b-142">Mantenga presionados los botones de **Bajar volumen** + **Inicio/Apagado** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="2631b-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="2631b-143">El dispositivo se reiniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2631b-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="2631b-144">Conecte el dispositivo al equipo host.</span><span class="sxs-lookup"><span data-stu-id="2631b-144">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="2631b-145">Abra el Administrador de dispositivos (para Windows 10, presione la tecla de **Windows** y, a continuación, la clave **X** y después seleccione **Administrador de dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="2631b-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="2631b-146">Asegúrese de que el dispositivo se muestre correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="2631b-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="2631b-148">Reprogramar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="2631b-148">Clean-reflash the device</span></span>

<span data-ttu-id="2631b-149">En situaciones extraordinarias, puede que tenga que reprogramar el dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2631b-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="2631b-150">Tenga en cuenta que no se espera que restablecer el dispositivo afecte a los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="2631b-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="2631b-151">Mostrar uniformidad de color</span><span class="sxs-lookup"><span data-stu-id="2631b-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="2631b-152">Arranque con sonido pero sin salida de pantalla</span><span class="sxs-lookup"><span data-stu-id="2631b-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="2631b-153">Patrón LED 1-3-5</span><span class="sxs-lookup"><span data-stu-id="2631b-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="2631b-154">Sobrecalentamiento</span><span class="sxs-lookup"><span data-stu-id="2631b-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="2631b-155">Bloqueos del sistema operativo (que son distintos de los bloqueos de la aplicación)</span><span class="sxs-lookup"><span data-stu-id="2631b-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="2631b-156">Hay dos formas de reprogramar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2631b-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="2631b-157">En ambos casos, en primer lugar debe instalar [Advanced Recovery Companion desde la Tienda Windows](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="2631b-157">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="2631b-158">Si reprograma el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM.</span><span class="sxs-lookup"><span data-stu-id="2631b-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="2631b-159">De forma predeterminada, Advanced Recovery Companion está configurado en estos momentos para descargar la compilación del lanzamiento de características para [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="2631b-159">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="2631b-160">Para obtener el paquete más reciente de Full Flash Update (FFU) de HoloLens 2 para reprogramar el dispositivo mediante Advanced Recovery Companion, [descárguelo aquí](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="2631b-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="2631b-161">Esta versión es la compilación más reciente de la que se dispone de manera general.</span><span class="sxs-lookup"><span data-stu-id="2631b-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="2631b-162">Antes de iniciar el procedimiento de reprogramación, asegúrese de que la aplicación esté instalada y en ejecución en su PC con Windows 10 y de que esté lista para detectar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2631b-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Captura de pantalla de la reprogramación de HoloLens 2](images/ARC1.png)

### <span data-ttu-id="2631b-164">Procedimiento normal</span><span class="sxs-lookup"><span data-stu-id="2631b-164">Normal procedure</span></span>

1. <span data-ttu-id="2631b-165">Mientras el dispositivo HoloLens está en funcionamiento, conéctelo al PC con Windows 10 en el que ha abierto previamente la aplicación Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="2631b-165">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="2631b-166">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="2631b-166">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla inicial de la reprogramación de HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="2631b-168">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y siga las instrucciones para completar la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="2631b-168">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="2631b-169">Procedimiento manual</span><span class="sxs-lookup"><span data-stu-id="2631b-169">Manual procedure</span></span>

<span data-ttu-id="2631b-170">Si el dispositivo HoloLens 2 no se inicia correctamente, puede que tenga que poner el dispositivo en modo de recuperación:</span><span class="sxs-lookup"><span data-stu-id="2631b-170">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="2631b-171">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="2631b-171">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="2631b-172">Mantenga pulsado el botón **de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="2631b-172">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="2631b-173">Todos los LEDs deberían apagarse.</span><span class="sxs-lookup"><span data-stu-id="2631b-173">All LEDs should turn off.</span></span>

3. <span data-ttu-id="2631b-174">Mientras mantiene pulsado el botón de **Subir volumen**, pulse y suelte el botón **de Inicio/Apagado** para encender el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2631b-174">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="2631b-175">Espere 15 segundos y suelte el botón de **Subir volumen**.</span><span class="sxs-lookup"><span data-stu-id="2631b-175">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="2631b-176">De los cinco LED, se encenderá solo el LED del centro.</span><span class="sxs-lookup"><span data-stu-id="2631b-176">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="2631b-177">Conecte el dispositivo al equipo host y abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2631b-177">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="2631b-178">(Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como Microsoft HoloLens, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="2631b-178">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="2631b-180">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="2631b-180">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla de la reprogramación de HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="2631b-182">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y, a continuación, siga las instrucciones para completar la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="2631b-182">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="2631b-183">Descargar ARC sin usar la App Store</span><span class="sxs-lookup"><span data-stu-id="2631b-183">Download ARC without using the app store</span></span>

<span data-ttu-id="2631b-184">Si el entorno de TI impide el uso de la aplicación de la Tienda Windows o limita el acceso a la tienda comercial, el administrador de TI puede hacer que esta aplicación esté disponible a través de una ruta de acceso de implementación "sin conexión".</span><span class="sxs-lookup"><span data-stu-id="2631b-184">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="2631b-185">Los administradores de TI también pueden distribuir esta aplicación a través de System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="2631b-185">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="2631b-186">Esta guía se centra en Advanced Recovery Companion, pero el proceso se puede utilizar también para otras aplicaciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="2631b-186">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="2631b-187">Siga estos pasos para habilitar la ruta de acceso de implementación:</span><span class="sxs-lookup"><span data-stu-id="2631b-187">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="2631b-188">Vaya a la [Microsoft Store para Empresas](https://businessstore.microsoft.com) e inicie sesión con una identidad de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2631b-188">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="2631b-189">Vaya a **Administrar – Configuración**.</span><span class="sxs-lookup"><span data-stu-id="2631b-189">Go to **Manage – Settings**.</span></span> <span data-ttu-id="2631b-190">Active **Mostrar las aplicaciones sin conexión** en la **Experiencia de compra**.</span><span class="sxs-lookup"><span data-stu-id="2631b-190">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="2631b-191">Vaya a **comprar para mi grupo** y busque [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="2631b-191">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="2631b-192">Cambie el **Tipo de licencia** a ***sin conexión*** y seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="2631b-192">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="2631b-193">En **Descargar el paquete para uso sin conexión**, seleccione el segundo botón azul de **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="2631b-193">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="2631b-194">Asegúrese de que la extensión del archivo sea *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="2631b-194">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="2631b-195">En esta etapa, si el PC de escritorio tiene acceso a Internet, haga doble clic en el paquete para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2631b-195">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="2631b-196">Si el PC de destino no tiene conectividad a Internet, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2631b-196">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="2631b-197">Seleccione la licencia sin codificar y, a continuación, seleccione **Generar licencia**.</span><span class="sxs-lookup"><span data-stu-id="2631b-197">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="2631b-198">En **Marcos necesarios**, seleccione **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="2631b-198">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="2631b-199">Use DISM para aplicar el paquete con la dependencia y la licencia.</span><span class="sxs-lookup"><span data-stu-id="2631b-199">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="2631b-200">Desde un símbolo del sistema de administrador, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2631b-200">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="2631b-201">El número de versión en este ejemplo de código puede no coincidir con la versión disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="2631b-201">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="2631b-202">También puede que haya elegido una ubicación de descarga diferente a la del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2631b-202">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="2631b-203">Realice los cambios necesarios en el comando.</span><span class="sxs-lookup"><span data-stu-id="2631b-203">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="2631b-204">Cuando planee usar Advanced Recovery Companion para instalar una FFU sin conexión, puede que resulte útil descargar la imagen flash.</span><span class="sxs-lookup"><span data-stu-id="2631b-204">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="2631b-205">[**Descargar la imagen actual para HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="2631b-205">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="2631b-206">Otros recursos:</span><span class="sxs-lookup"><span data-stu-id="2631b-206">Other resources:</span></span>
- [<span data-ttu-id="2631b-207">Distribuir aplicaciones sin conexión</span><span class="sxs-lookup"><span data-stu-id="2631b-207">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="2631b-208">Opciones de línea de comandos de servicio de paquete de aplicación DISM (.appx or .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="2631b-208">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
