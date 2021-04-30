---
title: Desbloqueo de Windows Holographic for Business características
description: Al actualizar a Windows Holographic for Business, HoloLens proporciona características adicionales diseñadas para empresas.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310156"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="0ec3c-103">Desbloqueo de Windows Holographic for Business características</span><span class="sxs-lookup"><span data-stu-id="0ec3c-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ec3c-104">Esta página solo se aplica a HoloLens 1st Gen.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="0ec3c-105">Microsoft HoloLens está disponible en *development Edition,* que ejecuta Windows Holographic (una edición de Windows 10 diseñada para HoloLens) y en [Commercial Suite](hololens-commercial-features.md), que proporciona características adicionales diseñadas para empresas.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="0ec3c-106">Al comprar Commercial Suite, recibirá una licencia que actualiza Windows Holographic a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="0ec3c-107">Puede aplicar esta licencia al dispositivo mediante el proveedor de administración de dispositivos móviles [(MDM)](#edition-upgrade-by-using-mdm) de la organización o un paquete [de aprovisionamiento](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="0ec3c-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="0ec3c-108">En Windows 10, versión 1803, puede comprobar que HoloLens se ha actualizado a la edición business seleccionando Settings  >  System (Sistema de **configuración).**</span><span class="sxs-lookup"><span data-stu-id="0ec3c-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="0ec3c-109">Actualización de edición mediante MDM</span><span class="sxs-lookup"><span data-stu-id="0ec3c-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="0ec3c-110">La licencia de empresa se puede aplicar mediante cualquier proveedor de MDM que admita el [proveedor de servicios de configuración (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) (en inglés).</span><span class="sxs-lookup"><span data-stu-id="0ec3c-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="0ec3c-111">La versión más reciente de la API de MDM de Microsoft será compatible con el CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="0ec3c-112">Para obtener instrucciones paso a paso para actualizar HoloLens mediante Microsoft Intune, consulte Actualización de dispositivos que ejecutan [Windows Holographic a Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="0ec3c-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="0ec3c-113">En otros proveedores de MDM, los pasos específicos para configurar e implementar la directiva pueden variar.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="0ec3c-114">Actualización de edición mediante un paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="0ec3c-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="0ec3c-115">Los paquetes de aprovisionamiento son archivos creados por la herramienta Diseñador de configuración de Windows que aplican una configuración especificada a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="0ec3c-116">Creación de un paquete de aprovisionamiento que actualice la edición de Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="0ec3c-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="0ec3c-117">Crea un paquete de aprovisionamiento para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="0ec3c-118">Vaya a **Configuración del entorno de ejecución**  >  **EdiciónActulta** y seleccione **EdiciónUpgradeWithLicense.**</span><span class="sxs-lookup"><span data-stu-id="0ec3c-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Actualización de la edición con la configuración de la licencia seleccionada](images/icd1.png)

1. <span data-ttu-id="0ec3c-120">Busque el archivo de licencia XML que se proporcionó al adquirir el conjunto de aplicaciones comerciales.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ec3c-121">Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="0ec3c-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="0ec3c-122">En el menú **Archivo**, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="0ec3c-123">Lea la advertencia de que los archivos de proyecto pueden contener información confidencial y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="0ec3c-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0ec3c-124">Al compilar un paquete de aprovisionamiento, puede incluir información confidencial en los archivos de proyecto y el archivo de paquete de aprovisionamiento (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="0ec3c-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="0ec3c-125">Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="0ec3c-126">Debe almacenar los archivos del proyecto en una ubicación segura y eliminar los archivos del proyecto cuando ya no los necesite.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="0ec3c-127">En el menú **Exportar**, selecciona **Paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="0ec3c-128">Cambie **Propietario a** **Administrador** de TI, que establece la prioridad de este paquete de aprovisionamiento para que sea mayor que otras aplicadas a este dispositivo desde orígenes diferentes y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="0ec3c-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="0ec3c-129">Establece un valor para **Versión del paquete**.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0ec3c-130">Puedes realizar cambios en los paquetes existentes y modificar el número de versión para actualizar los paquetes aplicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="0ec3c-131">En **Seleccionar detalles de seguridad para el paquete de aprovisionamiento,** seleccione **Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="0ec3c-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="0ec3c-132">Seleccione **Siguiente** para especificar la ubicación de salida a la que desea que vaya el paquete de aprovisionamiento una vez que se haya creado.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="0ec3c-133">De forma predeterminada, Windows ICD usa la carpeta de proyecto como ubicación de salida.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="0ec3c-134">Opcionalmente, puede seleccionar Examinar **para** cambiar la ubicación de salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="0ec3c-135">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-135">Select **Next**.</span></span>

1. <span data-ttu-id="0ec3c-136">Seleccione **Compilar** para empezar a compilar el paquete.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="0ec3c-137">La página de compilación muestra la información del proyecto y la barra de progreso indica el estado de compilación.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="0ec3c-138">Cuando se complete la compilación, seleccione **Finalizar.**</span><span class="sxs-lookup"><span data-stu-id="0ec3c-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="0ec3c-139">Aplicación del paquete de aprovisionamiento a HoloLens</span><span class="sxs-lookup"><span data-stu-id="0ec3c-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="0ec3c-140">Con el cable USB, conecte el dispositivo a un equipo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="0ec3c-141">Inicie el dispositivo, pero no continúe más allá de la **página** de ajuste de la experiencia de configuración inicial (la primera página con el cuadro azul).</span><span class="sxs-lookup"><span data-stu-id="0ec3c-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="0ec3c-142">En el equipo, HoloLens se muestra como un dispositivo en Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0ec3c-143">Si el dispositivo HoloLens ejecuta Windows 10, versión 1607 o anterior, abra Explorador de archivos presionando brevemente  y  liberando los botones Bajar volumen y Encendido simultáneamente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="0ec3c-144">En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="0ec3c-145">Mientras HoloLens sigue en la **página** de ajuste, presione  brevemente y suelte los botones **Bajar** volumen y Encendido simultáneamente de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="0ec3c-146">HoloLens le pregunta si confía en el paquete y le gustaría aplicarlo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="0ec3c-147">Confirma que el paquete es de confianza.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="0ec3c-148">Verás si el paquete se ha aplicado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="0ec3c-149">Si no se aplicó correctamente, puede corregir el paquete e intentarlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="0ec3c-150">Si se realiza correctamente, continúe con la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ec3c-150">If successful, proceed with device setup.</span></span>
