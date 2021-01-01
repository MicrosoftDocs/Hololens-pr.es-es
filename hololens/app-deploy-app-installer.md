---
title: Cómo cargar y instalar aplicaciones a través del instalador de aplicaciones de HoloLens 2
description: Descargar diapositivas e instalar aplicaciones a través de la interfaz de usuario
keywords: App Management, App, hololens, instalador de aplicaciones
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
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253097"
---
# <span data-ttu-id="5b507-104">Instalar aplicaciones en HoloLens 2 a través del instalador de la aplicación</span><span class="sxs-lookup"><span data-stu-id="5b507-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="5b507-105">Estamos **agregando una nueva función (instalador de aplicaciones) para que pueda instalar aplicaciones más fácilmente** en sus dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b507-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="5b507-106">La característica estará **activada de forma predeterminada en los dispositivos no administrados**.</span><span class="sxs-lookup"><span data-stu-id="5b507-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="5b507-107">Para evitar interrupciones en las empresas, el instalador **de aplicaciones no estará disponible para los dispositivos administrados** en este momento.</span><span class="sxs-lookup"><span data-stu-id="5b507-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="5b507-108">Esta característica está disponible en [Windows Holographic, versión 20H2: diciembre de 2020](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="5b507-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="5b507-109">Asegúrese de que el dispositivo está [actualizado](hololens-update-hololens.md) para usar esta característica.</span><span class="sxs-lookup"><span data-stu-id="5b507-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="5b507-110">Hemos **agregado una nueva función (instalador de aplicaciones) que te permite instalar aplicaciones de forma más fluida** en tus dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b507-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="5b507-111">La característica estará **activada de forma predeterminada en los dispositivos no administrados**.</span><span class="sxs-lookup"><span data-stu-id="5b507-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="5b507-112">Para evitar interrupciones en las empresas, el instalador **de aplicaciones no estará disponible para los dispositivos administrados** en este momento.</span><span class="sxs-lookup"><span data-stu-id="5b507-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="5b507-113">Un dispositivo se considera "administrado" si se cumple **alguna** de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5b507-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="5b507-114">MDM [inscrito](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="5b507-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="5b507-115">Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="5b507-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="5b507-116">La [identidad](hololens-identity.md) del usuario es Azure ad</span><span class="sxs-lookup"><span data-stu-id="5b507-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="5b507-117">Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni el uso de Device portal.</span><span class="sxs-lookup"><span data-stu-id="5b507-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="5b507-118">Descarga (a través de USB o a través de Microsoft Edge) el paquete appx en el dispositivo y navega hasta el paquete appx en el explorador de archivos para que se le solicite que inicie la instalación.</span><span class="sxs-lookup"><span data-stu-id="5b507-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="5b507-119">También puede [iniciar una instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="5b507-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="5b507-120">Al igual que las aplicaciones que se instalan desde Microsoft Store o mediante la instalación de prueba con la aplicación LOB de MDM, las aplicaciones tienen que estar firmadas digitalmente con la [herramienta firmar](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) y el [certificado usado para firmar debe ser de confianza para](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) el dispositivo HoloLens antes de que se pueda implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b507-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="5b507-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b507-121">Requirements</span></span>

### <span data-ttu-id="5b507-122">Para los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="5b507-122">For your devices:</span></span>

 <span data-ttu-id="5b507-123">la característica está actualmente disponible en las compilaciones 20H2 de Windows Holographic para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5b507-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="5b507-124">Asegúrese de que se [actualizan](hololens-update-hololens.md)todos los dispositivos que usan este método.</span><span class="sxs-lookup"><span data-stu-id="5b507-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="5b507-125">Para sus aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="5b507-125">For your apps:</span></span> 
<span data-ttu-id="5b507-126">La configuración de la solución de la aplicación debe ser **Master** o **Release** , ya que el instalador de la aplicación usará las dependencias de la tienda.</span><span class="sxs-lookup"><span data-stu-id="5b507-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="5b507-127">Más información sobre cómo [crear paquetes de aplicaciones](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="5b507-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="5b507-128">Las aplicaciones que se instalen a través de este método deben estar firmadas digitalmente.</span><span class="sxs-lookup"><span data-stu-id="5b507-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="5b507-129">Tendrás que usar un certificado para firmar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b507-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="5b507-130">Puede obtener un certificado desde la lista de [CA de confianza de MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), en cuyo caso no tendrá que realizar ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="5b507-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="5b507-131">También puede firmar su propio certificado, sin embargo, el certificado deberá insertarse en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b507-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="5b507-132">Cómo firmar aplicaciones [con la herramienta firmar.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="5b507-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="5b507-133">Opciones de certificado:</span><span class="sxs-lookup"><span data-stu-id="5b507-133">Certificate options:</span></span>**

- [<span data-ttu-id="5b507-134">Lista de CA de confianza de MS</span><span class="sxs-lookup"><span data-stu-id="5b507-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="5b507-135">Elija un método de implementación de certificados.</span><span class="sxs-lookup"><span data-stu-id="5b507-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="5b507-136">Los [paquetes de aprovisionamiento](hololens-provisioning.md) pueden aplicarse a dispositivos locales.</span><span class="sxs-lookup"><span data-stu-id="5b507-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="5b507-137">MDM se puede usar para [aplicar certificados con configuraciones de dispositivos](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="5b507-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="5b507-138">Use el en el [Administrador de certificados](certificate-manager.md)de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b507-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="5b507-139">Método de instalación</span><span class="sxs-lookup"><span data-stu-id="5b507-139">Installation method</span></span>

1. <span data-ttu-id="5b507-140">Compruebe que el dispositivo no se considere administrado.</span><span class="sxs-lookup"><span data-stu-id="5b507-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="5b507-141">Verifica que tu dispositivo HoloLens 2 esté encendido y que hayas iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="5b507-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="5b507-142">En su equipo, navegue hasta la aplicación personalizada y copie SUAPLICACIÓN. appxbundle a yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="5b507-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="5b507-143">Una vez que haya terminado de copiar el archivo, puede desconectar el dispositivo y finalizar la instalación más tarde.</span><span class="sxs-lookup"><span data-stu-id="5b507-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="5b507-144">Desde tu dispositivo HoloLens 2 abre el **menú Inicio**, selecciona **todas las aplicaciones** e inicia la aplicación **Explorador de archivos** .</span><span class="sxs-lookup"><span data-stu-id="5b507-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="5b507-145">Vaya a la carpeta descargas.</span><span class="sxs-lookup"><span data-stu-id="5b507-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="5b507-146">Es posible que tenga que estar en el panel izquierdo de la aplicación, seleccione **este dispositivo** en primer lugar y, a continuación, vaya a descargas.</span><span class="sxs-lookup"><span data-stu-id="5b507-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="5b507-147">Seleccione el archivo SUAPLICACIÓN. appxbundle.</span><span class="sxs-lookup"><span data-stu-id="5b507-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="5b507-148">Se iniciará el instalador de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b507-148">The App Installer will launch.</span></span> <span data-ttu-id="5b507-149">Seleccione el botón **instalar** para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b507-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="5b507-150">La aplicación instalada se iniciará automáticamente al finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="5b507-150">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalación de MRTK ejemplos mediante el instalador de aplicaciones](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="5b507-152">Solución de problemas de instalación</span><span class="sxs-lookup"><span data-stu-id="5b507-152">Troubleshooting Installs</span></span>

<span data-ttu-id="5b507-153">Si la aplicación no se instaló correctamente, compruebe lo siguiente para solucionar el problema:</span><span class="sxs-lookup"><span data-stu-id="5b507-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="5b507-154">Tu aplicación es una compilación de lanzamiento o maestra.</span><span class="sxs-lookup"><span data-stu-id="5b507-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="5b507-155">El dispositivo se actualizará a una compilación en la que está disponible esta característica.</span><span class="sxs-lookup"><span data-stu-id="5b507-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="5b507-156">Estás [conectado a Internet](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="5b507-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="5b507-157">Los [puntos de conexión de Microsoft Store](hololens-offline.md) están correctamente configurados.</span><span class="sxs-lookup"><span data-stu-id="5b507-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="5b507-158">Instalador Web</span><span class="sxs-lookup"><span data-stu-id="5b507-158">Web Installer</span></span>

<span data-ttu-id="5b507-159">Los usuarios pueden instalar una aplicación directamente desde un servidor Web.</span><span class="sxs-lookup"><span data-stu-id="5b507-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="5b507-160">Este flujo usa el instalador de aplicaciones combinado con un método de distribución de fácil descarga e instalación.</span><span class="sxs-lookup"><span data-stu-id="5b507-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="5b507-161">Cómo configurar la instalación en Internet:</span><span class="sxs-lookup"><span data-stu-id="5b507-161">How to set up web install:</span></span>

1. <span data-ttu-id="5b507-162">Asegúrate de que la aplicación esté correctamente configurada para instalarse.</span><span class="sxs-lookup"><span data-stu-id="5b507-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="5b507-163">Siga estos [pasos para habilitar la instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="5b507-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="5b507-164">Experiencia de usuario final:</span><span class="sxs-lookup"><span data-stu-id="5b507-164">End user experience:</span></span>

1. <span data-ttu-id="5b507-165">El usuario recibe e instala el certificado en el dispositivo con un método previamente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5b507-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="5b507-166">El usuario visita la dirección URL creada a partir del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="5b507-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="5b507-167">La aplicación se instalará en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b507-167">The app will now install to the device.</span></span> <span data-ttu-id="5b507-168">Para buscar la aplicación, abra el **menú Inicio** y seleccione el botón **todas las aplicaciones** para buscar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b507-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="5b507-169">Para obtener más ayuda con la solución de problemas del método de instalación del instalador de aplicaciones, visite [solucionar problemas del instalador](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b507-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="5b507-170">No se admite la interfaz de usuario durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="5b507-170">UI during the update process is not supported.</span></span> <span data-ttu-id="5b507-171">Por lo tanto, no se admite la opción ShowPrompt de [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) ni las opciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="5b507-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="5b507-172">Aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b507-172">Sample Apps</span></span>

<span data-ttu-id="5b507-173">Para probar el instalador de la aplicación con algunas aplicaciones de ejemplo, eche un vistazo a algunos de nuestros ejemplos disponibles:</span><span class="sxs-lookup"><span data-stu-id="5b507-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="5b507-174">Hub de ejemplos de MRTK</span><span class="sxs-lookup"><span data-stu-id="5b507-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="5b507-175">Surge</span><span class="sxs-lookup"><span data-stu-id="5b507-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="5b507-176">Aplicaciones de muestra para UWP que se pueden usar para pruebas</span><span class="sxs-lookup"><span data-stu-id="5b507-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
