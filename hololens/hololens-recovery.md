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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915974"
---
# <span data-ttu-id="28c42-104">Reiniciar, restablecer o recuperar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="28c42-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="28c42-105">Cargar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="28c42-105">Charge the device</span></span>

<span data-ttu-id="28c42-106">Antes de iniciar un procedimiento de resolución de problemas, asegúrese de que la carga de la batería de su dispositivo se sitúe entre el 20 y 40% de capacidad, si es posible.</span><span class="sxs-lookup"><span data-stu-id="28c42-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="28c42-107">Utilice el cargador y los cables USB tipo C que vienen con el dispositivo HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="28c42-107">Use the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="28c42-108">Si dichos accesorios no están disponibles, asegúrese de que el cargador disponible admita al menos 15 vatios de energía.</span><span class="sxs-lookup"><span data-stu-id="28c42-108">If those accessories aren't available, make sure the charger that's available can support at least 15 W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="28c42-109">Si es posible, evite usar un PC para cargar el dispositivo por USB, pues implica una carga lenta.</span><span class="sxs-lookup"><span data-stu-id="28c42-109">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="28c42-110">Si el dispositivo se enciende y funciona correctamente, hay tres formas de comprobar la carga de la batería:</span><span class="sxs-lookup"><span data-stu-id="28c42-110">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="28c42-111">Desde el menú principal de la interfaz de usuario del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="28c42-111">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="28c42-112">Observe el LED cerca del botón de encendido (si la carga de la batería está al 40%, debería ver al menos dos LED fijos).</span><span class="sxs-lookup"><span data-stu-id="28c42-112">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
- <span data-ttu-id="28c42-113">En su equipo host, abra el Explorador de archivos y busque su dispositivo HoloLens 2 en el lado izquierdo bajo **Este PC**.</span><span class="sxs-lookup"><span data-stu-id="28c42-113">On your host PC, open File Explorer and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="28c42-114">Haga clic con el botón secundario en el dispositivo y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="28c42-114">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="28c42-115">Un cuadro de diálogo mostrará el nivel de carga de la batería.</span><span class="sxs-lookup"><span data-stu-id="28c42-115">A dialog box will show the battery charge level.</span></span>

   ![La pantalla de propiedades de HoloLens 2 muestra el nivel de cambio en la carga de batería](images/ResetRecovery2.png)

<span data-ttu-id="28c42-117">Si el dispositivo no puede arrancar en el menú de inicio, observe la apariencia del LED y la enumeración de dispositivos en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="28c42-117">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="28c42-118">A continuación, siga la [guía de solución de problemas](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="28c42-118">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="28c42-119">Si el estado del dispositivo no coincide con ninguno de los estados enumerados en la guía de solución de problemas, realice el *procedimiento de restablecimiento completo* con el dispositivo conectado a la fuente de alimentación, en lugar de al equipo host.</span><span class="sxs-lookup"><span data-stu-id="28c42-119">If the state of the device doesn't match any of the states listed in the troubleshooting guide, do the *hard reset procedure* with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="28c42-120">Espere al menos una hora para que el dispositivo se cargue.</span><span class="sxs-lookup"><span data-stu-id="28c42-120">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="28c42-121">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="28c42-121">Reset the device</span></span>

<span data-ttu-id="28c42-122">En determinadas circunstancias, puede que tenga que reiniciar manualmente el dispositivo sin utilizar el SW UI.</span><span class="sxs-lookup"><span data-stu-id="28c42-122">Under certain circumstances, you may have to manually reset the device without using the SW UI.</span></span>

### <span data-ttu-id="28c42-123">Procedimiento estándar</span><span class="sxs-lookup"><span data-stu-id="28c42-123">Standard procedure</span></span>
1. <span data-ttu-id="28c42-124">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="28c42-124">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="28c42-125">Mantenga pulsado el botón **de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="28c42-125">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="28c42-126">Todos los LEDs deberían estar apagados.</span><span class="sxs-lookup"><span data-stu-id="28c42-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="28c42-127">Espere de 2 a 3 segundos y, a continuación, pulse el botón de **Inicio/Apagado**.</span><span class="sxs-lookup"><span data-stu-id="28c42-127">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="28c42-128">Se encenderán los LEDs cercanos al botón de Inicio/Apagado y el dispositivo se iniciará.</span><span class="sxs-lookup"><span data-stu-id="28c42-128">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="28c42-129">Conecte el dispositivo al equipo host y, después, abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28c42-129">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="28c42-130">(Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="28c42-130">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="28c42-132">Procedimiento para hacer un restablecimiento completo</span><span class="sxs-lookup"><span data-stu-id="28c42-132">Hard-reset procedure</span></span>

<span data-ttu-id="28c42-133">Si el procedimiento de reinicio estándar no ha funcionado, utilice el procedimiento de restablecimiento completo:</span><span class="sxs-lookup"><span data-stu-id="28c42-133">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="28c42-134">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="28c42-134">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="28c42-135">Mantenga presionados los botones de **Bajar volumen** + **Inicio/Apagado** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="28c42-135">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="28c42-136">El dispositivo se reiniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="28c42-136">The device will automatically restart.</span></span>

4. <span data-ttu-id="28c42-137">Conecte el dispositivo al equipo host.</span><span class="sxs-lookup"><span data-stu-id="28c42-137">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="28c42-138">Abra el Administrador de dispositivos (para Windows 10, presione la tecla de **Windows** y, a continuación, la clave **X** y después seleccione **Administrador de dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="28c42-138">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="28c42-139">Asegúrese de que el dispositivo se muestre correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="28c42-139">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="28c42-141">Reprogramar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="28c42-141">Clean-reflash the device</span></span>

<span data-ttu-id="28c42-142">En situaciones extraordinarias, puede que tenga que reprogramar el dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="28c42-142">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="28c42-143">Hay dos formas de reprogramar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28c42-143">There are two ways to reflash the device.</span></span> <span data-ttu-id="28c42-144">En ambos casos, en primer lugar debe instalar [Advanced Recovery Companion desde la Tienda Windows](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="28c42-144">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="28c42-145">Si reprograma el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM.</span><span class="sxs-lookup"><span data-stu-id="28c42-145">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="28c42-146">De forma predeterminada, Advanced Recovery Companion está configurado en estos momentos para descargar la compilación del lanzamiento de características para [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="28c42-146">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="28c42-147">Para obtener el paquete más reciente de Full Flash Update (FFU) de HoloLens 2 para reprogramar el dispositivo mediante Advanced Recovery Companion, [descárguelo aquí](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="28c42-147">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="28c42-148">Esta versión es la compilación más reciente de la que se dispone de manera general.</span><span class="sxs-lookup"><span data-stu-id="28c42-148">This version is the latest generally available build.</span></span>

<span data-ttu-id="28c42-149">Antes de iniciar el procedimiento de reprogramación, asegúrese de que la aplicación esté instalada y en ejecución en su PC con Windows 10 y de que esté lista para detectar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28c42-149">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Captura de pantalla de la reprogramación de HoloLens 2](images/ARC1.png)

### <span data-ttu-id="28c42-151">Procedimiento normal</span><span class="sxs-lookup"><span data-stu-id="28c42-151">Normal procedure</span></span>

1. <span data-ttu-id="28c42-152">Mientras el dispositivo HoloLens está en funcionamiento, conéctelo al PC con Windows 10 en el que ha abierto previamente la aplicación Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="28c42-152">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="28c42-153">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="28c42-153">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla inicial de la reprogramación de HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="28c42-155">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y siga las instrucciones para completar la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="28c42-155">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="28c42-156">Procedimiento manual</span><span class="sxs-lookup"><span data-stu-id="28c42-156">Manual procedure</span></span>

<span data-ttu-id="28c42-157">Si el dispositivo HoloLens 2 no se inicia correctamente, puede que tenga que poner el dispositivo en modo de recuperación:</span><span class="sxs-lookup"><span data-stu-id="28c42-157">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="28c42-158">Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.</span><span class="sxs-lookup"><span data-stu-id="28c42-158">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="28c42-159">Mantenga pulsado el botón **de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="28c42-159">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="28c42-160">Todos los LEDs deberían apagarse.</span><span class="sxs-lookup"><span data-stu-id="28c42-160">All LEDs should turn off.</span></span>

3. <span data-ttu-id="28c42-161">Mientras mantiene pulsado el botón de **Subir volumen**, pulse y suelte el botón **de Inicio/Apagado** para encender el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28c42-161">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="28c42-162">Espere 15 segundos y suelte el botón de **Subir volumen**.</span><span class="sxs-lookup"><span data-stu-id="28c42-162">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="28c42-163">De los cinco LED, se encenderá solo el LED del centro.</span><span class="sxs-lookup"><span data-stu-id="28c42-163">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="28c42-164">Conecte el dispositivo al equipo host y abra el Administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28c42-164">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="28c42-165">(Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como Microsoft HoloLens, tal y como se muestra en la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="28c42-165">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="28c42-167">El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:</span><span class="sxs-lookup"><span data-stu-id="28c42-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Pantalla de la reprogramación de HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="28c42-169">Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y, a continuación, siga las instrucciones para completar la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="28c42-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="28c42-170">Descargar ARC sin usar la App Store</span><span class="sxs-lookup"><span data-stu-id="28c42-170">Download ARC without using the app store</span></span>

<span data-ttu-id="28c42-171">Si el entorno de TI impide el uso de la aplicación de la Tienda Windows o limita el acceso a la tienda comercial, el administrador de TI puede hacer que esta aplicación esté disponible a través de una ruta de acceso de implementación "sin conexión".</span><span class="sxs-lookup"><span data-stu-id="28c42-171">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="28c42-172">Los administradores de TI también pueden distribuir esta aplicación a través de System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="28c42-172">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="28c42-173">Esta guía se centra en Advanced Recovery Companion, pero el proceso se puede utilizar también para otras aplicaciones sin conexión.</span><span class="sxs-lookup"><span data-stu-id="28c42-173">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="28c42-174">Siga estos pasos para habilitar la ruta de acceso de implementación:</span><span class="sxs-lookup"><span data-stu-id="28c42-174">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="28c42-175">Vaya a la [Microsoft Store para Empresas](https://businessstore.microsoft.com) e inicie sesión con una identidad de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28c42-175">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="28c42-176">Vaya a **Administrar – Configuración**.</span><span class="sxs-lookup"><span data-stu-id="28c42-176">Go to **Manage – Settings**.</span></span> <span data-ttu-id="28c42-177">Active **Mostrar las aplicaciones sin conexión** en la **Experiencia de compra**.</span><span class="sxs-lookup"><span data-stu-id="28c42-177">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="28c42-178">Vaya a **comprar para mi grupo** y busque [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="28c42-178">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="28c42-179">Cambie el **Tipo de licencia** a ***sin conexión*** y seleccione **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="28c42-179">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="28c42-180">En **Descargar el paquete para uso sin conexión**, seleccione el segundo botón azul de **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="28c42-180">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="28c42-181">Asegúrese de que la extensión del archivo sea *.appxbundle*.</span><span class="sxs-lookup"><span data-stu-id="28c42-181">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="28c42-182">En esta etapa, si el PC de escritorio tiene acceso a Internet, haga doble clic en el paquete para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="28c42-182">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="28c42-183">Si el PC de destino no tiene conectividad a Internet, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="28c42-183">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="28c42-184">Seleccione la licencia sin codificar y, a continuación, seleccione **Generar licencia**.</span><span class="sxs-lookup"><span data-stu-id="28c42-184">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="28c42-185">En **Marcos necesarios**, seleccione **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="28c42-185">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="28c42-186">Use DISM para aplicar el paquete con la dependencia y la licencia.</span><span class="sxs-lookup"><span data-stu-id="28c42-186">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="28c42-187">Desde un símbolo del sistema de administrador, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="28c42-187">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="28c42-188">El número de versión en este ejemplo de código puede no coincidir con la versión disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="28c42-188">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="28c42-189">También puede que haya elegido una ubicación de descarga diferente a la del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="28c42-189">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="28c42-190">Realice los cambios necesarios en el comando.</span><span class="sxs-lookup"><span data-stu-id="28c42-190">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="28c42-191">Cuando planee usar Advanced Recovery Companion para instalar una FFU sin conexión, puede que resulte útil descargar la imagen flash.</span><span class="sxs-lookup"><span data-stu-id="28c42-191">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="28c42-192">[**Descargar la imagen actual para HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="28c42-192">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="28c42-193">Otros recursos:</span><span class="sxs-lookup"><span data-stu-id="28c42-193">Other resources:</span></span>
- [<span data-ttu-id="28c42-194">Distribuir aplicaciones sin conexión</span><span class="sxs-lookup"><span data-stu-id="28c42-194">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="28c42-195">Opciones de línea de comandos de servicio de paquete de aplicación DISM (.appx or .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="28c42-195">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
