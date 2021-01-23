---
title: 'Escenarios comunes: HoloLens seguro sin conexión 2'
description: Aprende a configurar un escenario de implementación segura sin conexión y de implementación de aplicaciones con aprovisionamiento para dispositivos HoloLens.
keywords: HoloLens, administración, sin conexión, seguro sin conexión
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283421"
---
# <span data-ttu-id="fc93a-104">Escenarios comunes: HoloLens seguro sin conexión 2</span><span class="sxs-lookup"><span data-stu-id="fc93a-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="fc93a-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="fc93a-105">Overview</span></span>

<span data-ttu-id="fc93a-106">En esta guía se proporcionan instrucciones para aplicar un paquete de aprovisionamiento de muestra que bloqueará un HoloLens 2 para su uso en entornos seguros con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="fc93a-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="fc93a-107">Deshabilita wi-fi.</span><span class="sxs-lookup"><span data-stu-id="fc93a-107">Disable WiFi.</span></span>
-   <span data-ttu-id="fc93a-108">Deshabilita BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="fc93a-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="fc93a-109">Deshabilite los micrófonos.</span><span class="sxs-lookup"><span data-stu-id="fc93a-109">Disable Microphones.</span></span>
-   <span data-ttu-id="fc93a-110">Impide agregar o quitar paquetes de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="fc93a-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="fc93a-111">Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.</span><span class="sxs-lookup"><span data-stu-id="fc93a-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="fc93a-112">Preparar</span><span class="sxs-lookup"><span data-stu-id="fc93a-112">Prepare</span></span>

<span data-ttu-id="fc93a-113">Configuración del equipo con Windows 10</span><span class="sxs-lookup"><span data-stu-id="fc93a-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="fc93a-114">[Descarga el archivo del sistema operativo HoloLens 2](https://aka.ms/hololens2download) más reciente directamente en un equipo.</span><span class="sxs-lookup"><span data-stu-id="fc93a-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="fc93a-115">La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="fc93a-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="fc93a-116">Descargar e instalar la herramienta Advanced Recovery Companion(ARC) [de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) en tu PC</span><span class="sxs-lookup"><span data-stu-id="fc93a-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="fc93a-117">Descarga e instala la herramienta más reciente del Diseñador de configuraciones [de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) de Microsoft Store en tu PC.</span><span class="sxs-lookup"><span data-stu-id="fc93a-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="fc93a-118">[Descarga la OfflineSecureHL2_Sample carpeta con los archivos del proyecto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para compilar el PPKG.</span><span class="sxs-lookup"><span data-stu-id="fc93a-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="fc93a-119">Preparar la aplicación [de línea de negocio sin conexión para la implementación de PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="fc93a-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="fc93a-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="fc93a-120">Configure</span></span>

<span data-ttu-id="fc93a-121">Crear un paquete de aprovisionamiento de configuración segura</span><span class="sxs-lookup"><span data-stu-id="fc93a-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="fc93a-122">Inicia la herramienta WCD en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fc93a-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="fc93a-123">Seleccione **Archivo -> Abrir proyecto**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="fc93a-124">Vaya a la ubicación de la carpeta OfflineSecureHL2_Sample guardada anteriormente y seleccione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="fc93a-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="fc93a-125">El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="fc93a-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)

<span data-ttu-id="fc93a-127">Configuraciones establecidas en este paquete de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="fc93a-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="fc93a-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc93a-128">Item</span></span>                                                |     <span data-ttu-id="fc93a-129">Configuración</span><span class="sxs-lookup"><span data-stu-id="fc93a-129">Setting</span></span>                       |     <span data-ttu-id="fc93a-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc93a-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="fc93a-131">Cuentas o usuarios</span><span class="sxs-lookup"><span data-stu-id="fc93a-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="fc93a-132">Nombre de usuario local & contraseña</span><span class="sxs-lookup"><span data-stu-id="fc93a-132">Local User Name & Password</span></span>    |     <span data-ttu-id="fc93a-133">Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un solo nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="fc93a-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="fc93a-134">Primera experiencia / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="fc93a-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="fc93a-135">Verdadero</span><span class="sxs-lookup"><span data-stu-id="fc93a-135">True</span></span>                          |     <span data-ttu-id="fc93a-136">Omite la calibración solo durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fc93a-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="fc93a-137">Primera experiencia / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="fc93a-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="fc93a-138">Verdadero</span><span class="sxs-lookup"><span data-stu-id="fc93a-138">True</span></span>                          |     <span data-ttu-id="fc93a-139">Omite el aprendizaje del dispositivo durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fc93a-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="fc93a-140">Primera experiencia / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="fc93a-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="fc93a-141">Verdadero</span><span class="sxs-lookup"><span data-stu-id="fc93a-141">True</span></span>                          |     <span data-ttu-id="fc93a-142">Omite la configuración Wi-Fi durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fc93a-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="fc93a-143">Directivas/Conectividad/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="fc93a-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="fc93a-144">No</span><span class="sxs-lookup"><span data-stu-id="fc93a-144">No</span></span>                            |     <span data-ttu-id="fc93a-145">Deshabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="fc93a-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="fc93a-146">Directivas/Experiencia/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="fc93a-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="fc93a-147">No</span><span class="sxs-lookup"><span data-stu-id="fc93a-147">No</span></span>                            |     <span data-ttu-id="fc93a-148">Deshabilita Cortana (para eliminar posibles problemas ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="fc93a-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="fc93a-149">Directivas/Realidad mixta/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="fc93a-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="fc93a-150">Sí</span><span class="sxs-lookup"><span data-stu-id="fc93a-150">Yes</span></span>                           |     <span data-ttu-id="fc93a-151">Deshabilita el micrófono</span><span class="sxs-lookup"><span data-stu-id="fc93a-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="fc93a-152">Directivas/Privacidad/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="fc93a-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="fc93a-153">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="fc93a-153">Force deny</span></span>                    |     <span data-ttu-id="fc93a-154">Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas ya que el seguimiento de ubicación está deshabilitado)</span><span class="sxs-lookup"><span data-stu-id="fc93a-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="fc93a-155">Directivas/Privacidad/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="fc93a-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="fc93a-156">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="fc93a-156">Force deny</span></span>                    |     <span data-ttu-id="fc93a-157">Impide que las aplicaciones intenten acceder a los micrófonos (para eliminar posibles problemas ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="fc93a-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="fc93a-158">Directivas/Seguridad/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="fc93a-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="fc93a-159">No</span><span class="sxs-lookup"><span data-stu-id="fc93a-159">No</span></span>                            |     <span data-ttu-id="fc93a-160">Impide que cualquier usuario agregue paquetes de aprovisionamiento que puedan intentar invalidar directivas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="fc93a-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="fc93a-161">Directivas/Seguridad/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="fc93a-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="fc93a-162">No</span><span class="sxs-lookup"><span data-stu-id="fc93a-162">No</span></span>                            |     <span data-ttu-id="fc93a-163">Impide que nadie quite este paquete de aprovisionamiento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="fc93a-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="fc93a-164">Directivas/Sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="fc93a-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="fc93a-165">No</span><span class="sxs-lookup"><span data-stu-id="fc93a-165">No</span></span>                            |     <span data-ttu-id="fc93a-166">Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="fc93a-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="fc93a-167">Directivas/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="fc93a-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="fc93a-168">No</span><span class="sxs-lookup"><span data-stu-id="fc93a-168">No</span></span>                            |     <span data-ttu-id="fc93a-169">Deshabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="fc93a-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="fc93a-170">En Configuración de tiempo de ejecución, seleccione **Cuentas / Usuarios / Nombre de usuario: Holo / Contraseña**</span><span class="sxs-lookup"><span data-stu-id="fc93a-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="fc93a-171">Anote la contraseña y restablezca si lo desea.</span><span class="sxs-lookup"><span data-stu-id="fc93a-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="fc93a-172">Ve a UniversalAppInstall /UserContextApp y configura la aplicación [lob](app-deploy-provisioning-package.md) que vas a implementar en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fc93a-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="fc93a-174">Una vez completado, selecciona el botón "Exportar" y sigue todas las indicaciones hasta que se cree el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="fc93a-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="fc93a-176">Implementar</span><span class="sxs-lookup"><span data-stu-id="fc93a-176">Deploy</span></span>

1. <span data-ttu-id="fc93a-177">Conecta HL2 a tu PC con Windows 10 a través de un cable USB.</span><span class="sxs-lookup"><span data-stu-id="fc93a-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="fc93a-178">Iniciar la herramienta ARC y seleccionar **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="fc93a-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="fc93a-179">En la siguiente pantalla, seleccione **Selección de paquete manual.**</span><span class="sxs-lookup"><span data-stu-id="fc93a-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="fc93a-180">Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="fc93a-181">En la página Advertencia, **seleccione Continuar**.</span><span class="sxs-lookup"><span data-stu-id="fc93a-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="fc93a-182">Espere a que la herramienta ARC complete la instalación del sistema operativo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="fc93a-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="fc93a-183">Una vez que el dispositivo completa la instalación y arranca la copia de seguridad, desde el equipo ve al Explorador de archivos y copia el archivo PPKG guardado anteriormente en la carpeta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc93a-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Archivo PPKG en el equipo en la ventana del Explorador de archivos.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="fc93a-185">En HoloLens 2, presione la combinación de botones \*\*\*\* siguiente para ejecutar el paquete de aprovisionamiento: pulse bajar volumen y botón de **encendido** al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fc93a-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="fc93a-186">Se te pedirá que apliques el paquete de aprovisionamiento, selecciona **Confirmar**</span><span class="sxs-lookup"><span data-stu-id="fc93a-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="fc93a-187">Una vez completado el paquete de aprovisionamiento, selecciona **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="fc93a-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="fc93a-188">A continuación, se te pedirá que inicies sesión en el dispositivo con la cuenta local compartida y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="fc93a-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="fc93a-189">Mantener</span><span class="sxs-lookup"><span data-stu-id="fc93a-189">Maintain</span></span>

<span data-ttu-id="fc93a-190">Con esta configuración, se recomienda reiniciar el proceso anterior y volver a actualizar el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización al sistema operativo o a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fc93a-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

