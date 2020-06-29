---
title: Desbloquear las funciones de Windows Holographic for Business
description: Al actualizar a Windows Holographic para la empresa, HoloLens ofrece características adicionales diseñadas para empresas.
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829621"
---
# <span data-ttu-id="c2744-103">Desbloquear las funciones de Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="c2744-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2744-104">Esta página solo se aplica a HoloLens 1 ª gen.</span><span class="sxs-lookup"><span data-stu-id="c2744-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="c2744-105">Microsoft HoloLens está disponible en la *edición de desarrollo*, que ejecuta Windows Holographic (una edición de Windows 10 diseñada para HoloLens), y en el [conjunto comercial](hololens-commercial-features.md), que ofrece características adicionales diseñadas para empresas.</span><span class="sxs-lookup"><span data-stu-id="c2744-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="c2744-106">Si adquieres la Commercial Suite, recibirás una licencia que actualizará Windows Holographic a Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="c2744-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="c2744-107">Puede aplicar esta licencia al dispositivo con el [proveedor de administración de dispositivos móviles (MDM)](#edition-upgrade-by-using-mdm) o un [paquete de aprovisionamiento](#edition-upgrade-by-using-a-provisioning-package)de la organización.</span><span class="sxs-lookup"><span data-stu-id="c2744-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="c2744-108">En Windows 10, versión 1803, puede comprobar que HoloLens se ha actualizado a la edición para empresas seleccionando sistema de **configuración**  >  **System**.</span><span class="sxs-lookup"><span data-stu-id="c2744-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="c2744-109">Actualización de edición mediante MDM</span><span class="sxs-lookup"><span data-stu-id="c2744-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="c2744-110">La licencia de empresa se puede aplicar mediante cualquier proveedor de MDM que admita el [proveedor de servicios de configuración (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) (en inglés).</span><span class="sxs-lookup"><span data-stu-id="c2744-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="c2744-111">La versión más reciente de la API de MDM de Microsoft será compatible con el CSP WindowsLicensing.</span><span class="sxs-lookup"><span data-stu-id="c2744-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="c2744-112">Para obtener instrucciones paso a paso para actualizar HoloLens con Microsoft Intune, consulte [actualizar dispositivos que ejecutan Windows Holographic a Windows Holographic para empresas](https://docs.microsoft.com/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="c2744-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="c2744-113">En otros proveedores de MDM, los pasos específicos para configurar e implementar la directiva pueden variar.</span><span class="sxs-lookup"><span data-stu-id="c2744-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="c2744-114">Actualización de edición mediante un paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="c2744-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="c2744-115">Los paquetes de aprovisionamiento son archivos creados por la herramienta Diseñador de configuraciones de Windows que aplican una configuración especificada a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2744-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="c2744-116">Creación de un paquete de aprovisionamiento que actualice la edición de Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="c2744-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="c2744-117">Crea un paquete de aprovisionamiento para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c2744-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="c2744-118">Ve a **Configuración de tiempo de ejecución** > **EditionUpgrade**y selecciona **EditionUpgradeWithLicense**.</span><span class="sxs-lookup"><span data-stu-id="c2744-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Actualización de la edición con la configuración de la licencia seleccionada](images/icd1.png)

1. <span data-ttu-id="c2744-120">Busque el archivo de licencia XML que se proporcionó cuando compró el conjunto comercial.</span><span class="sxs-lookup"><span data-stu-id="c2744-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2744-121">Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="c2744-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="c2744-122">En el menú **archivo** , seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c2744-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="c2744-123">Lea la advertencia de que los archivos de proyecto pueden contener información confidencial y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c2744-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c2744-124">Al crear un paquete de aprovisionamiento, puede incluir información confidencial en el archivo de archivos de proyecto y en el archivo de paquete de aprovisionamiento (. ppkg).</span><span class="sxs-lookup"><span data-stu-id="c2744-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="c2744-125">Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran.</span><span class="sxs-lookup"><span data-stu-id="c2744-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="c2744-126">Debe almacenar los archivos de proyecto en una ubicación segura y eliminar los archivos de proyecto cuando ya no los necesite.</span><span class="sxs-lookup"><span data-stu-id="c2744-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="c2744-127">En el menú **Exportar**, selecciona **Paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="c2744-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="c2744-128">Cambie el **propietario** a **Administrador de ti**, que establece la prioridad de este paquete de aprovisionamiento para que sea superior a la de otros usuarios que se aplican a este dispositivo desde diferentes orígenes y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2744-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="c2744-129">Establece un valor para **Versión del paquete**.</span><span class="sxs-lookup"><span data-stu-id="c2744-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c2744-130">Puedes realizar cambios en los paquetes existentes y cambiar el número de versión para actualizar los paquetes aplicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c2744-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="c2744-131">En **seleccionar detalles de seguridad para el paquete de aprovisionamiento**, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2744-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="c2744-132">Seleccione **siguiente** para especificar la ubicación de salida donde quiere que aparezca el paquete de aprovisionamiento una vez que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="c2744-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="c2744-133">De forma predeterminada, Windows ICD usa la carpeta de proyecto como la ubicación de salida.</span><span class="sxs-lookup"><span data-stu-id="c2744-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="c2744-134">De manera opcional, puede seleccionar **examinar** para cambiar la ubicación de salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c2744-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="c2744-135">Selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2744-135">Select **Next**.</span></span>

1. <span data-ttu-id="c2744-136">Seleccione **compilación** para empezar a crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="c2744-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="c2744-137">En la página compilación se muestra la información del proyecto y la barra de progreso indica el estado de la compilación.</span><span class="sxs-lookup"><span data-stu-id="c2744-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="c2744-138">Una vez completada la compilación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c2744-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="c2744-139">Aplicación del paquete de aprovisionamiento a HoloLens</span><span class="sxs-lookup"><span data-stu-id="c2744-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="c2744-140">Con el cable USB, conecte el dispositivo a un PC.</span><span class="sxs-lookup"><span data-stu-id="c2744-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="c2744-141">Inicie el dispositivo, pero no continúe después de la página **ajustar** de la experiencia de configuración inicial (la primera página con el cuadro azul).</span><span class="sxs-lookup"><span data-stu-id="c2744-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="c2744-142">En el equipo, HoloLens se muestra como un dispositivo en el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="c2744-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2744-143">Si el dispositivo HoloLens ejecuta Windows 10, versión 1607 o anterior, abre el explorador de archivos presionando y soltando el **volumen** y los botones de **encendido** y apagado de forma simultánea en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2744-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="c2744-144">En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2744-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="c2744-145">Mientras HoloLens esté en la página **ajustar** , pulse brevemente y suelte los botones de **encendido** y **apagado** de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="c2744-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="c2744-146">HoloLens te pregunta si confías en el paquete y deseas aplicarlo.</span><span class="sxs-lookup"><span data-stu-id="c2744-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="c2744-147">Confirma que el paquete es de confianza.</span><span class="sxs-lookup"><span data-stu-id="c2744-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="c2744-148">Verás si el paquete se ha aplicado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c2744-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="c2744-149">Si no se aplicó correctamente, puedes corregir el paquete e intentarlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c2744-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="c2744-150">Si es correcto, continúe con la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2744-150">If successful, proceed with device setup.</span></span>
