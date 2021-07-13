---
title: HoloLens Cifrado de BitLocker
description: Obtenga información sobre cómo habilitar el cifrado de dispositivos BitLocker para proteger los archivos almacenados en HoloLens de realidad mixta.
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
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635252"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="93acb-103">Cifrado de BitLocker para HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="93acb-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="93acb-104">HoloLens (1.ª generación) y HoloLens 2 admiten el cifrado de dispositivos mediante BitLocker; sin embargo, BitLocker siempre está habilitado en HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="93acb-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="93acb-105">Este artículo le ayudará a habilitar y administrar BitLocker en HoloLens (1.ª generación).</span><span class="sxs-lookup"><span data-stu-id="93acb-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="93acb-106">En HoloLens (1.ª generación) puede habilitar el cifrado de dispositivos BitLocker manualmente o mediante la administración de dispositivos móviles (MDM).</span><span class="sxs-lookup"><span data-stu-id="93acb-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="93acb-107">Siga estas instrucciones para habilitar el cifrado [de dispositivos BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger los archivos y la información almacenada en el HoloLens.</span><span class="sxs-lookup"><span data-stu-id="93acb-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="93acb-108">El cifrado de dispositivos ayuda a proteger los datos mediante el método de cifrado AES-CBC 128, que es equivalente al método [EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) en el proveedor de servicios de configuración (CSP) de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="93acb-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="93acb-109">El personal que tiene la clave de cifrado correcta (por ejemplo, una contraseña) puede descifrarla o realizar una recuperación de datos.</span><span class="sxs-lookup"><span data-stu-id="93acb-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="93acb-110">Habilitación del cifrado de dispositivos mediante MDM</span><span class="sxs-lookup"><span data-stu-id="93acb-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="93acb-111">Puede usar el proveedor de Administración de dispositivos móviles (MDM) para aplicar una directiva que requiera cifrado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="93acb-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="93acb-112">La directiva que se va a usar [es la configuración Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) en el CSP de directiva.</span><span class="sxs-lookup"><span data-stu-id="93acb-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="93acb-113">Consulte las instrucciones para habilitar el cifrado de dispositivos mediante Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="93acb-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="93acb-114">Para otras herramientas de MDM, consulte la documentación del proveedor de MDM para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="93acb-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="93acb-115">Si el proveedor de MDM requiere un URI personalizado para el cifrado de dispositivos, use la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="93acb-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="93acb-116">**Nombre:** nombre de su elección</span><span class="sxs-lookup"><span data-stu-id="93acb-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="93acb-117">**Descripción:** opcional</span><span class="sxs-lookup"><span data-stu-id="93acb-117">**Description**: optional</span></span>
- <span data-ttu-id="93acb-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="93acb-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="93acb-119">**Tipo de datos**: entero</span><span class="sxs-lookup"><span data-stu-id="93acb-119">**Data type**: integer</span></span>
- <span data-ttu-id="93acb-120">**Valor**: `1`</span><span class="sxs-lookup"><span data-stu-id="93acb-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="93acb-121">Habilitación del cifrado de dispositivos mediante un paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="93acb-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="93acb-122">Los paquetes de aprovisionamiento son archivos creados por la Windows diseñador de configuración que aplican una configuración especificada a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="93acb-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="93acb-123">Creación de un paquete de aprovisionamiento que actualice la Windows holographic edition y habilita el cifrado</span><span class="sxs-lookup"><span data-stu-id="93acb-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="93acb-124">Crea un paquete de aprovisionamiento para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="93acb-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="93acb-125">Vaya a **Configuración del entorno de ejecución**  >  **Directivas**  >  **seguridad** y **seleccione RequerirDispositivoEncryption.**</span><span class="sxs-lookup"><span data-stu-id="93acb-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Requerir configuración de cifrado de dispositivo configurada en Sí](images/device-encryption.png)

1. <span data-ttu-id="93acb-127">Busque el archivo de licencia XML que se proporcionó al adquirir el conjunto de aplicaciones comerciales.</span><span class="sxs-lookup"><span data-stu-id="93acb-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="93acb-128">Busca y selecciona el archivo de licencia XML que se te proporcionara al adquirir la Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="93acb-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="93acb-129">Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="93acb-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="93acb-130">En el menú **Archivo**, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="93acb-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="93acb-131">Lea la advertencia que explica que los archivos de proyecto pueden contener información confidencial y haga clic **en Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="93acb-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="93acb-132">Al compilar un paquete de aprovisionamiento, puede incluir información confidencial en los archivos de proyecto y el archivo de paquete de aprovisionamiento (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="93acb-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="93acb-133">Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran.</span><span class="sxs-lookup"><span data-stu-id="93acb-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="93acb-134">Debe almacenar los archivos del proyecto en una ubicación segura y eliminar los archivos del proyecto cuando ya no los necesite.</span><span class="sxs-lookup"><span data-stu-id="93acb-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="93acb-135">En el menú **Exportar**, haz clic en **Paquete de aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="93acb-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="93acb-136">Cambie **Propietario a** **Administrador** de TI, que establecerá la prioridad de este paquete de aprovisionamiento mayor que los paquetes de aprovisionamiento aplicados a este dispositivo desde otros orígenes y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="93acb-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="93acb-137">Establece un valor para **Versión del paquete**.</span><span class="sxs-lookup"><span data-stu-id="93acb-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="93acb-138">Puedes realizar cambios en los paquetes existentes y modificar el número de versión para actualizar los paquetes aplicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="93acb-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="93acb-139">En **Selecciona los detalles de seguridad del paquete de aprovisionamiento**, haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93acb-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="93acb-140">Haz clic en **Siguiente** para especificar la ubicación de salida donde quieras ubicar el paquete de aprovisionamiento una vez compilado.</span><span class="sxs-lookup"><span data-stu-id="93acb-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="93acb-141">De forma predeterminada, Windows ICD usa la carpeta de proyecto como ubicación de salida.</span><span class="sxs-lookup"><span data-stu-id="93acb-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="93acb-142">También puedes hacer clic en Examinar para cambiar la ubicación de salida predeterminada.</span><span class="sxs-lookup"><span data-stu-id="93acb-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="93acb-143">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="93acb-143">Click **Next**.</span></span>
1. <span data-ttu-id="93acb-144">Haz clic en **Compilar** para comenzar a compilar el paquete.</span><span class="sxs-lookup"><span data-stu-id="93acb-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="93acb-145">La información del proyecto se muestra en la página de compilación y la barra de progreso indica el estado de la compilación.</span><span class="sxs-lookup"><span data-stu-id="93acb-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="93acb-146">Cuando la compilación se haya completado, haz clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="93acb-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="93acb-147">Aplicación del paquete de aprovisionamiento a HoloLens</span><span class="sxs-lookup"><span data-stu-id="93acb-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="93acb-148">Conectar el dispositivo a través de USB a un equipo e  inicie el dispositivo, pero no continúe más allá de la página de ajuste de la experiencia de configuración inicial (la primera página con el cuadro azul).</span><span class="sxs-lookup"><span data-stu-id="93acb-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="93acb-149">Presiona brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.</span><span class="sxs-lookup"><span data-stu-id="93acb-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="93acb-150">HoloLens aparecerá como un dispositivo en el Explorador de archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="93acb-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="93acb-151">En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="93acb-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="93acb-152">En la página de **ajuste**, presiona otra vez brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.</span><span class="sxs-lookup"><span data-stu-id="93acb-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="93acb-153">El dispositivo te preguntará si el paquete es de confianza y si quieres aplicarlo.</span><span class="sxs-lookup"><span data-stu-id="93acb-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="93acb-154">Confirma que el paquete es de confianza.</span><span class="sxs-lookup"><span data-stu-id="93acb-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="93acb-155">Verás si el paquete se ha aplicado correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="93acb-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="93acb-156">Si se ha producido un error, puedes arreglar el paquete y volver a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="93acb-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="93acb-157">Si se ha hecho correctamente, continúe con la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="93acb-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="93acb-158">Si el dispositivo se compró antes de agosto de 2016, deberá iniciar sesión en el dispositivo con una cuenta Microsoft, obtener la actualización más reciente del sistema operativo y, a continuación, restablecer el sistema operativo para aplicar el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="93acb-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="93acb-159">Comprobación del cifrado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="93acb-159">Verify device encryption</span></span>

<span data-ttu-id="93acb-160">El cifrado es silencioso en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="93acb-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="93acb-161">Para comprobar el estado de cifrado del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="93acb-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="93acb-162">En HoloLens, vaya **a** Configuración  >  **Sistema**  >  **acerca de**.</span><span class="sxs-lookup"><span data-stu-id="93acb-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="93acb-163">**BitLocker** está **habilitado si** el dispositivo está cifrado.</span><span class="sxs-lookup"><span data-stu-id="93acb-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Acerca de la pantalla que muestra BitLocker habilitado](images/about-encryption.png)
