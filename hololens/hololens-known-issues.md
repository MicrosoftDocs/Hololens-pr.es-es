---
title: Problemas conocidos de HoloLens (1.ª generación)
description: Manténgase al día con nuestra lista de problemas conocidos y soluciones alternativas que pueden afectar a los clientes y desarrolladores de HoloLens que usan Unity y el Portal de dispositivos Windows.
keywords: solución de problemas, problemas conocidos, ayuda
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923557"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="bfa43-104">Problemas conocidos de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="bfa43-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="bfa43-105">Esta es la lista actual de problemas conocidos de los dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="bfa43-106">Compruebe aquí primero si ve un comportamiento extraño.</span><span class="sxs-lookup"><span data-stu-id="bfa43-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="bfa43-107">Esta lista se mantendrá actualizada a medida que se detectan o notifican nuevos problemas, o a medida que se solucionen problemas en futuras actualizaciones de software de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="bfa43-108">Si detecta un problema que no está bloqueando, notimente en el dispositivo HoloLens a través [de Centro de opiniones](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="bfa43-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="bfa43-109">Si el problema al que se enfrenta le está bloqueando, además de presentar comentarios, [envíe una solicitud de soporte técnico](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="bfa43-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="bfa43-110">Problemas conocidos de todas las generaciones de HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfa43-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="bfa43-111">Problemas conocidos de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="bfa43-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="bfa43-112">Problemas conocidos de todas las generaciones de HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfa43-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="bfa43-113">Unity</span><span class="sxs-lookup"><span data-stu-id="bfa43-113">Unity</span></span>

- <span data-ttu-id="bfa43-114">Consulte [Instalación de las herramientas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Unity recomendada para el desarrollo de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-114">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="bfa43-115">Los problemas conocidos de Unity HoloLens Technical Preview se documentan en los [foros de Unity de HoloLens.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="bfa43-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="bfa43-116">Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="bfa43-116">Windows Device Portal</span></span>

- <span data-ttu-id="bfa43-117">La característica Live Preview de Mixed Reality captura puede presentar varios segundos de latencia.</span><span class="sxs-lookup"><span data-stu-id="bfa43-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="bfa43-118">En la página Entrada virtual, los controles Gesto y Desplazamiento de la sección Gestos virtuales no son funcionales.</span><span class="sxs-lookup"><span data-stu-id="bfa43-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="bfa43-119">Su uso no tendrá ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="bfa43-119">Using them will have no effect.</span></span> <span data-ttu-id="bfa43-120">El teclado virtual de la página de entrada virtual funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="bfa43-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="bfa43-121">Después de habilitar el modo de desarrollador en Configuración, puede tardar unos segundos antes de que el conmutador active el Portal de dispositivos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="bfa43-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="bfa43-122">Carga de la cámara de OneDrive</span><span class="sxs-lookup"><span data-stu-id="bfa43-122">OneDrive camera upload</span></span>

<span data-ttu-id="bfa43-123">La aplicación OneDrive para HoloLens no admite la carga automática de cámaras para cuentas profesionales o educativas.</span><span class="sxs-lookup"><span data-stu-id="bfa43-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="bfa43-124">Soluciones alternativas:</span><span class="sxs-lookup"><span data-stu-id="bfa43-124">Workarounds:</span></span>

- <span data-ttu-id="bfa43-125">Si es viable para su empresa, la carga automática de la cámara se admite en las cuentas microsoft del consumidor.</span><span class="sxs-lookup"><span data-stu-id="bfa43-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="bfa43-126">Puede iniciar sesión en su cuenta Microsoft además de la cuenta profesional o educativa (la aplicación OneDrive admite el inicio de sesión dual).</span><span class="sxs-lookup"><span data-stu-id="bfa43-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="bfa43-127">Desde el perfil de la cuenta microsoft en OneDrive, puede habilitar la carga automática de la cámara en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="bfa43-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="bfa43-128">Si no puede usar de forma segura una cuenta Microsoft de consumidor para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta laboral o educativa desde la aplicación OneDrive.</span><span class="sxs-lookup"><span data-stu-id="bfa43-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="bfa43-129">Para ello, asegúrese de que ha iniciado sesión en su cuenta laboral o educativa en la aplicación OneDrive.</span><span class="sxs-lookup"><span data-stu-id="bfa43-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="bfa43-130">Seleccione el **+** botón y elija **Cargar.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="bfa43-131">Para buscar las fotos o vídeos que desea cargar, vaya a **Imágenes > Camera Roll**.</span><span class="sxs-lookup"><span data-stu-id="bfa43-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="bfa43-132">Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.</span><span class="sxs-lookup"><span data-stu-id="bfa43-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="bfa43-133">Problemas conocidos de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="bfa43-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="bfa43-134">No se puede conectar e implementar en HoloLens a través de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bfa43-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="bfa43-135">Última actualización: 8/8 @ 5:11PM - Visual Studio ha publicado VS 2019 versión 16.2, que incluye una corrección para este problema.</span><span class="sxs-lookup"><span data-stu-id="bfa43-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="bfa43-136">Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.</span><span class="sxs-lookup"><span data-stu-id="bfa43-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="bfa43-137">Visual Studio versión 16.2 de VS 2019, que incluye una corrección para este problema.</span><span class="sxs-lookup"><span data-stu-id="bfa43-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="bfa43-138">Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.</span><span class="sxs-lookup"><span data-stu-id="bfa43-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="bfa43-139">Causa principal del problema: los usuarios que usaron Visual Studio 2015 o versiones anteriores de Visual Studio 2017 para implementar y depurar aplicaciones en holoLens y, a continuación, usaron posteriormente las versiones más recientes de Visual Studio 2017 o Visual Studio 2019 con el mismo HoloLens, se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="bfa43-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="bfa43-140">Las versiones más recientes de Visual Studio implementan una nueva versión de un componente, pero los archivos de la versión anterior se quedan en el dispositivo, lo que provoca un error en la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="bfa43-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="bfa43-141">Esto produce el siguiente mensaje de error: DEP0100: Asegúrese de que el dispositivo de destino tiene habilitado el modo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="bfa43-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="bfa43-142">No se pudo obtener una licencia de desarrollador \<ip\> en debido al error 80004005.</span><span class="sxs-lookup"><span data-stu-id="bfa43-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="bfa43-143">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="bfa43-143">Workaround</span></span>

<span data-ttu-id="bfa43-144">Nuestro equipo está trabajando actualmente en una corrección.</span><span class="sxs-lookup"><span data-stu-id="bfa43-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="bfa43-145">Mientras tanto, puede usar los pasos siguientes para evitar el problema y ayudar a desbloquear la implementación y depuración:</span><span class="sxs-lookup"><span data-stu-id="bfa43-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="bfa43-146">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bfa43-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="bfa43-147">Seleccione **File (Archivo)**  > **New (Nuevo)**  > **Project (Proyecto)** .</span><span class="sxs-lookup"><span data-stu-id="bfa43-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="bfa43-148">Seleccione Aplicación de consola de escritorio de Windows de **Visual C#**  >    >  **(.NET Framework).**</span><span class="sxs-lookup"><span data-stu-id="bfa43-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="bfa43-149">Asigne un nombre al proyecto (por ejemplo, "HoloLensDeploymentFix") y asegúrese de que framework esté establecido en al menos .NET Framework 4.5 y, a continuación, seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="bfa43-150">Haga clic con el botón **derecho** en el nodo Referencias  Explorador de soluciones agregue las siguientes referencias (seleccione la sección Examinar y **seleccione Examinar**):</span><span class="sxs-lookup"><span data-stu-id="bfa43-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="bfa43-151">Si no tiene instalada la versión 10.0.18362.0, use la versión más reciente que tenga.</span><span class="sxs-lookup"><span data-stu-id="bfa43-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="bfa43-152">Haga clic con el botón derecho en el proyecto Explorador de soluciones seleccione **Agregar**  >  **elemento existente.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="bfa43-153">Vaya a C:\Archivos de programa (x86)\Windows Kits\10\bin\10.0.18362.0\x86 y cambie el filtro a Todos los archivos **( \* . \* )**.</span><span class="sxs-lookup"><span data-stu-id="bfa43-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="bfa43-154">Seleccione tanto SirepClient.dll como SshClient.dll y Seleccione **Agregar.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="bfa43-155">Busque y seleccione ambos archivos en Explorador de soluciones (deben estar en la parte inferior de la  lista de archivos) y cambie **Copiar** al directorio de salida en la ventana Propiedades a Copiar **siempre.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="bfa43-156">En la parte superior del archivo, agregue lo siguiente a la lista existente `using` de instrucciones:</span><span class="sxs-lookup"><span data-stu-id="bfa43-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="bfa43-157">Dentro de `static void Main(...)` , agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfa43-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="bfa43-158">Seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="bfa43-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="bfa43-159">Abra una ventana del símbolo del sistema y cd en la carpeta que contiene el archivo .exe compilado (por ejemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="bfa43-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="bfa43-160">Ejecute el ejecutable y proporcione la dirección IP del dispositivo como argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="bfa43-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="bfa43-161">(Si está conectado mediante USB, puede usar 127.0.0.1; de lo contrario, use la dirección IP del Wi-Fi del dispositivo).  Por ejemplo, "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="bfa43-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="bfa43-162">Una vez que la herramienta ha salido sin ningún mensaje (esto solo debería tardar unos segundos), ahora podrá implementar y depurar desde Visual Studio 2017 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bfa43-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="bfa43-163">No es necesario seguir utilizando la herramienta.</span><span class="sxs-lookup"><span data-stu-id="bfa43-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="bfa43-164">Proporcionaremos más actualizaciones a medida que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="bfa43-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="bfa43-165">Problemas al iniciar Microsoft Store aplicaciones en HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfa43-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="bfa43-166">Última actualización: 4/2 @ 10 a. m.: problema resuelto.</span><span class="sxs-lookup"><span data-stu-id="bfa43-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="bfa43-167">Puede experimentar problemas al intentar iniciar el Microsoft Store y las aplicaciones en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="bfa43-168">Hemos determinado que el problema se produce cuando las actualizaciones de aplicaciones en segundo plano implementan una versión más reciente de los paquetes de marco en secuencias específicas mientras una o varias de sus aplicaciones dependientes todavía se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="bfa43-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="bfa43-169">En este caso, una actualización automática de la aplicación entregó una nueva versión de .NET Native Framework (versión 10.0.25531 a 10.0.27413) hizo que las aplicaciones que se ejecutan no se actualicen correctamente para todas las aplicaciones en ejecución que consumen la versión anterior del marco.</span><span class="sxs-lookup"><span data-stu-id="bfa43-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="bfa43-170">El flujo para la actualización del marco es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfa43-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="bfa43-171">El nuevo paquete de marco se descarga de la tienda e se instala.</span><span class="sxs-lookup"><span data-stu-id="bfa43-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="bfa43-172">Todas las aplicaciones que usan el marco anterior se "actualizan" para usar la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="bfa43-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="bfa43-173">Si se interrumpe el paso 2 antes de la finalización, las aplicaciones para las que no se registró el marco más reciente no se iniciarán desde el menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="bfa43-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="bfa43-174">Creemos que cualquier aplicación de HoloLens podría verse afectada por este problema.</span><span class="sxs-lookup"><span data-stu-id="bfa43-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="bfa43-175">Algunos usuarios han informado de que el cierre de aplicaciones con cierre e inicio de otras aplicaciones como Centro de opiniones, Visor 3D o Fotos resuelve el problema para ellas; sin embargo, esto no funciona el 100 % del tiempo.</span><span class="sxs-lookup"><span data-stu-id="bfa43-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="bfa43-176">La raíz ha provocado que este problema no se haya producido en la propia actualización, sino en un error en el sistema operativo que ha provocado que la actualización del marco de trabajo de .NET Native se controle incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="bfa43-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="bfa43-177">Nos complace anunciar que hemos identificado una corrección y hemos publicado una actualización (versión del sistema operativo 17763.380) que contiene la corrección.</span><span class="sxs-lookup"><span data-stu-id="bfa43-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="bfa43-178">Para ver si el dispositivo puede realizar la actualización:</span><span class="sxs-lookup"><span data-stu-id="bfa43-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="bfa43-179">Vaya a la aplicación Configuración y abra **Actualizar & Seguridad.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="bfa43-180">Seleccione **Buscar actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="bfa43-181">Si la actualización a 17763.380 está disponible, actualice a esta compilación para recibir la corrección del error de app hang.</span><span class="sxs-lookup"><span data-stu-id="bfa43-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="bfa43-182">Tras actualizar a esta versión del sistema operativo, las aplicaciones deben funcionar según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="bfa43-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="bfa43-183">Además, como hacemos con cada versión del sistema operativo HoloLens, hemos publicado la imagen de FFU en el Centro [de descarga de Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)</span><span class="sxs-lookup"><span data-stu-id="bfa43-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="bfa43-184">Si no desea realizar la actualización, hemos publicado una nueva versión de Microsoft Store aplicación para UWP a partir del 29/3.</span><span class="sxs-lookup"><span data-stu-id="bfa43-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="bfa43-185">Después de tener la versión actualizada de Store:</span><span class="sxs-lookup"><span data-stu-id="bfa43-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="bfa43-186">Abra store y confirme que se carga.</span><span class="sxs-lookup"><span data-stu-id="bfa43-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="bfa43-187">Use el gesto de Bloom para abrir el menú.</span><span class="sxs-lookup"><span data-stu-id="bfa43-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="bfa43-188">Intente abrir aplicaciones previamente rotas.</span><span class="sxs-lookup"><span data-stu-id="bfa43-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="bfa43-189">Si todavía no se puede iniciar, mantenga presionado el icono de la aplicación rota y seleccione Desinstalar.</span><span class="sxs-lookup"><span data-stu-id="bfa43-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="bfa43-190">Vuelva a instalar estas aplicaciones desde la tienda.</span><span class="sxs-lookup"><span data-stu-id="bfa43-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="bfa43-191">Si el dispositivo sigue sin poder cargar aplicaciones, puede realizar la instalación local de una versión de .NET Native Framework y Runtime a través del Centro de descarga siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bfa43-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="bfa43-192">Descargue este [archivo ZIP desde](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfa43-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="bfa43-193">La descomprimir producirá dos archivos.</span><span class="sxs-lookup"><span data-stu-id="bfa43-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="bfa43-194">Microsoft .NET.Native.Runtime.1.7.appx y Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="bfa43-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="bfa43-195">Compruebe que el dispositivo está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="bfa43-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="bfa43-196">Si no lo ha hecho antes, consulte Uso de [la Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="bfa43-196">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="bfa43-197">A continuación, quiere entrar en el Portal de dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="bfa43-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="bfa43-198">Nuestra recomendación es hacerlo a través de USB y lo haría escribiendo http://127.0.0.1:10080 en el explorador.</span><span class="sxs-lookup"><span data-stu-id="bfa43-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="bfa43-199">Una vez que haya Portal de dispositivos Windows, necesitamos que "cargue lateralmente" los dos archivos que descargó.</span><span class="sxs-lookup"><span data-stu-id="bfa43-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="bfa43-200">Para ello, debe bajar la barra lateral izquierda hasta llegar a la sección **Aplicaciones** y seleccionar **Aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="bfa43-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="bfa43-201">A continuación, verá una pantalla similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="bfa43-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="bfa43-202">Quiere ir a la sección que indica **Instalar** aplicación y ir a donde descomprimió esos dos archivos APPX.</span><span class="sxs-lookup"><span data-stu-id="bfa43-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="bfa43-203">Solo puede realizar una de cada vez, por lo que después de seleccionar la primera, haga clic en "Ir" en la sección Implementar.</span><span class="sxs-lookup"><span data-stu-id="bfa43-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="bfa43-204">A continuación, haga esto para el segundo archivo APPX.</span><span class="sxs-lookup"><span data-stu-id="bfa43-204">Then do this for the second APPX file.</span></span>

   ![Portal de dispositivos Windows instalar la Side-Loaded aplicación](images/20190322-DevicePortal.png)

1. <span data-ttu-id="bfa43-206">En este momento creemos que las aplicaciones deben empezar a funcionar de nuevo y que también puede acceder a store.</span><span class="sxs-lookup"><span data-stu-id="bfa43-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="bfa43-207">En algunos casos, es necesario ejecutar el paso adicional de iniciar la aplicación Visor 3D antes de que se inicien las aplicaciones afectadas.</span><span class="sxs-lookup"><span data-stu-id="bfa43-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="bfa43-208">Agradecemos su paciencia a medida que hemos pasado por el proceso para resolver este problema y esperamos seguir trabajando con nuestra comunidad para crear experiencias de Mixed Reality correctas.</span><span class="sxs-lookup"><span data-stu-id="bfa43-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="bfa43-209">Actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="bfa43-209">Device Update</span></span>

- <span data-ttu-id="bfa43-210">30 segundos después de una nueva actualización, el shell puede desaparecer una vez.</span><span class="sxs-lookup"><span data-stu-id="bfa43-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="bfa43-211">Realice el gesto **de Bloom** para reanudar la sesión.</span><span class="sxs-lookup"><span data-stu-id="bfa43-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="bfa43-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bfa43-212">Visual Studio</span></span>

- <span data-ttu-id="bfa43-213">Consulte [Instalación de las herramientas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Visual Studio que se recomienda para el desarrollo de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-213">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="bfa43-214">Al implementar una aplicación desde Visual Studio a HoloLens, es posible que vea el error: La operación solicitada no se puede realizar en un archivo con una sección asignada por **el usuario abierta. (Excepción de HRESULT: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="bfa43-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="bfa43-215">Si esto sucede, inténtelo de nuevo y, por lo general, la implementación se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="bfa43-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="bfa43-216">API</span><span class="sxs-lookup"><span data-stu-id="bfa43-216">API</span></span>

- <span data-ttu-id="bfa43-217">Si la aplicación establece [el](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) punto de enfoque detrás del usuario o lo normal en camera.forward, los hologramas no aparecerán en Captura de realidad mixta fotos o vídeos.</span><span class="sxs-lookup"><span data-stu-id="bfa43-217">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="bfa43-218">Hasta que se corrigió este error [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) en Windows, si las aplicaciones establecen activamente el punto de enfoque, deben asegurarse de que el plano normal se establece en dirección opuesta a la cámara (por ejemplo, normal = -camera.forward).</span><span class="sxs-lookup"><span data-stu-id="bfa43-218">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="bfa43-219">Controlador inalámbrico de Xbox</span><span class="sxs-lookup"><span data-stu-id="bfa43-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="bfa43-220">El controlador inalámbrico S de Xbox debe actualizarse para poder usarse con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="bfa43-221">Asegúrese de que [está actualizado antes](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) de intentar emparejar el controlador con holoLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="bfa43-222">Si reinicias HoloLens mientras el controlador inalámbrico de Xbox está conectado, el controlador no se volverá a conectar automáticamente a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="bfa43-223">La luz del botón Guía parpadeará lentamente hasta que el controlador se apague después de 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="bfa43-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="bfa43-224">Para volver a conectar el controlador inmediatamente, apague el controlador manteniendo presionado el botón Guía hasta que se apague la luz.</span><span class="sxs-lookup"><span data-stu-id="bfa43-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="bfa43-225">Cuando vuelva a encender el controlador, se volverá a conectar a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="bfa43-226">Si HoloLens entra en espera mientras el controlador inalámbrico de Xbox está conectado, cualquier entrada en el controlador reactivará HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bfa43-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="bfa43-227">Puede evitarlo apagando el controlador cuando haya terminado de usarlo.</span><span class="sxs-lookup"><span data-stu-id="bfa43-227">You can prevent this by powering off your controller when you are done using it.</span></span>

