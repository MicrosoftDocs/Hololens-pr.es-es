---
title: 'Escenarios comunes: HoloLens con conexión segura 2'
description: Implementación segura y de aplicaciones sin conexión a través del aprovisionamiento.
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080538"
---
# <span data-ttu-id="490e7-104">Escenarios comunes: HoloLens con conexión segura 2</span><span class="sxs-lookup"><span data-stu-id="490e7-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="490e7-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="490e7-105">Overview</span></span>
<span data-ttu-id="490e7-106">Esta guía proporciona una guía para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará una HoloLens 2 para su uso en entornos seguros con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="490e7-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="490e7-107">Deshabilitar WiFi.</span><span class="sxs-lookup"><span data-stu-id="490e7-107">Disable WiFi.</span></span>
-   <span data-ttu-id="490e7-108">Deshabilitar BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="490e7-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="490e7-109">Deshabilitar micrófonos.</span><span class="sxs-lookup"><span data-stu-id="490e7-109">Disable Microphones.</span></span>
-   <span data-ttu-id="490e7-110">Impide agregar o quitar paquetes de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="490e7-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="490e7-111">Ningún usuario puede habilitar ninguno de los componentes restringidos mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="490e7-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="490e7-112">Preparar</span><span class="sxs-lookup"><span data-stu-id="490e7-112">Prepare</span></span> 
<span data-ttu-id="490e7-113">Configuración de Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="490e7-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="490e7-114">[Descarga el archivo de sistema operativo HoloLens 2 más reciente](https://aka.ms/hololens2download) directamente en tu PC.</span><span class="sxs-lookup"><span data-stu-id="490e7-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="490e7-115">La compatibilidad con esta configuración está incluida en la compilación 19041,1117 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="490e7-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="490e7-116">Descargar e instalar la herramienta de asistente de recuperación avanzada (ARC) [de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) en su PC</span><span class="sxs-lookup"><span data-stu-id="490e7-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="490e7-117">Descargue e instale la herramienta [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) más reciente de Microsoft Store en su PC.</span><span class="sxs-lookup"><span data-stu-id="490e7-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="490e7-118">[Descargue la carpeta OfflineSecureHL2_Sample con los archivos de proyecto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para generar el PPKG.</span><span class="sxs-lookup"><span data-stu-id="490e7-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="490e7-119">Prepare la [aplicación de línea de negocio sin conexión para la implementación de PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="490e7-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="490e7-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="490e7-120">Configure</span></span>
<span data-ttu-id="490e7-121">Crear un paquete de aprovisionamiento de configuración segura</span><span class="sxs-lookup"><span data-stu-id="490e7-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="490e7-122">Inicia la herramienta WCD en tu PC.</span><span class="sxs-lookup"><span data-stu-id="490e7-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="490e7-123">Seleccione **archivo-> abrir proyecto**.</span><span class="sxs-lookup"><span data-stu-id="490e7-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="490e7-124">Vaya a la ubicación de la carpeta OfflineSecureHL2_Sample guardada anteriormente y seleccione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="490e7-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="490e7-125">El proyecto debe abrirse y ahora debe tener una lista de personalizaciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="490e7-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)

<span data-ttu-id="490e7-127">Configuraciones definidas en este paquete de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="490e7-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="490e7-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="490e7-128">Item</span></span>                                                |     <span data-ttu-id="490e7-129">Configuración</span><span class="sxs-lookup"><span data-stu-id="490e7-129">Setting</span></span>                       |     <span data-ttu-id="490e7-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="490e7-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="490e7-131">Cuentas/usuarios</span><span class="sxs-lookup"><span data-stu-id="490e7-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="490e7-132">Nombre de usuario local & contraseña</span><span class="sxs-lookup"><span data-stu-id="490e7-132">Local User Name & Password</span></span>    |     <span data-ttu-id="490e7-133">Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un solo nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="490e7-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="490e7-134">Primera experiencia/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="490e7-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="490e7-135">Verdadero</span><span class="sxs-lookup"><span data-stu-id="490e7-135">True</span></span>                          |     <span data-ttu-id="490e7-136">Omite la calibración durante la configuración del dispositivo inicial solamente</span><span class="sxs-lookup"><span data-stu-id="490e7-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="490e7-137">Primera experiencia/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="490e7-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="490e7-138">Verdadero</span><span class="sxs-lookup"><span data-stu-id="490e7-138">True</span></span>                          |     <span data-ttu-id="490e7-139">Omite la formación de dispositivos durante la configuración del dispositivo inicial</span><span class="sxs-lookup"><span data-stu-id="490e7-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="490e7-140">Primera experiencia/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="490e7-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="490e7-141">Verdadero</span><span class="sxs-lookup"><span data-stu-id="490e7-141">True</span></span>                          |     <span data-ttu-id="490e7-142">Omite la configuración de Wi-Fi durante la configuración del dispositivo inicial</span><span class="sxs-lookup"><span data-stu-id="490e7-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="490e7-143">Directivas/conectividad/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="490e7-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="490e7-144">No</span><span class="sxs-lookup"><span data-stu-id="490e7-144">No</span></span>                            |     <span data-ttu-id="490e7-145">Deshabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="490e7-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="490e7-146">Directivas/experiencia/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="490e7-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="490e7-147">No</span><span class="sxs-lookup"><span data-stu-id="490e7-147">No</span></span>                            |     <span data-ttu-id="490e7-148">Deshabilita Cortana (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="490e7-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="490e7-149">Directivas/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="490e7-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="490e7-150">Sí</span><span class="sxs-lookup"><span data-stu-id="490e7-150">Yes</span></span>                           |     <span data-ttu-id="490e7-151">Deshabilita el micrófono</span><span class="sxs-lookup"><span data-stu-id="490e7-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="490e7-152">Directivas/privacidad/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="490e7-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="490e7-153">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="490e7-153">Force deny</span></span>                    |     <span data-ttu-id="490e7-154">Impide que las aplicaciones intenten obtener acceso a los datos de la ubicación (para eliminar posibles problemas porque el seguimiento de ubicación está deshabilitado)</span><span class="sxs-lookup"><span data-stu-id="490e7-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="490e7-155">Directivas/privacidad/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="490e7-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="490e7-156">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="490e7-156">Force deny</span></span>                    |     <span data-ttu-id="490e7-157">Impide que las aplicaciones intenten acceder a micrófonos (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="490e7-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="490e7-158">Directivas/seguridad/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="490e7-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="490e7-159">No</span><span class="sxs-lookup"><span data-stu-id="490e7-159">No</span></span>                            |     <span data-ttu-id="490e7-160">Impide que cualquier persona agregue paquetes de aprovisionamiento que puedan intentar suplantar las directivas de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="490e7-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="490e7-161">Directivas/seguridad/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="490e7-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="490e7-162">No</span><span class="sxs-lookup"><span data-stu-id="490e7-162">No</span></span>                            |     <span data-ttu-id="490e7-163">Impide que cualquier persona quite este paquete de aprovisionamiento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="490e7-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="490e7-164">Directivas/sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="490e7-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="490e7-165">No</span><span class="sxs-lookup"><span data-stu-id="490e7-165">No</span></span>                            |     <span data-ttu-id="490e7-166">Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="490e7-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="490e7-167">Directivas/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="490e7-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="490e7-168">No</span><span class="sxs-lookup"><span data-stu-id="490e7-168">No</span></span>                            |     <span data-ttu-id="490e7-169">Deshabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="490e7-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="490e7-170">En Runtime Settings, seleccione **accounts/Users/username: holo/password**</span><span class="sxs-lookup"><span data-stu-id="490e7-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="490e7-171">Anote la contraseña y reinicie si lo desea.</span><span class="sxs-lookup"><span data-stu-id="490e7-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="490e7-172">Vaya a UniversalAppInstall/UserContextApp y [Configure la aplicación LOB](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="490e7-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="490e7-174">Una vez completado, seleccione el botón "exportar" y siga todas las indicaciones hasta que se cree el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="490e7-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="490e7-176">Implementar</span><span class="sxs-lookup"><span data-stu-id="490e7-176">Deploy</span></span>
1. <span data-ttu-id="490e7-177">Conecta el HL2 a tu PC con Windows 10 a través del cable USB.</span><span class="sxs-lookup"><span data-stu-id="490e7-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="490e7-178">Inicia la herramienta ARC y selecciona **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="490e7-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="490e7-179">En la siguiente pantalla, seleccione **selección de paquetes manual**.</span><span class="sxs-lookup"><span data-stu-id="490e7-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="490e7-180">Vaya al archivo. FFU descargado anteriormente y seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="490e7-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="490e7-181">En la página de advertencia, seleccione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="490e7-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="490e7-182">Espera a que la herramienta de arco complete la instalación del sistema operativo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="490e7-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="490e7-183">Una vez que el dispositivo complete la instalación y arranque de nuevo, desde su PC, navegue hasta el explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="490e7-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![PPKG archivo en equipo en la ventana del explorador de archivos.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="490e7-185">En la HoloLens 2, pulse el siguiente cuadro combinado de botones para ejecutar el paquete de aprovisionamiento: Pulse **volumen bajo** y **botón de encendido** al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="490e7-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="490e7-186">Se le pedirá que aplique el paquete de aprovisionamiento, seleccione confirm ( **confirmar** ).</span><span class="sxs-lookup"><span data-stu-id="490e7-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="490e7-187">Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="490e7-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="490e7-188">Se le pedirá que inicie sesión en el dispositivo con la cuenta local y la contraseña compartidas.</span><span class="sxs-lookup"><span data-stu-id="490e7-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="490e7-189">Mantener</span><span class="sxs-lookup"><span data-stu-id="490e7-189">Maintain</span></span>
<span data-ttu-id="490e7-190">Con esta configuración, se recomienda reiniciar el proceso anterior y volver a crear un flash del dispositivo con la herramienta ARC y aplicar una nueva PPKG para hacer actualizaciones en el sistema operativo o en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="490e7-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

