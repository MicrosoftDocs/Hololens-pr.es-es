---
title: Cómo realizar la carga de prueba e instalar aplicaciones a través de HoloLens 2 Instalador de aplicación
description: Aprenda a instalar y solucionar problemas de aplicaciones con el instalador de aplicaciones y a cargar e instalar aplicaciones a través de la interfaz de usuario.
keywords: administración de aplicaciones, aplicación, hololens, instalador de aplicaciones
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
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924135"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="9c57e-104">Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación</span><span class="sxs-lookup"><span data-stu-id="9c57e-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="9c57e-105">Esta característica estaba disponible en [Windows Holographic, versión 20H2– Actualización de diciembre de 2020.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="9c57e-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="9c57e-106">Asegúrese de que el [dispositivo está actualizado](hololens-update-hololens.md) para usar esta característica.</span><span class="sxs-lookup"><span data-stu-id="9c57e-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="9c57e-107">Hemos agregado **una nueva funcionalidad (Instalador de aplicación)** que le permite instalar aplicaciones de forma más fluida en los dispositivos HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9c57e-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="9c57e-108">La característica estará en **modo predeterminado para dispositivos no administrados.**</span><span class="sxs-lookup"><span data-stu-id="9c57e-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="9c57e-109">Para evitar interrupciones en las empresas, el instalador de aplicaciones no **estará disponible para dispositivos administrados** en este momento.</span><span class="sxs-lookup"><span data-stu-id="9c57e-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="9c57e-110">Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="9c57e-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="9c57e-111">Inscrito [en](hololens-enroll-mdm.md) MDM</span><span class="sxs-lookup"><span data-stu-id="9c57e-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="9c57e-112">Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="9c57e-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="9c57e-113">Identidad [de usuario](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="9c57e-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="9c57e-114">Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni usar Portal de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9c57e-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="9c57e-115">Descargue (a través de USB o a través de Microsoft Edge) el paquete de Appx en el dispositivo y vaya al paquete de Appx en el Explorador de archivos para que se le pida que arranque la instalación.</span><span class="sxs-lookup"><span data-stu-id="9c57e-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="9c57e-116">Como alternativa, [inicie una instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="9c57e-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="9c57e-117">Al igual que las aplicaciones que instala desde Microsoft Store o la instalación local mediante la funcionalidad de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) implementación de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) aplicaciones LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la herramienta de firma y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c57e-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c57e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c57e-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="9c57e-119">Para los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="9c57e-119">For your devices:</span></span>

<span data-ttu-id="9c57e-120">Esta característica está disponible actualmente en las compilaciones de Windows Holographic 20H2 para HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9c57e-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="9c57e-121">Asegúrese de que todos los dispositivos que usan este método se [actualizan.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="9c57e-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="9c57e-122">Para las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="9c57e-122">For your apps:</span></span>

<span data-ttu-id="9c57e-123">La configuración de la solución de la aplicación debe ser **Maestra** o **Versión,** ya que el Instalador de aplicación usará dependencias del almacén.</span><span class="sxs-lookup"><span data-stu-id="9c57e-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="9c57e-124">Más información sobre la [creación de paquetes de aplicaciones.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="9c57e-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="9c57e-125">Las aplicaciones que se instalan a través de este método deben estar firmadas digitalmente.</span><span class="sxs-lookup"><span data-stu-id="9c57e-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="9c57e-126">Deberá usar un certificado para firmar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c57e-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="9c57e-127">Puede obtener un certificado de la lista de ca de confianza de [MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)en cuyo caso no tendrá que realizar ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="9c57e-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="9c57e-128">O bien, puede firmar su propio certificado, pero ese certificado deberá insertarse en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9c57e-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="9c57e-129">Cómo firmar aplicaciones [mediante la herramienta Firmar.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="9c57e-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="9c57e-130">**Opciones de certificado:**</span><span class="sxs-lookup"><span data-stu-id="9c57e-130">**Certificate options:**</span></span>

- [<span data-ttu-id="9c57e-131">Lista de ca de confianza de MS</span><span class="sxs-lookup"><span data-stu-id="9c57e-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="9c57e-132">**Elija un método de implementación de certificado.**</span><span class="sxs-lookup"><span data-stu-id="9c57e-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="9c57e-133">[Los paquetes de](hololens-provisioning.md) aprovisionamiento se pueden aplicar a dispositivos locales.</span><span class="sxs-lookup"><span data-stu-id="9c57e-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="9c57e-134">MDM se puede usar para [aplicar certificados con configuraciones de dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="9c57e-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="9c57e-135">Use en el dispositivo el [Administrador de certificados](certificate-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9c57e-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="9c57e-136">Método de instalación</span><span class="sxs-lookup"><span data-stu-id="9c57e-136">Installation method</span></span>

1. <span data-ttu-id="9c57e-137">Compruebe que el dispositivo no se considera administrado.</span><span class="sxs-lookup"><span data-stu-id="9c57e-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="9c57e-138">Compruebe que el HoloLens 2 está encendido y que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="9c57e-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="9c57e-139">En el equipo, vaya a la aplicación personalizada y copie yourapp.appxbundle en yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="9c57e-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="9c57e-140">Cuando termine de copiar el archivo, puede desconectar el dispositivo y finalizar la instalación más adelante.</span><span class="sxs-lookup"><span data-stu-id="9c57e-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="9c57e-141">En el HoloLens 2, abra el **menú Inicio,** seleccione Todas las **aplicaciones** e inicie **Explorador de archivos** aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c57e-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="9c57e-142">Vaya a la carpeta Descargas.</span><span class="sxs-lookup"><span data-stu-id="9c57e-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="9c57e-143">En el panel izquierdo de la aplicación, seleccione Este **dispositivo** en primer lugar y, a continuación, vaya a Descargas.</span><span class="sxs-lookup"><span data-stu-id="9c57e-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="9c57e-144">Seleccione el archivo yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="9c57e-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="9c57e-145">La Instalador de aplicación se iniciará.</span><span class="sxs-lookup"><span data-stu-id="9c57e-145">The App Installer will launch.</span></span> <span data-ttu-id="9c57e-146">Seleccione el **botón** Instalar para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c57e-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="9c57e-147">La aplicación instalada se iniciará automáticamente al finalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="9c57e-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalación de ejemplos de MRTK mediante Instalador de aplicación](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="9c57e-149">Solución de problemas de instalación</span><span class="sxs-lookup"><span data-stu-id="9c57e-149">Troubleshooting Installs</span></span>

<span data-ttu-id="9c57e-150">Si la aplicación no se pudo instalar, compruebe lo siguiente para solucionar problemas:</span><span class="sxs-lookup"><span data-stu-id="9c57e-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="9c57e-151">La aplicación es una compilación maestra o de versión.</span><span class="sxs-lookup"><span data-stu-id="9c57e-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="9c57e-152">El dispositivo se actualiza a una compilación en la que esta característica está disponible.</span><span class="sxs-lookup"><span data-stu-id="9c57e-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="9c57e-153">Está conectado [a Internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="9c57e-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="9c57e-154">Los [puntos de conexión de la Microsoft Store](hololens-offline.md) están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="9c57e-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="9c57e-155">Instalador web</span><span class="sxs-lookup"><span data-stu-id="9c57e-155">Web Installer</span></span>

<span data-ttu-id="9c57e-156">Los usuarios pueden instalar una aplicación directamente desde un servidor web.</span><span class="sxs-lookup"><span data-stu-id="9c57e-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="9c57e-157">Este flujo usa el Instalador de aplicación combinado con un método de distribución fácil de descargar e instalar.</span><span class="sxs-lookup"><span data-stu-id="9c57e-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="9c57e-158">Configuración de la instalación web:</span><span class="sxs-lookup"><span data-stu-id="9c57e-158">How to set up web install:</span></span>

1. <span data-ttu-id="9c57e-159">Asegúrese de que la aplicación está configurada correctamente para instalarse.</span><span class="sxs-lookup"><span data-stu-id="9c57e-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="9c57e-160">Siga estos [pasos para habilitar la instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="9c57e-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="9c57e-161">Experiencia del usuario final:</span><span class="sxs-lookup"><span data-stu-id="9c57e-161">End user experience:</span></span>

1. <span data-ttu-id="9c57e-162">El usuario recibe e instala el certificado en el dispositivo mediante un método elegido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9c57e-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="9c57e-163">El usuario visita la dirección URL creada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="9c57e-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="9c57e-164">La aplicación se instalará ahora en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9c57e-164">The app will now install to the device.</span></span> <span data-ttu-id="9c57e-165">Para buscar la aplicación, abra **el** menú Inicio y seleccione el botón **Todas las** aplicaciones para buscar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c57e-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="9c57e-166">Para obtener más ayuda con la solución de problemas del método de instalación del instalador de aplicaciones, visite [Solución de problemas del instalador de aplicaciones.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="9c57e-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="9c57e-167">No se admite la interfaz de usuario durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="9c57e-167">UI during the update process is not supported.</span></span> <span data-ttu-id="9c57e-168">Por lo tanto, la opción ShowPrompt de [esta página y](https://docs.microsoft.com/windows/msix/app-installer/update-settings) las opciones relacionadas no se admiten.</span><span class="sxs-lookup"><span data-stu-id="9c57e-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="9c57e-169">Aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c57e-169">Sample Apps</span></span>

<span data-ttu-id="9c57e-170">Pruebe el Instalador de aplicación con una de nuestras aplicaciones de ejemplo disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c57e-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="9c57e-171">Aplicaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c57e-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
