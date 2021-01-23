---
title: Cómo realizar una instalación de prueba de la carga e instalación de aplicaciones a través del Instalador de aplicación de HoloLens 2
description: Aprende a instalar y solucionar problemas de aplicaciones con el instalador de la aplicación y a cargar e instalar aplicaciones a través de la interfaz de usuario.
keywords: administración de aplicaciones, aplicación, hololens, instalador de aplicación
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: af4e222a4f83ab82466a383099897986ddf6b8c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297295"
---
# <span data-ttu-id="039d8-104">Instalar aplicaciones en HoloLens 2 mediante el Instalador de aplicación</span><span class="sxs-lookup"><span data-stu-id="039d8-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="039d8-105">Esta característica estaba disponible en [Windows Holographic, versión 20H2 – Actualización de diciembre de 2020](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="039d8-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="039d8-106">Asegúrate de que el dispositivo [esté actualizado](hololens-update-hololens.md) para usar esta característica.</span><span class="sxs-lookup"><span data-stu-id="039d8-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="039d8-107">Hemos agregado **una nueva funcionalidad (Instalador** de aplicación) para permitirle instalar aplicaciones de forma más sencilla en sus dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="039d8-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="039d8-108">La característica estará en **modo predeterminado para dispositivos no administrados.**</span><span class="sxs-lookup"><span data-stu-id="039d8-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="039d8-109">Para evitar interrupciones en las empresas, el instalador de aplicación no **estará disponible para dispositivos administrados** en este momento.</span><span class="sxs-lookup"><span data-stu-id="039d8-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="039d8-110">Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="039d8-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="039d8-111">MDM [inscrito](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="039d8-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="039d8-112">Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="039d8-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="039d8-113">Identidad [de usuario](hololens-identity.md) es Azure AD</span><span class="sxs-lookup"><span data-stu-id="039d8-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="039d8-114">Ahora puedes instalar aplicaciones sin necesidad de habilitar el modo de desarrollador o usar Device Portal.</span><span class="sxs-lookup"><span data-stu-id="039d8-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="039d8-115">Descarga (a través de USB o a través de Microsoft Edge) la agrupación Appx en el dispositivo y navega a la agrupación Appx en el Explorador de archivos para que se te pida que arranques la instalación.</span><span class="sxs-lookup"><span data-stu-id="039d8-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="039d8-116">Como alternativa, [inicie una instalación desde una página web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="039d8-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="039d8-117">Al igual que las aplicaciones que instalas desde Microsoft Store o la instalación de instalación local [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) con la [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) funcionalidad de implementación de la aplicación LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la Herramienta de firma y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="039d8-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="039d8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="039d8-118">Requirements</span></span>

### <span data-ttu-id="039d8-119">Para los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="039d8-119">For your devices:</span></span>

<span data-ttu-id="039d8-120">Esta característica está disponible actualmente en compilaciones de Windows Holographic 20H2 para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="039d8-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="039d8-121">Asegúrese de que todos los dispositivos que usan este método se [actualizan.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="039d8-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="039d8-122">Para las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="039d8-122">For your apps:</span></span>

<span data-ttu-id="039d8-123">La configuración de la solución de la aplicación debe ser **Principal** o **Versión,** ya que el Instalador de aplicación usará dependencias de la tienda.</span><span class="sxs-lookup"><span data-stu-id="039d8-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="039d8-124">Consulta más sobre cómo [crear paquetes de aplicaciones.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="039d8-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="039d8-125">Las aplicaciones que se instalan a través de este método deben estar firmadas digitalmente.</span><span class="sxs-lookup"><span data-stu-id="039d8-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="039d8-126">Tendrás que usar un certificado para firmar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="039d8-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="039d8-127">Puede obtener un certificado de la lista de CA de confianza de [MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)en cuyo caso no tendrá que realizar ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="039d8-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="039d8-128">O bien, puedes firmar tu propio certificado, pero ese certificado tendrá que insertarse en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="039d8-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="039d8-129">Cómo firmar aplicaciones [con la Herramienta de inicio de sesión.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="039d8-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="039d8-130">Opciones de certificado:</span><span class="sxs-lookup"><span data-stu-id="039d8-130">Certificate options:</span></span>**

- [<span data-ttu-id="039d8-131">Lista de CA de confianza de MS</span><span class="sxs-lookup"><span data-stu-id="039d8-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="039d8-132">Elige un método de implementación de certificados.</span><span class="sxs-lookup"><span data-stu-id="039d8-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="039d8-133">[Los paquetes de](hololens-provisioning.md) aprovisionamiento se pueden aplicar a dispositivos locales.</span><span class="sxs-lookup"><span data-stu-id="039d8-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="039d8-134">MDM puede usarse para [aplicar certificados con configuraciones de dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="039d8-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="039d8-135">Usa el Administrador de certificados [en el dispositivo.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="039d8-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="039d8-136">Método de instalación</span><span class="sxs-lookup"><span data-stu-id="039d8-136">Installation method</span></span>

1. <span data-ttu-id="039d8-137">Comprueba que el dispositivo no se considera administrado.</span><span class="sxs-lookup"><span data-stu-id="039d8-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="039d8-138">Comprueba que el dispositivo HoloLens 2 esté encendido y que has iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="039d8-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="039d8-139">En el equipo, ve a la aplicación personalizada y copia tuapp.appxbundle en tudevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="039d8-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="039d8-140">Cuando termines de copiar el archivo, puedes desconectar el dispositivo y finalizar la instalación más adelante.</span><span class="sxs-lookup"><span data-stu-id="039d8-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="039d8-141">En el dispositivo HoloLens 2, abra el **menú Inicio,** seleccione Todas las **aplicaciones** e inicie la aplicación **Explorador de** archivos.</span><span class="sxs-lookup"><span data-stu-id="039d8-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="039d8-142">Vaya a la carpeta Descargas.</span><span class="sxs-lookup"><span data-stu-id="039d8-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="039d8-143">Es posible que deba seleccionar primero \*\*\*\* este dispositivo en el panel izquierdo de la aplicación y, a continuación, ir a Descargas.</span><span class="sxs-lookup"><span data-stu-id="039d8-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="039d8-144">Selecciona el archivo yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="039d8-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="039d8-145">Se iniciará el Instalador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="039d8-145">The App Installer will launch.</span></span> <span data-ttu-id="039d8-146">Selecciona el **botón** Instalar para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="039d8-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="039d8-147">La aplicación instalada se iniciará automáticamente al finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="039d8-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalación de ejemplos de MRTK a través del Instalador de aplicación](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="039d8-149">Solución de problemas de las instalaciones</span><span class="sxs-lookup"><span data-stu-id="039d8-149">Troubleshooting Installs</span></span>

<span data-ttu-id="039d8-150">Si la aplicación no se pudo instalar, comprueba lo siguiente para solucionar problemas:</span><span class="sxs-lookup"><span data-stu-id="039d8-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="039d8-151">La aplicación es una compilación principal o de versión.</span><span class="sxs-lookup"><span data-stu-id="039d8-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="039d8-152">El dispositivo se actualiza a una compilación en la que esta característica está disponible.</span><span class="sxs-lookup"><span data-stu-id="039d8-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="039d8-153">Está conectado [a Internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="039d8-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="039d8-154">Los [puntos de conexión de Microsoft Store](hololens-offline.md) están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="039d8-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="039d8-155">Instalador web</span><span class="sxs-lookup"><span data-stu-id="039d8-155">Web Installer</span></span>

<span data-ttu-id="039d8-156">Los usuarios pueden instalar una aplicación directamente desde un servidor web.</span><span class="sxs-lookup"><span data-stu-id="039d8-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="039d8-157">Este flujo usa el Instalador de aplicación combinado con un método de distribución fácil de descargar e instalar.</span><span class="sxs-lookup"><span data-stu-id="039d8-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="039d8-158">Cómo configurar la instalación web:</span><span class="sxs-lookup"><span data-stu-id="039d8-158">How to set up web install:</span></span>

1. <span data-ttu-id="039d8-159">Asegúrate de que la aplicación esté configurada correctamente para instalarse.</span><span class="sxs-lookup"><span data-stu-id="039d8-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="039d8-160">Siga estos [pasos para habilitar la instalación desde una página web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="039d8-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="039d8-161">Experiencia del usuario final:</span><span class="sxs-lookup"><span data-stu-id="039d8-161">End user experience:</span></span>

1. <span data-ttu-id="039d8-162">El usuario recibe e instala el certificado en el dispositivo mediante un método previamente elegido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="039d8-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="039d8-163">El usuario visita la dirección URL creada a partir del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="039d8-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="039d8-164">La aplicación se instalará ahora en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="039d8-164">The app will now install to the device.</span></span> <span data-ttu-id="039d8-165">Para encontrar la aplicación, abre el **menú Inicio** y selecciona **el** botón Todas las aplicaciones para encontrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="039d8-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="039d8-166">Para obtener más ayuda con la solución de problemas del método de instalación del instalador de aplicaciones, visita [solucionar problemas del instalador de la aplicación.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="039d8-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="039d8-167">No se admite la interfaz de usuario durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="039d8-167">UI during the update process is not supported.</span></span> <span data-ttu-id="039d8-168">Por lo tanto, la opción ShowPrompt de [esta página y](https://docs.microsoft.com/windows/msix/app-installer/update-settings) las opciones relacionadas no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="039d8-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="039d8-169">Aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="039d8-169">Sample Apps</span></span>

<span data-ttu-id="039d8-170">Para probar el Instalador de aplicación con algunas aplicaciones de ejemplo, echa un vistazo a algunos de nuestros ejemplos disponibles:</span><span class="sxs-lookup"><span data-stu-id="039d8-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="039d8-171">Centro de ejemplos de MRTK</span><span class="sxs-lookup"><span data-stu-id="039d8-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="039d8-172">Superficies</span><span class="sxs-lookup"><span data-stu-id="039d8-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="039d8-173">Aplicaciones de muestra para UWP que se pueden usar para pruebas</span><span class="sxs-lookup"><span data-stu-id="039d8-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
