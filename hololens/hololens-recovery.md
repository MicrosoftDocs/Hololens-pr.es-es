---
title: Reiniciar, restablecer o recuperar HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828596"
---
# <span data-ttu-id="26fc2-104">Reseteo y recuperación para el HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="26fc2-104">Reset and Recovery for HoloLens 2</span></span>

## <span data-ttu-id="26fc2-105">Cargando el dispositivo</span><span class="sxs-lookup"><span data-stu-id="26fc2-105">Charging the device</span></span>

<span data-ttu-id="26fc2-106">Antes de iniciar cualquier procedimiento de resolución de problemas, si es posible, asegúrese de que su dispositivo tiene una carga de por lo menos entre el 20% y el 40%.</span><span class="sxs-lookup"><span data-stu-id="26fc2-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="26fc2-107">Por favor, asegúrese de que está utilizando el cargador y los cables USB tipo C que vienen con el dispositivo HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="26fc2-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="26fc2-108">En caso de que no esté disponible, asegúrese de que el cargador disponible pueda soportar al menos 15W de potencia.</span><span class="sxs-lookup"><span data-stu-id="26fc2-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="26fc2-109">Si es posible, no utilice un PC para cargar el dispositivo a través de USB ya que esto proporcionará una carga muy lenta.</span><span class="sxs-lookup"><span data-stu-id="26fc2-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="26fc2-110">Si el dispositivo se enciende y funciona correctamente, hay tres formas diferentes de comprobar la carga de la batería.</span><span class="sxs-lookup"><span data-stu-id="26fc2-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="26fc2-111">Desde el menú principal de la interfaz del dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="26fc2-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="26fc2-112">Usando el LED cerca del botón de encendido (para el 40% debería ver al menos dos LEDs sólidos).</span><span class="sxs-lookup"><span data-stu-id="26fc2-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="26fc2-113">En su equipo host abra la ventana del Explorador de archivos y busque su dispositivo HoloLens 2 en el lado izquierdo bajo "Esta PC".</span><span class="sxs-lookup"><span data-stu-id="26fc2-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="26fc2-114">a.</span><span class="sxs-lookup"><span data-stu-id="26fc2-114">a.</span></span> <span data-ttu-id="26fc2-115">Haga clic con el botón derecho del ratón en el nombre del dispositivo y seleccione las propiedades.</span><span class="sxs-lookup"><span data-stu-id="26fc2-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="26fc2-116">Aparecerá un diálogo que muestra el nivel de la batería de su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-116">A dialog will appear showing the battery level for your device.</span></span>

![Recuperación de restablecimiento de HoloLens 2](images/ResetRecovery2.png)

<span data-ttu-id="26fc2-118">Si no se puede iniciar el dispositivo en el menú de inicio, tome nota de los LED y la enumeración en el equipo host y siga la guía de solución de problemas (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="26fc2-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="26fc2-119">En caso de que el estado del dispositivo no se encuentre en ninguno de los estados enumerados en la guía de solución de problemas, ejecute el\*\* procedimiento de restablecimiento completo\*\* sin volver a conectar el dispositivo a su equipo host, sino que lo conecte a la fuente de alimentación</span><span class="sxs-lookup"><span data-stu-id="26fc2-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="26fc2-120">Espere al menos una hora para que el dispositivo se cargue.</span><span class="sxs-lookup"><span data-stu-id="26fc2-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="26fc2-121">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="26fc2-121">Reset the device</span></span>

<span data-ttu-id="26fc2-122">En determinadas circunstancias, el cliente puede verse obligado a reiniciar manualmente el dispositivo sin utilizar el SW UI.</span><span class="sxs-lookup"><span data-stu-id="26fc2-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="26fc2-123">Procedimiento estándar</span><span class="sxs-lookup"><span data-stu-id="26fc2-123">Standard procedure</span></span>
1. <span data-ttu-id="26fc2-124">Desconecte el dispositivo de la fuente de alimentación o del equipo host desenchufando el cable de tipo C.</span><span class="sxs-lookup"><span data-stu-id="26fc2-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="26fc2-125">Mantenga pulsado el **botón de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="26fc2-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="26fc2-126">Todos los LEDs deberían estar apagados.</span><span class="sxs-lookup"><span data-stu-id="26fc2-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="26fc2-127">Espere 2-3 segundos y presione brevemente el **botón de encendido**, los LEDs cercanos al botón de encendido se encenderán y el dispositivo comenzará a arrancar.</span><span class="sxs-lookup"><span data-stu-id="26fc2-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="26fc2-128">Conecte el dispositivo al equipo host, abra el Administrador de dispositivos (para Windows 10 pulse la tecla **"Windows"** y luego la tecla **"x"** y haga clic en "Administrador de dispositivos") y asegúrese de que el dispositivo se enumera correctamente como HoloLente de Microsoft como se muestra en las siguientes imágenes:</span><span class="sxs-lookup"><span data-stu-id="26fc2-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

### <span data-ttu-id="26fc2-130">Procedimiento para hacer un restablecimiento completo</span><span class="sxs-lookup"><span data-stu-id="26fc2-130">Hard-reset procedure</span></span>

<span data-ttu-id="26fc2-131">Si el procedimiento de reinicio estándar no funciona, puede utilizar el procedimiento de restablecimiento completo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="26fc2-132">Desconecte el dispositivo de la fuente de alimentación o del equipo host desenchufando el cable de tipo C.</span><span class="sxs-lookup"><span data-stu-id="26fc2-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="26fc2-133">Mantenga presionado el botón de\*\* volumen + el botón de encendido \*\* durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="26fc2-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="26fc2-134">El dispositivo se reiniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="26fc2-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="26fc2-135">Conecte el dispositivo a el equipo host, abra el Administrador de dispositivos (para Windows 10 pulse la tecla **"Windows"** y luego la tecla **"x"** y haga clic en "Administrador de dispositivos") y asegúrese de que el dispositivo se enumera correctamente como HoloLens de Microsoft como se muestra en las siguientes imágenes.</span><span class="sxs-lookup"><span data-stu-id="26fc2-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="26fc2-137">Formatear el dispositivo</span><span class="sxs-lookup"><span data-stu-id="26fc2-137">Clean reflash the device</span></span>

<span data-ttu-id="26fc2-138">En situaciones extraordinarias se le puede pedir que formatee el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="26fc2-139">Hay dos formas de formatear un dispositivo HoloLens2.</span><span class="sxs-lookup"><span data-stu-id="26fc2-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="26fc2-140">Para todos los procedimientos de formateo se le pedirá que[instale la aplicación Advanced Recovery Companion de la Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="26fc2-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="26fc2-141">Si restablece el dispositivo, se borrarán todos sus datos personales, aplicaciones y configuraciones, incluido el restablecimiento del TPM.</span><span class="sxs-lookup"><span data-stu-id="26fc2-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="26fc2-142">Advanced Recovery Companion está actualmente programado para descargar la versión de la función para[Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), si desea descargar la última HoloLens 2 FFU para formatear su dispositivo a través de Advanced Recovery Companion, puede descargarla desde[aquí](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="26fc2-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="26fc2-143">Esto se mantiene actualizado y coincidirá con la última construcción generalmente disponible.</span><span class="sxs-lookup"><span data-stu-id="26fc2-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="26fc2-144">Antes de iniciar el procedimiento de flasheo, asegúrese de que la aplicación esté instalada y funcionando en su PC con Windows 10 y que esté lista para detectar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![Formateo de HoloLens 2](images/ARC1.png)

### <span data-ttu-id="26fc2-146">Procedimiento normal</span><span class="sxs-lookup"><span data-stu-id="26fc2-146">Normal procedure</span></span>

1. <span data-ttu-id="26fc2-147">Mientras el dispositivo HoloLens está funcionando, conéctelo a su PC con Windows 10 donde previamente inició la aplicación Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="26fc2-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="26fc2-148">El dispositivo se detectará automáticamente y la interfaz de la aplicación Advanced Recovery Companion se actualizará de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="26fc2-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![Formateo de HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="26fc2-150">Seleccione el dispositivo HoloLens2 en la interfaz de la aplicación Advanced Recovery Companion y siga las instrucciones para completar el flasheo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="26fc2-151">Procedimiento manual</span><span class="sxs-lookup"><span data-stu-id="26fc2-151">Manual procedure</span></span>

<span data-ttu-id="26fc2-152">Si el dispositivo no inicia correctamente, es posible que tenga que poner el dispositivo HoloLens 2 en modo de recuperación.</span><span class="sxs-lookup"><span data-stu-id="26fc2-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="26fc2-153">Desconecte el dispositivo de la fuente de alimentación o del equipo host desenchufando el cable de tipo C.</span><span class="sxs-lookup"><span data-stu-id="26fc2-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="26fc2-154">Mantenga pulsado el **botón de encendido** durante 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="26fc2-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="26fc2-155">Todos los LEDs deberían apagarse.</span><span class="sxs-lookup"><span data-stu-id="26fc2-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="26fc2-156">Mientras se pulsa el botón de**subir el volumen**, pulse y suelte el**botón de encendido** para encender el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="26fc2-157">Espere 15 segundos antes de soltar el botón de subir el volumen.</span><span class="sxs-lookup"><span data-stu-id="26fc2-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="26fc2-158">De los 5 LEDs del dispositivo, sólo se encenderá el LED del medio.</span><span class="sxs-lookup"><span data-stu-id="26fc2-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="26fc2-159">Conecte el dispositivo al equipo host, abra el Administrador de dispositivos (para Windows 10 pulse la tecla **"Windows"** y luego la tecla **"x"** y haga clic en "Administrador de dispositivos") y asegúrese de que el dispositivo se enumera correctamente como HoloLente de Microsoft como se muestra en la imagen de abajo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="26fc2-161">El dispositivo se detectará automáticamente y la interfaz de la aplicación Advanced Recovery Companion se actualizará de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="26fc2-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![Formateo de HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="26fc2-163">Seleccione el dispositivo HoloLens 2 en la interfaz de la aplicación Advanced Recovery Companion y siga las instrucciones para completar el flasheo.</span><span class="sxs-lookup"><span data-stu-id="26fc2-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="26fc2-164">Descargar ARC sin usar la tienda de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="26fc2-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="26fc2-165">Si un entorno de TI impide el uso de la aplicación Windows Store o limita el acceso a la tienda minorista, los administradores de TI pueden hacer que esta aplicación esté disponible a través de otras vías de despliegue "fuera de línea".</span><span class="sxs-lookup"><span data-stu-id="26fc2-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="26fc2-166">Este proceso también puede utilizarse para otras aplicaciones, como se ha visto en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="26fc2-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="26fc2-167">Esta guía se centrará en Advanced Recovery Companion, pero puede ser modificada para otras aplicaciones fuera de línea.</span><span class="sxs-lookup"><span data-stu-id="26fc2-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="26fc2-168">Esta ruta de despliegue puede habilitarse con los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="26fc2-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="26fc2-169">Diríjase al [sitio web de la tienda para empresas](https://businessstore.microsoft.com)e inicie sesión con una identidad de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26fc2-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="26fc2-170">Diríjase a **Administrar - Configuración**, y active **Mostrar aplicaciones fuera de línea** en**Experiencia de compra**como se describe enhttps://businessstore.microsoft.com/manage/settings/shop</span><span class="sxs-lookup"><span data-stu-id="26fc2-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="26fc2-171">Diríjase a la**tienda de mi grupo**y busque la aplicación[Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="26fc2-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="26fc2-172">Cambie el cuadro de **Tipo de licencia**a fuera de línea y haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="26fc2-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="26fc2-173">En Descargar el paquete para uso fuera de línea, haga clic en el segundo botón azul **"Descargar"**.</span><span class="sxs-lookup"><span data-stu-id="26fc2-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="26fc2-174">Asegúrese de que la extensión del archivo sea .appxbundle.</span><span class="sxs-lookup"><span data-stu-id="26fc2-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="26fc2-175">En esta etapa, si la PC de escritorio tiene acceso a Internet, simplemente haga doble clic e instale.</span><span class="sxs-lookup"><span data-stu-id="26fc2-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="26fc2-176">El administrador de TI también puede distribuir esta aplicación a través de System Center Configuration Manager (SCCM) o Intune.</span><span class="sxs-lookup"><span data-stu-id="26fc2-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="26fc2-177">Si el ordenador objetivo no tiene conexión a Internet, se necesitan algunos pasos adicionales:</span><span class="sxs-lookup"><span data-stu-id="26fc2-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="26fc2-178">Seleccione la licencia no codificada y haga clic en **"Generar licencia"** y en **"Marcos necesarios"** haga clic en **"Descargar."** </span><span class="sxs-lookup"><span data-stu-id="26fc2-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="26fc2-179">Los ordenadores sin acceso a Internet tendrán que usar DISM para aplicar el paquete con la dependencia y la licencia.</span><span class="sxs-lookup"><span data-stu-id="26fc2-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="26fc2-180">En un símbolo de comando de administrador, escriba:</span><span class="sxs-lookup"><span data-stu-id="26fc2-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="26fc2-181">El número de versión en este ejemplo de código puede no coincidir con la versión disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="26fc2-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="26fc2-182">También puede haber elegido una ubicación de descarga diferente a la del ejemplo dado.</span><span class="sxs-lookup"><span data-stu-id="26fc2-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="26fc2-183">Asegúrese de hacer los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="26fc2-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="26fc2-184">Cuando se planea usar Advanced Recovery Companion para instalar un ffu fuera de línea puede ser útil descargar su imagen intermitente para estar disponible, aquí está la[imagen actual para HoloLens 2](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="26fc2-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="26fc2-185">Otros recursos:</span><span class="sxs-lookup"><span data-stu-id="26fc2-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


