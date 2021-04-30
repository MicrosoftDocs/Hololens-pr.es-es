---
title: 'Escenarios comunes: seguridad sin conexión HoloLens 2'
description: Aprenda a configurar un escenario de implementación segura sin conexión y de implementación de aplicaciones con aprovisionamiento para dispositivos HoloLens.
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309128"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="849c0-104">Escenarios comunes: seguridad sin conexión HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="849c0-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="849c0-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="849c0-105">Overview</span></span>

<span data-ttu-id="849c0-106">En esta guía se proporcionan instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros con las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="849c0-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="849c0-107">Deshabilite wi-fi.</span><span class="sxs-lookup"><span data-stu-id="849c0-107">Disable WiFi.</span></span>
-   <span data-ttu-id="849c0-108">Deshabilite BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="849c0-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="849c0-109">Deshabilite micrófonos.</span><span class="sxs-lookup"><span data-stu-id="849c0-109">Disable Microphones.</span></span>
-   <span data-ttu-id="849c0-110">Impide agregar o quitar paquetes de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="849c0-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="849c0-111">Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.</span><span class="sxs-lookup"><span data-stu-id="849c0-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="849c0-112">Preparación</span><span class="sxs-lookup"><span data-stu-id="849c0-112">Prepare</span></span>

<span data-ttu-id="849c0-113">Windows 10 configuración de PC</span><span class="sxs-lookup"><span data-stu-id="849c0-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="849c0-114">[Descargue el archivo HoloLens 2 sistema operativo más](https://aka.ms/hololens2download) reciente directamente en un equipo.</span><span class="sxs-lookup"><span data-stu-id="849c0-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="849c0-115">La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="849c0-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="849c0-116">Descargar o instalar la herramienta Advanced Recovery Companion(ARC) [desde el Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al equipo</span><span class="sxs-lookup"><span data-stu-id="849c0-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="849c0-117">Descargue o instale la herramienta [del Diseñador de configuración de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) más reciente Microsoft Store en el equipo.</span><span class="sxs-lookup"><span data-stu-id="849c0-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="849c0-118">[Descargue la OfflineSecureHL2_Sample con los archivos del proyecto para](https://aka.ms/HoloLensDocs-SecureOfflineSample) compilar el PPKG.</span><span class="sxs-lookup"><span data-stu-id="849c0-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="849c0-119">Prepare la aplicación [de línea de negocio sin conexión para la implementación de PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="849c0-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="849c0-120">Configuración</span><span class="sxs-lookup"><span data-stu-id="849c0-120">Configure</span></span>

<span data-ttu-id="849c0-121">Compilación de un paquete de aprovisionamiento de configuración segura</span><span class="sxs-lookup"><span data-stu-id="849c0-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="849c0-122">Inicie la herramienta WCD en el equipo.</span><span class="sxs-lookup"><span data-stu-id="849c0-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="849c0-123">Seleccione **Archivo -> Abrir proyecto**.</span><span class="sxs-lookup"><span data-stu-id="849c0-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="849c0-124">Vaya a la ubicación de la carpeta guardada OfflineSecureHL2_Sample y seleccione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="849c0-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="849c0-125">El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="849c0-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849c0-126">![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="849c0-126">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="849c0-127">Configuraciones establecidas en este paquete de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="849c0-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="849c0-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="849c0-128">Item</span></span>                                                |     <span data-ttu-id="849c0-129">Parámetro</span><span class="sxs-lookup"><span data-stu-id="849c0-129">Setting</span></span>                       |     <span data-ttu-id="849c0-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="849c0-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="849c0-131">Cuentas y usuarios</span><span class="sxs-lookup"><span data-stu-id="849c0-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="849c0-132">Nombre de usuario local & contraseña</span><span class="sxs-lookup"><span data-stu-id="849c0-132">Local User Name & Password</span></span>    |     <span data-ttu-id="849c0-133">Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un único nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="849c0-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="849c0-134">Primera experiencia/HoloLens/Skip Holobration</span><span class="sxs-lookup"><span data-stu-id="849c0-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="849c0-135">Verdadero</span><span class="sxs-lookup"><span data-stu-id="849c0-135">True</span></span>                          |     <span data-ttu-id="849c0-136">Omite la calibración solo durante la configuración inicial del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="849c0-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="849c0-137">Primera experiencia/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="849c0-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="849c0-138">Verdadero</span><span class="sxs-lookup"><span data-stu-id="849c0-138">True</span></span>                          |     <span data-ttu-id="849c0-139">Omite el entrenamiento del dispositivo durante la configuración inicial del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="849c0-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="849c0-140">Primera experiencia/HoloLens/Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="849c0-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="849c0-141">Verdadero</span><span class="sxs-lookup"><span data-stu-id="849c0-141">True</span></span>                          |     <span data-ttu-id="849c0-142">Omite la Wi-Fi durante la configuración inicial del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="849c0-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="849c0-143">Directivas/Conectividad/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="849c0-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="849c0-144">No</span><span class="sxs-lookup"><span data-stu-id="849c0-144">No</span></span>                            |     <span data-ttu-id="849c0-145">Deshabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="849c0-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="849c0-146">Directivas/Experiencia/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="849c0-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="849c0-147">No</span><span class="sxs-lookup"><span data-stu-id="849c0-147">No</span></span>                            |     <span data-ttu-id="849c0-148">Deshabilita Cortana (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="849c0-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="849c0-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="849c0-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="849c0-150">Yes</span><span class="sxs-lookup"><span data-stu-id="849c0-150">Yes</span></span>                           |     <span data-ttu-id="849c0-151">Deshabilita el micrófono</span><span class="sxs-lookup"><span data-stu-id="849c0-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="849c0-152">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="849c0-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="849c0-153">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="849c0-153">Force deny</span></span>                    |     <span data-ttu-id="849c0-154">Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas, ya que el seguimiento de ubicación está deshabilitado)</span><span class="sxs-lookup"><span data-stu-id="849c0-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="849c0-155">Directivas/Privacidad/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="849c0-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="849c0-156">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="849c0-156">Force deny</span></span>                    |     <span data-ttu-id="849c0-157">Impide que las aplicaciones intenten acceder a los micrófonos (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="849c0-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="849c0-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="849c0-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="849c0-159">No</span><span class="sxs-lookup"><span data-stu-id="849c0-159">No</span></span>                            |     <span data-ttu-id="849c0-160">Impide que alguien agregue paquetes de aprovisionamiento que puedan intentar invalidar las directivas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="849c0-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="849c0-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="849c0-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="849c0-162">No</span><span class="sxs-lookup"><span data-stu-id="849c0-162">No</span></span>                            |     <span data-ttu-id="849c0-163">Impide que alguien quite este paquete de aprovisionamiento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="849c0-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="849c0-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="849c0-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="849c0-165">No</span><span class="sxs-lookup"><span data-stu-id="849c0-165">No</span></span>                            |     <span data-ttu-id="849c0-166">Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="849c0-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="849c0-167">Directivas/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="849c0-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="849c0-168">No</span><span class="sxs-lookup"><span data-stu-id="849c0-168">No</span></span>                            |     <span data-ttu-id="849c0-169">Deshabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="849c0-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="849c0-170">En Configuración del entorno de ejecución, **seleccione Cuentas/Usuarios/NombreDeUsuario: Holo/Contraseña.**</span><span class="sxs-lookup"><span data-stu-id="849c0-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="849c0-171">Anote la contraseña y restablezca si lo desea.</span><span class="sxs-lookup"><span data-stu-id="849c0-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="849c0-172">Vaya a UniversalAppInstall /UserContextApp y configure la aplicación [LOB](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="849c0-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849c0-173">![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="849c0-173">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="849c0-174">Una vez completado, seleccione el botón "Exportar" y siga todas las indicaciones hasta que se cree el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="849c0-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849c0-175">![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="849c0-175">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="849c0-176">Implementar</span><span class="sxs-lookup"><span data-stu-id="849c0-176">Deploy</span></span>

1. <span data-ttu-id="849c0-177">Conecte hl2 al equipo Windows 10 a través de un cable USB.</span><span class="sxs-lookup"><span data-stu-id="849c0-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="849c0-178">Inicie la herramienta ARC y seleccione **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="849c0-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 pantalla inicial de reflash limpia](images/ARC2.png)

1. <span data-ttu-id="849c0-180">En la siguiente pantalla, seleccione **Selección manual del paquete.**</span><span class="sxs-lookup"><span data-stu-id="849c0-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 de información de ARC](images/arc_device_info.png)

1. <span data-ttu-id="849c0-182">Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="849c0-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="849c0-183">En la página Advertencia, seleccione **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="849c0-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 de advertencia de ARC](images/arc_warning.png)

1. <span data-ttu-id="849c0-185">Espere a que la herramienta ARC complete la instalación HoloLens 2 sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="849c0-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="849c0-186">Una vez que el dispositivo complete la instalación y arranque la copia de seguridad, desde el equipo vaya a Explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="849c0-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="849c0-187">![Archivo PPKG en pc en Explorador de archivos ventana.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="849c0-187">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="849c0-188">En la HoloLens 2, presione el siguiente botón combinado para ejecutar el paquete de aprovisionamiento: **Pulse** Bajar volumen y **Botón** de encendido al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="849c0-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="849c0-189">Se le pedirá que aplique el paquete de aprovisionamiento y seleccione **Confirmar.**</span><span class="sxs-lookup"><span data-stu-id="849c0-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="849c0-190">Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="849c0-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="849c0-191">A continuación, se le pedirá que inicie sesión en el dispositivo con la cuenta local y la contraseña compartidas.</span><span class="sxs-lookup"><span data-stu-id="849c0-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="849c0-192">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="849c0-192">Maintain</span></span>

<span data-ttu-id="849c0-193">Con esta configuración, se recomienda reiniciar el proceso anterior y volver a actualizar el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización del sistema operativo o las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="849c0-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
