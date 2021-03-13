---
title: 'Escenarios comunes: HoloLens 2 seguro sin conexión'
description: Aprende a configurar un escenario de implementación segura sin conexión e implementación de aplicaciones con aprovisionamiento para dispositivos HoloLens.
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
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407602"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="3b8b3-104">Escenarios comunes: HoloLens 2 seguro sin conexión</span><span class="sxs-lookup"><span data-stu-id="3b8b3-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="3b8b3-105">Información general</span><span class="sxs-lookup"><span data-stu-id="3b8b3-105">Overview</span></span>

<span data-ttu-id="3b8b3-106">Esta guía proporciona instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros con las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="3b8b3-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="3b8b3-107">Deshabilite WiFi.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-107">Disable WiFi.</span></span>
-   <span data-ttu-id="3b8b3-108">Deshabilitar BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="3b8b3-109">Deshabilitar micrófonos.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-109">Disable Microphones.</span></span>
-   <span data-ttu-id="3b8b3-110">Impide agregar o quitar paquetes de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="3b8b3-111">Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="3b8b3-112">Preparar</span><span class="sxs-lookup"><span data-stu-id="3b8b3-112">Prepare</span></span>

<span data-ttu-id="3b8b3-113">Instalación del equipo con Windows 10</span><span class="sxs-lookup"><span data-stu-id="3b8b3-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="3b8b3-114">[Descargue el archivo del sistema operativo HoloLens 2 más](https://aka.ms/hololens2download) reciente directamente en un equipo.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="3b8b3-115">La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="3b8b3-116">Descargar e instalar la herramienta Advanced Recovery Companion(ARC) [de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) en tu PC</span><span class="sxs-lookup"><span data-stu-id="3b8b3-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="3b8b3-117">Descargue o instale la herramienta más reciente del Diseñador de configuraciones [de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) de Microsoft Store en su PC.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="3b8b3-118">[Descargue la OfflineSecureHL2_Sample con los archivos del proyecto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para crear el PPKG.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="3b8b3-119">Preparar la aplicación [línea de negocio sin conexión para la implementación de PPKG](app-deploy-provisioning-package.md).</span><span class="sxs-lookup"><span data-stu-id="3b8b3-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="3b8b3-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="3b8b3-120">Configure</span></span>

<span data-ttu-id="3b8b3-121">Crear un paquete de aprovisionamiento de configuración segura</span><span class="sxs-lookup"><span data-stu-id="3b8b3-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="3b8b3-122">Inicie la herramienta WCD en su PC.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="3b8b3-123">Seleccione **Archivo -> Abrir proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="3b8b3-124">Desplácese hasta la ubicación de la carpeta OfflineSecureHL2_Sample y seleccione: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="3b8b3-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="3b8b3-125">El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles:</span><span class="sxs-lookup"><span data-stu-id="3b8b3-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="3b8b3-127">Configuraciones establecidas en este paquete de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="3b8b3-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="3b8b3-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b8b3-128">Item</span></span>                                                |     <span data-ttu-id="3b8b3-129">Configuración</span><span class="sxs-lookup"><span data-stu-id="3b8b3-129">Setting</span></span>                       |     <span data-ttu-id="3b8b3-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b8b3-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="3b8b3-131">Cuentas /Usuarios</span><span class="sxs-lookup"><span data-stu-id="3b8b3-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="3b8b3-132">Contraseña de nombre de & local</span><span class="sxs-lookup"><span data-stu-id="3b8b3-132">Local User Name & Password</span></span>    |     <span data-ttu-id="3b8b3-133">Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un solo nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="3b8b3-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="3b8b3-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="3b8b3-135">Verdadero</span><span class="sxs-lookup"><span data-stu-id="3b8b3-135">True</span></span>                          |     <span data-ttu-id="3b8b3-136">Omite la calibración solo durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3b8b3-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="3b8b3-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="3b8b3-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="3b8b3-138">Verdadero</span><span class="sxs-lookup"><span data-stu-id="3b8b3-138">True</span></span>                          |     <span data-ttu-id="3b8b3-139">Omite el aprendizaje del dispositivo durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3b8b3-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="3b8b3-140">Primera experiencia / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="3b8b3-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="3b8b3-141">Verdadero</span><span class="sxs-lookup"><span data-stu-id="3b8b3-141">True</span></span>                          |     <span data-ttu-id="3b8b3-142">Omite Wi-Fi configuración durante la configuración inicial del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3b8b3-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="3b8b3-143">Directivas/Conectividad/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="3b8b3-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="3b8b3-144">No</span><span class="sxs-lookup"><span data-stu-id="3b8b3-144">No</span></span>                            |     <span data-ttu-id="3b8b3-145">Deshabilita Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3b8b3-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="3b8b3-146">Directivas/Experiencia/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="3b8b3-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="3b8b3-147">No</span><span class="sxs-lookup"><span data-stu-id="3b8b3-147">No</span></span>                            |     <span data-ttu-id="3b8b3-148">Deshabilita Cortana (para eliminar posibles problemas ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="3b8b3-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="3b8b3-149">Directivas/Realidad mixta/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="3b8b3-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="3b8b3-150">Sí</span><span class="sxs-lookup"><span data-stu-id="3b8b3-150">Yes</span></span>                           |     <span data-ttu-id="3b8b3-151">Deshabilita micrófono</span><span class="sxs-lookup"><span data-stu-id="3b8b3-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="3b8b3-152">Directivas/Privacidad/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="3b8b3-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="3b8b3-153">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="3b8b3-153">Force deny</span></span>                    |     <span data-ttu-id="3b8b3-154">Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas ya que el seguimiento de ubicación está deshabilitado)</span><span class="sxs-lookup"><span data-stu-id="3b8b3-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="3b8b3-155">Directivas/Privacidad/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="3b8b3-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="3b8b3-156">Forzar denegación</span><span class="sxs-lookup"><span data-stu-id="3b8b3-156">Force deny</span></span>                    |     <span data-ttu-id="3b8b3-157">Impide que las aplicaciones intenten acceder a micrófonos (para eliminar posibles problemas ya que los micrófonos están deshabilitados)</span><span class="sxs-lookup"><span data-stu-id="3b8b3-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="3b8b3-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="3b8b3-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="3b8b3-159">No</span><span class="sxs-lookup"><span data-stu-id="3b8b3-159">No</span></span>                            |     <span data-ttu-id="3b8b3-160">Impide que cualquier usuario agregue paquetes de aprovisionamiento que puedan intentar invalidar directivas bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="3b8b3-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="3b8b3-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="3b8b3-162">No</span><span class="sxs-lookup"><span data-stu-id="3b8b3-162">No</span></span>                            |     <span data-ttu-id="3b8b3-163">Impide que alguien quite este paquete de aprovisionamiento bloqueado.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="3b8b3-164">Directivas/Sistema/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="3b8b3-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="3b8b3-165">No</span><span class="sxs-lookup"><span data-stu-id="3b8b3-165">No</span></span>                            |     <span data-ttu-id="3b8b3-166">Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="3b8b3-167">Directivas/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="3b8b3-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="3b8b3-168">No</span><span class="sxs-lookup"><span data-stu-id="3b8b3-168">No</span></span>                            |     <span data-ttu-id="3b8b3-169">Deshabilita Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3b8b3-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="3b8b3-170">En Configuración del tiempo de ejecución, seleccione **Cuentas / Usuarios / UserName: Holo / Password**.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="3b8b3-171">Anote la contraseña y restablezca si lo desea.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="3b8b3-172">Vaya a UniversalAppInstall / UserContextApp y configure la aplicación [lob](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="3b8b3-174">Una vez completado, selecciona el botón "Exportar" y sigue todos los mensajes hasta que se cree el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="3b8b3-176">Implementar</span><span class="sxs-lookup"><span data-stu-id="3b8b3-176">Deploy</span></span>

1. <span data-ttu-id="3b8b3-177">Conecta el HL2 a tu PC con Windows 10 a través de un cable USB.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="3b8b3-178">Iniciar la herramienta ARC y seleccionar **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="3b8b3-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Pantalla inicial de la reprogramación de HoloLens 2](images/ARC2.png)

1. <span data-ttu-id="3b8b3-180">En la siguiente pantalla, seleccione **Selección manual del paquete**.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-180">On the next screen select **Manual package selection**.</span></span>

   ![Pantalla de información de HOLOLens 2 ARC](images/arc_device_info.png)

1. <span data-ttu-id="3b8b3-182">Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="3b8b3-183">En la página Advertencia, **seleccione Continuar**.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-183">At the Warning page select **Continue**.</span></span>

   ![Pantalla de advertencia de HOLOLens 2 ARC](images/arc_warning.png)

1. <span data-ttu-id="3b8b3-185">Espere a que la herramienta ARC complete la instalación del sistema operativo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="3b8b3-186">Una vez que el dispositivo complete la instalación y se inicie la copia de seguridad, desde el equipo vaya al Explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Archivo PPKG en pc en la ventana Explorador de archivos.](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="3b8b3-188">En HoloLens 2, presione el siguiente botón combinado para ejecutar el paquete de aprovisionamiento: **pulse** Bajar volumen y Botón de **encendido** al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="3b8b3-189">Se le pedirá que aplique el paquete de aprovisionamiento, seleccione **Confirmar**</span><span class="sxs-lookup"><span data-stu-id="3b8b3-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="3b8b3-190">Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="3b8b3-191">A continuación, se te pedirá que inicies sesión en el dispositivo con la cuenta local compartida y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="3b8b3-192">Mantener</span><span class="sxs-lookup"><span data-stu-id="3b8b3-192">Maintain</span></span>

<span data-ttu-id="3b8b3-193">Con esta configuración, se recomienda reiniciar el proceso anterior y reflash el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización del sistema operativo y/o las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b8b3-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
