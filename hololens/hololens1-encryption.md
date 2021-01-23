---
title: Cifrado de BitLocker de HoloLens
description: Aprende a habilitar el cifrado de dispositivos bitlocker para proteger los archivos almacenados en los dispositivos de realidad mixta de HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 268c3650b85e7e7f102618ccc5a94c25de54dcfe
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284031"
---
# <span data-ttu-id="b1087-103">Cifrado de BitLocker (1º exgen) para HoloLens</span><span class="sxs-lookup"><span data-stu-id="b1087-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="b1087-104">HoloLens (1.ª generación) y HoloLens 2 admiten el cifrado de dispositivos con BitLocker; sin embargo, BitLocker siempre está habilitado en HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b1087-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="b1087-105">Este artículo te ayudará a habilitar y administrar BitLocker en HoloLens (1.ª generación).</span><span class="sxs-lookup"><span data-stu-id="b1087-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="b1087-106">En HoloLens (1.ª generación) puedes habilitar el cifrado de dispositivos BitLocker manualmente o mediante la administración de dispositivos móviles (MDM).</span><span class="sxs-lookup"><span data-stu-id="b1087-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="b1087-107">Sigue estas instrucciones para habilitar el cifrado [de dispositivos BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger los archivos y la información almacenada en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b1087-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="b1087-108">El cifrado de dispositivos ayuda a proteger los datos mediante el método de cifrado AES-CBC 128, que es equivalente al método [EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) en el proveedor de servicios de configuración (CSP) de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="b1087-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="b1087-109">El personal que tiene la clave de cifrado correcta (como una contraseña) puede descifrarla o realizar una recuperación de datos.</span><span class="sxs-lookup"><span data-stu-id="b1087-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <span data-ttu-id="b1087-110">Habilitar el cifrado de dispositivos con MDM</span><span class="sxs-lookup"><span data-stu-id="b1087-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="b1087-111">Puedes usar el proveedor de administración de dispositivos móviles (MDM) para aplicar una directiva que requiera cifrado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b1087-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="b1087-112">La directiva que se va a usar [es la configuración Seguridad/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) en el CSP de directivas.</span><span class="sxs-lookup"><span data-stu-id="b1087-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="b1087-113">Consulta las instrucciones para habilitar el cifrado de dispositivos con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b1087-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="b1087-114">Para otras herramientas MDM, consulta la documentación de tu proveedor MDM para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b1087-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="b1087-115">Si el proveedor de MDM requiere un URI personalizado para el cifrado de dispositivos, usa la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="b1087-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="b1087-116">**Nombre**: el nombre que elijas</span><span class="sxs-lookup"><span data-stu-id="b1087-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="b1087-117">**Descripción**: opcional</span><span class="sxs-lookup"><span data-stu-id="b1087-117">**Description**: optional</span></span>
- <span data-ttu-id="b1087-118">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="b1087-118">**OMA-URI**:</span></span> `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- <span data-ttu-id="b1087-119">**Tipo de datos**: enteros</span><span class="sxs-lookup"><span data-stu-id="b1087-119">**Data type**: integer</span></span>
- <span data-ttu-id="b1087-120">**Valor**:</span><span class="sxs-lookup"><span data-stu-id="b1087-120">**Value**:</span></span> `1`

## <span data-ttu-id="b1087-121">Habilitar el cifrado de dispositivo mediante un paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="b1087-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="b1087-122">Los paquetes de aprovisionamiento son archivos creados por la herramienta Diseñador de configuraciones de Windows que aplican una configuración especificada a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b1087-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <span data-ttu-id="b1087-123">Crear un paquete de aprovisionamiento que actualice la edición Holográfica de Windows y permita el cifrado</span><span class="sxs-lookup"><span data-stu-id="b1087-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="b1087-124">Crea un paquete de aprovisionamiento para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b1087-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="b1087-125">Ve a **Configuración de tiempo de ejecución** > **Directivas** > **Seguridad** y selecciona **RequireDeviceEncryption**.</span><span class="sxs-lookup"><span data-stu-id="b1087-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Requerir el establecimiento de la configuración de cifrado de dispositivo en sí](images/device-encryption.png)

1. <span data-ttu-id="b1087-127">Busque el archivo de licencia XML que se proporcionó al adquirir commercial suite.</span><span class="sxs-lookup"><span data-stu-id="b1087-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="b1087-128">Busca y selecciona el archivo de licencia XML que se te proporcionara al adquirir la Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="b1087-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b1087-129">Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="b1087-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="b1087-130">En el menú **Archivo**, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b1087-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="b1087-131">Lea la advertencia que explica que los archivos del proyecto pueden contener información confidencial y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="b1087-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b1087-132">Al compilar un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos del proyecto y el archivo de paquete de aprovisionamiento (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="b1087-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="b1087-133">Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran.</span><span class="sxs-lookup"><span data-stu-id="b1087-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="b1087-134">Debe almacenar los archivos del proyecto en una ubicación segura y eliminar los archivos del proyecto cuando ya no sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b1087-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="b1087-135">En el menú **Exportar**, haz clic en **Paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="b1087-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="b1087-136">Cambia el **Propietario** a **Administrador de TI** para establecer una prioridad para este paquete de aprovisionamiento superior a la de los paquetes de aprovisionamiento aplicados a este dispositivo desde otros orígenes y, a continuación, selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b1087-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="b1087-137">Establece un valor para **Versión del paquete**.</span><span class="sxs-lookup"><span data-stu-id="b1087-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="b1087-138">Puedes realizar cambios en los paquetes existentes y modificar el número de versión para actualizar los paquetes aplicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b1087-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="b1087-139">En **Selecciona los detalles de seguridad del paquete de aprovisionamiento**, haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b1087-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="b1087-140">Haz clic en **Siguiente** para especificar la ubicación de salida donde quieras ubicar el paquete de aprovisionamiento una vez compilado.</span><span class="sxs-lookup"><span data-stu-id="b1087-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="b1087-141">De forma predeterminada, Windows ICD usa la carpeta de proyecto como la ubicación de salida.</span><span class="sxs-lookup"><span data-stu-id="b1087-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="b1087-142">También puedes hacer clic en Examinar para cambiar la ubicación de salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b1087-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="b1087-143">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b1087-143">Click **Next**.</span></span>
1. <span data-ttu-id="b1087-144">Haz clic en **Compilar** para comenzar a compilar el paquete.</span><span class="sxs-lookup"><span data-stu-id="b1087-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="b1087-145">La información del proyecto se muestra en la página de compilación y la barra de progreso indica el estado de la compilación.</span><span class="sxs-lookup"><span data-stu-id="b1087-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="b1087-146">Cuando la compilación se haya completado, haz clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b1087-146">When the build completes, click **Finish**.</span></span>

### <span data-ttu-id="b1087-147">Aplicación del paquete de aprovisionamiento a HoloLens</span><span class="sxs-lookup"><span data-stu-id="b1087-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="b1087-148">Conecta el dispositivo mediante USB a un equipo e inícialo, pero no pases de la página de **ajuste** de la experiencia de configuración inicial (la primera página con el cuadro azul).</span><span class="sxs-lookup"><span data-stu-id="b1087-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="b1087-149">Presiona brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.</span><span class="sxs-lookup"><span data-stu-id="b1087-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="b1087-150">HoloLens aparecerá como un dispositivo en el Explorador de archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="b1087-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="b1087-151">En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b1087-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="b1087-152">En la página de **ajuste**, presiona otra vez brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.</span><span class="sxs-lookup"><span data-stu-id="b1087-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="b1087-153">El dispositivo te preguntará si el paquete es de confianza y si quieres aplicarlo.</span><span class="sxs-lookup"><span data-stu-id="b1087-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="b1087-154">Confirma que el paquete es de confianza.</span><span class="sxs-lookup"><span data-stu-id="b1087-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="b1087-155">Verás si el paquete se ha aplicado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="b1087-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="b1087-156">Si se ha producido un error, puedes arreglar el paquete y volver a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="b1087-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="b1087-157">Si se ha aplicado correctamente, continúa con la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b1087-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="b1087-158">Si el dispositivo se ha adquirido antes de agosto de 2016, deberás iniciar sesión en el dispositivo con una cuenta de Microsoft, obtener la última actualización del sistema operativo y luego restablecer dicho sistema operativo para aplicar el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="b1087-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <span data-ttu-id="b1087-159">Verificar el cifrado de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b1087-159">Verify device encryption</span></span>

<span data-ttu-id="b1087-160">El cifrado es silencioso en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b1087-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="b1087-161">Para verificar el estado de cifrado del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b1087-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="b1087-162">En HoloLens, ve a **Configuración** > **Sistema** > **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="b1087-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="b1087-163">**BitLocker** está **habilitado si** el dispositivo está cifrado.</span><span class="sxs-lookup"><span data-stu-id="b1087-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Acerca de la pantalla que muestra BitLocker habilitado](images/about-encryption.png)
