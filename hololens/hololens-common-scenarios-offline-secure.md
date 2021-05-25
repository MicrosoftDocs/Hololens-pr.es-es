---
title: 'Escenarios comunes: seguridad sin conexión HoloLens 2'
description: Aprenda a configurar un escenario de implementación de aplicaciones y una implementación segura sin conexión con el aprovisionamiento para dispositivos HoloLens.
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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397886"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="cc259-104">Escenarios comunes: seguridad sin conexión HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="cc259-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="cc259-105">Información general</span><span class="sxs-lookup"><span data-stu-id="cc259-105">Overview</span></span>

<span data-ttu-id="cc259-106">En esta guía se proporcionan instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros con las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="cc259-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="cc259-107">Deshabilite Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="cc259-107">Disable WiFi.</span></span>
-   <span data-ttu-id="cc259-108">Deshabilite BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="cc259-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="cc259-109">Deshabilite micrófonos.</span><span class="sxs-lookup"><span data-stu-id="cc259-109">Disable Microphones.</span></span>
-   <span data-ttu-id="cc259-110">Impide agregar o quitar paquetes de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="cc259-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="cc259-111">Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.</span><span class="sxs-lookup"><span data-stu-id="cc259-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="cc259-112">[![Escenario seguro sin conexión ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cc259-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="cc259-113">Preparación</span><span class="sxs-lookup"><span data-stu-id="cc259-113">Prepare</span></span>

<span data-ttu-id="cc259-114">Windows 10 configuración del equipo</span><span class="sxs-lookup"><span data-stu-id="cc259-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="cc259-115">[Descargue el archivo HoloLens 2 sistema operativo más reciente](https://aka.ms/hololens2download) directamente en un equipo.</span><span class="sxs-lookup"><span data-stu-id="cc259-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="cc259-116">La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="cc259-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="cc259-117">Descargue o instale la herramienta Advanced Recovery Companion(ARC) [desde el Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al equipo.</span><span class="sxs-lookup"><span data-stu-id="cc259-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="cc259-118">Descargue o instale la herramienta más reciente del Diseñador de configuración de [Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) Microsoft Store en el equipo.</span><span class="sxs-lookup"><span data-stu-id="cc259-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="cc259-119">[Descargue la OfflineSecureHL2_Sample con los archivos del proyecto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para compilar el archivo PPKG.</span><span class="sxs-lookup"><span data-stu-id="cc259-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="cc259-120">Prepare la aplicación [de línea de negocio sin conexión para la implementación de PPKG.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="cc259-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="cc259-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="cc259-121">Configure</span></span>

<span data-ttu-id="cc259-122">Compilación de un paquete de aprovisionamiento de configuración segura</span><span class="sxs-lookup"><span data-stu-id="cc259-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="cc259-123">Inicie la herramienta WCD en el equipo.</span><span class="sxs-lookup"><span data-stu-id="cc259-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="cc259-124">Seleccione **Archivo -> Abrir proyecto**.</span><span class="sxs-lookup"><span data-stu-id="cc259-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="cc259-125">Vaya a la ubicación de la carpeta de OfflineSecureHL2_Sample guardada anteriormente y seleccione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="cc259-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="cc259-126">El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="cc259-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc259-127">![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="cc259-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="cc259-128">Configuraciones establecidas en este paquete de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="cc259-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="cc259-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc259-129">Item</span></span>                                                |     <span data-ttu-id="cc259-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="cc259-130">Setting</span></span>                       |     <span data-ttu-id="cc259-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc259-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="cc259-132">Cuentas o usuarios</span><span class="sxs-lookup"><span data-stu-id="cc259-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="cc259-133">Nombre de usuario local & contraseña</span><span class="sxs-lookup"><span data-stu-id="cc259-133">Local User Name & Password</span></span>    |     <span data-ttu-id="cc259-134">Para estos dispositivos sin conexión, todos los usuarios del dispositivo deben establecer y compartir un único nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="cc259-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="cc259-135">Primera experiencia/HoloLens/Skip Holobration</span><span class="sxs-lookup"><span data-stu-id="cc259-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="cc259-136">Verdadero</span><span class="sxs-lookup"><span data-stu-id="cc259-136">True</span></span>                          |     <span data-ttu-id="cc259-137">Omite la calibración solo durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc259-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="cc259-138">Primera experiencia/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="cc259-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="cc259-139">Verdadero</span><span class="sxs-lookup"><span data-stu-id="cc259-139">True</span></span>                          |     <span data-ttu-id="cc259-140">Omite el entrenamiento del dispositivo durante la configuración inicial del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc259-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="cc259-141">Primera experiencia/HoloLens/Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cc259-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="cc259-142">Verdadero</span><span class="sxs-lookup"><span data-stu-id="cc259-142">True</span></span>                          |     <span data-ttu-id="cc259-143">Omite la Wi-Fi durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc259-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="cc259-144">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="cc259-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="cc259-145">No</span><span class="sxs-lookup"><span data-stu-id="cc259-145">No</span></span>                            |     <span data-ttu-id="cc259-146">Deshabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="cc259-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="cc259-147">Policies/Experience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="cc259-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="cc259-148">No</span><span class="sxs-lookup"><span data-stu-id="cc259-148">No</span></span>                            |     <span data-ttu-id="cc259-149">Deshabilita Cortana (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="cc259-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="cc259-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="cc259-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="cc259-151">Sí</span><span class="sxs-lookup"><span data-stu-id="cc259-151">Yes</span></span>                           |     <span data-ttu-id="cc259-152">Deshabilita el micrófono</span><span class="sxs-lookup"><span data-stu-id="cc259-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="cc259-153">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="cc259-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="cc259-154">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="cc259-154">Force deny</span></span>                    |     <span data-ttu-id="cc259-155">Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas, ya que el seguimiento de ubicación está deshabilitado)</span><span class="sxs-lookup"><span data-stu-id="cc259-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="cc259-156">Directivas/Privacidad/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="cc259-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="cc259-157">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="cc259-157">Force deny</span></span>                    |     <span data-ttu-id="cc259-158">Impide que las aplicaciones intenten acceder a los micrófonos (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="cc259-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="cc259-159">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="cc259-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="cc259-160">No</span><span class="sxs-lookup"><span data-stu-id="cc259-160">No</span></span>                            |     <span data-ttu-id="cc259-161">Impide que alguien agregue paquetes de aprovisionamiento que puedan intentar invalidar las directivas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="cc259-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="cc259-162">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="cc259-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="cc259-163">No</span><span class="sxs-lookup"><span data-stu-id="cc259-163">No</span></span>                            |     <span data-ttu-id="cc259-164">Impide que alguien quite este paquete de aprovisionamiento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="cc259-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="cc259-165">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="cc259-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="cc259-166">No</span><span class="sxs-lookup"><span data-stu-id="cc259-166">No</span></span>                            |     <span data-ttu-id="cc259-167">Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="cc259-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="cc259-168">Directivas/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="cc259-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="cc259-169">No</span><span class="sxs-lookup"><span data-stu-id="cc259-169">No</span></span>                            |     <span data-ttu-id="cc259-170">Deshabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="cc259-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="cc259-171">En Configuración del entorno de ejecución, **seleccione Cuentas/Usuarios/NombreDeUsuario: Holo/Contraseña.**</span><span class="sxs-lookup"><span data-stu-id="cc259-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="cc259-172">Anote la contraseña y restablezca si lo desea.</span><span class="sxs-lookup"><span data-stu-id="cc259-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="cc259-173">Vaya a UniversalAppInstall /UserContextApp y configure la aplicación [LOB](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cc259-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc259-174">![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="cc259-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="cc259-175">Una vez completado, seleccione el botón "Exportar" y siga todas las indicaciones hasta que se cree el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="cc259-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc259-176">![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="cc259-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="cc259-177">Implementar</span><span class="sxs-lookup"><span data-stu-id="cc259-177">Deploy</span></span>

1. <span data-ttu-id="cc259-178">Conecte hl2 al equipo Windows 10 a través de un cable USB.</span><span class="sxs-lookup"><span data-stu-id="cc259-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="cc259-179">Inicie la herramienta ARC y seleccione **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="cc259-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 pantalla inicial de reflash limpia](images/ARC2.png)

1. <span data-ttu-id="cc259-181">En la siguiente pantalla, seleccione **Selección manual de paquetes.**</span><span class="sxs-lookup"><span data-stu-id="cc259-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 de información de ARC](images/arc_device_info.png)

1. <span data-ttu-id="cc259-183">Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="cc259-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="cc259-184">En la página Advertencia, seleccione **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="cc259-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 de advertencia de ARC](images/arc_warning.png)

1. <span data-ttu-id="cc259-186">Espere a que la herramienta ARC complete la instalación HoloLens 2 sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cc259-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="cc259-187">Una vez que el dispositivo complete la instalación y arranque la copia de seguridad, desde el equipo vaya a Explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc259-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc259-188">![Archivo PPKG en pc en Explorador de archivos ventana.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="cc259-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="cc259-189">En la HoloLens 2, presione el siguiente botón combinado para ejecutar el paquete de aprovisionamiento: **Pulse** Bajar volumen y **Botón** de encendido al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="cc259-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="cc259-190">Se le pedirá que aplique el paquete de aprovisionamiento y seleccione **Confirmar.**</span><span class="sxs-lookup"><span data-stu-id="cc259-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="cc259-191">Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="cc259-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="cc259-192">A continuación, se le pedirá que inicie sesión en el dispositivo con la cuenta local compartida y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="cc259-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="cc259-193">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="cc259-193">Maintain</span></span>

<span data-ttu-id="cc259-194">Con esta configuración, se recomienda reiniciar el proceso anterior y volver a actualizar el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización del sistema operativo o las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cc259-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
