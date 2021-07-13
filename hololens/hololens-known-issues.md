---
title: Problemas conocidos de HoloLens (1.ª generación)
description: Manténgase al día con nuestra lista de problemas conocidos y soluciones alternativas que pueden afectar HoloLens clientes y desarrolladores que usan Unity y Windows Portal de dispositivos.
keywords: solución de problemas, problema conocido, ayuda
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
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640311"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="4113a-104">Problemas conocidos de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="4113a-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="4113a-105">Esta es la lista actual de problemas conocidos para HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4113a-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="4113a-106">Compruebe aquí primero si ve un comportamiento extraño.</span><span class="sxs-lookup"><span data-stu-id="4113a-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="4113a-107">Esta lista se mantendrá actualizada a medida que se detectan o notifican nuevos problemas, o a medida que se solucione el problema en HoloLens actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="4113a-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="4113a-108">Si detecta un problema que no está bloqueando, notimente en el dispositivo HoloLens a través [de Centro de opiniones](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="4113a-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="4113a-109">Si el problema al que se enfrenta le está bloqueando, además de presentar comentarios, [envíe una solicitud de soporte técnico](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="4113a-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="4113a-110">Problemas conocidos de todas las HoloLens generaciones</span><span class="sxs-lookup"><span data-stu-id="4113a-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="4113a-111">Problemas conocidos de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="4113a-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="4113a-112">Problemas conocidos de todas las HoloLens generaciones</span><span class="sxs-lookup"><span data-stu-id="4113a-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="4113a-113">Unity</span><span class="sxs-lookup"><span data-stu-id="4113a-113">Unity</span></span>

- <span data-ttu-id="4113a-114">Consulte [Instalación de las herramientas](/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Unity recomendada para HoloLens desarrollo.</span><span class="sxs-lookup"><span data-stu-id="4113a-114">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="4113a-115">Los problemas conocidos con unity HoloLens Technical Preview se documentan [en los HoloLens de Unity.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="4113a-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="4113a-116">Portal de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="4113a-116">Windows Device Portal</span></span>

- <span data-ttu-id="4113a-117">La característica Live Preview de Mixed Reality captura puede presentar varios segundos de latencia.</span><span class="sxs-lookup"><span data-stu-id="4113a-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="4113a-118">En la página Entrada virtual, los controles Gesto y Desplazamiento de la sección Gestos virtuales no son funcionales.</span><span class="sxs-lookup"><span data-stu-id="4113a-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="4113a-119">Su uso no tendrá ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="4113a-119">Using them will have no effect.</span></span> <span data-ttu-id="4113a-120">El teclado virtual de la página de entrada virtual funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="4113a-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="4113a-121">Después de habilitar el modo de desarrollador en Configuración, puede tardar unos segundos antes de que el conmutador active el Portal de dispositivos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4113a-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="4113a-122">OneDrive de la cámara</span><span class="sxs-lookup"><span data-stu-id="4113a-122">OneDrive camera upload</span></span>

<span data-ttu-id="4113a-123">La OneDrive aplicación para HoloLens no admite la carga automática de cámara para cuentas de trabajo o educativas.</span><span class="sxs-lookup"><span data-stu-id="4113a-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="4113a-124">Soluciones alternativas:</span><span class="sxs-lookup"><span data-stu-id="4113a-124">Workarounds:</span></span>

- <span data-ttu-id="4113a-125">Si es viable para su empresa, la carga automática de la cámara se admite en las cuentas Microsoft del consumidor.</span><span class="sxs-lookup"><span data-stu-id="4113a-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="4113a-126">Puede iniciar sesión en su cuenta Microsoft además de la cuenta profesional o educativa (la aplicación OneDrive admite el inicio de sesión doble).</span><span class="sxs-lookup"><span data-stu-id="4113a-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="4113a-127">Desde el perfil de la cuenta De Microsoft OneDrive puede habilitar la carga automática de lanzamiento de cámara en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4113a-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="4113a-128">Si no puede usar de forma segura una cuenta Microsoft de consumidor para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta de trabajo o educativa desde la OneDrive aplicación.</span><span class="sxs-lookup"><span data-stu-id="4113a-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="4113a-129">Para ello, asegúrese de que ha iniciado sesión en su cuenta de trabajo o educativa en la OneDrive aplicación.</span><span class="sxs-lookup"><span data-stu-id="4113a-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="4113a-130">Seleccione el **+** botón y elija **Upload**.</span><span class="sxs-lookup"><span data-stu-id="4113a-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="4113a-131">Para buscar las fotos o vídeos que desea cargar, vaya a **Imágenes > de cámara.**</span><span class="sxs-lookup"><span data-stu-id="4113a-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="4113a-132">Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.</span><span class="sxs-lookup"><span data-stu-id="4113a-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="4113a-133">Problemas conocidos de HoloLens (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="4113a-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="4113a-134">No se puede conectar e implementar en HoloLens a través de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4113a-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="4113a-135">Última actualización: 8/8 @ 5:11 p. m.: Visual Studio ha publicado VS 2019, versión 16.2, que incluye una corrección para este problema.</span><span class="sxs-lookup"><span data-stu-id="4113a-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="4113a-136">Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.</span><span class="sxs-lookup"><span data-stu-id="4113a-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="4113a-137">Visual Studio versión 16.2 de VS 2019, que incluye una corrección para este problema.</span><span class="sxs-lookup"><span data-stu-id="4113a-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="4113a-138">Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.</span><span class="sxs-lookup"><span data-stu-id="4113a-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="4113a-139">Causa principal del problema: los usuarios que usaron Visual Studio 2015 o versiones anteriores de Visual Studio 2017 para implementar y depurar aplicaciones en su HoloLens y, a continuación, usaron posteriormente las versiones más recientes de Visual Studio 2017 o Visual Studio 2019 con el mismo HoloLens se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="4113a-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="4113a-140">Las versiones más recientes de Visual Studio implementan una nueva versión de un componente, pero los archivos de la versión anterior se quedan en el dispositivo, lo que provoca un error en la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="4113a-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="4113a-141">Esto produce el siguiente mensaje de error: DEP0100: Asegúrese de que el dispositivo de destino tiene habilitado el modo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="4113a-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="4113a-142">No se pudo obtener una licencia de desarrollador \<ip\> en debido al error 80004005.</span><span class="sxs-lookup"><span data-stu-id="4113a-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="4113a-143">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="4113a-143">Workaround</span></span>

<span data-ttu-id="4113a-144">Nuestro equipo está trabajando actualmente en una corrección.</span><span class="sxs-lookup"><span data-stu-id="4113a-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="4113a-145">Mientras tanto, puede usar los pasos siguientes para evitar el problema y ayudar a desbloquear la implementación y depuración:</span><span class="sxs-lookup"><span data-stu-id="4113a-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="4113a-146">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4113a-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="4113a-147">Seleccione **File (Archivo)**  > **New (Nuevo)**  > **Project (Proyecto)** .</span><span class="sxs-lookup"><span data-stu-id="4113a-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="4113a-148">Seleccione **Visual C#**  >  **Windows aplicación de** consola de escritorio  >  **(.NET Framework).**</span><span class="sxs-lookup"><span data-stu-id="4113a-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="4113a-149">Asigne al proyecto un nombre (por ejemplo, "HoloLensDeploymentFix") y asegúrese de que framework esté establecido en al menos .NET Framework 4.5 y, a continuación, seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="4113a-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="4113a-150">Haga clic con el **botón** derecho en el nodo Referencias  Explorador de soluciones agregue las siguientes referencias (seleccione la sección Examinar y seleccione **Examinar**):</span><span class="sxs-lookup"><span data-stu-id="4113a-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="4113a-151">Si no tiene instalada la versión 10.0.18362.0, use la versión más reciente que tenga.</span><span class="sxs-lookup"><span data-stu-id="4113a-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="4113a-152">Haga clic con el botón derecho en el proyecto Explorador de soluciones seleccione **Agregar**  >  **elemento existente.**</span><span class="sxs-lookup"><span data-stu-id="4113a-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="4113a-153">Vaya a C:\Archivos de programa (x86)\Windows Kits\10\bin\10.0.18362.0\x86 y cambie el filtro a Todos los archivos **( \* . \* )**.</span><span class="sxs-lookup"><span data-stu-id="4113a-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="4113a-154">Seleccione SirepClient.dll y SshClient.dll y Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4113a-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="4113a-155">Busque y seleccione ambos archivos en Explorador de soluciones (deben estar en la parte  inferior de la  lista de archivos) y cambie Copiar al directorio de salida en la ventana Propiedades a Copiar **siempre.**</span><span class="sxs-lookup"><span data-stu-id="4113a-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="4113a-156">En la parte superior del archivo, agregue lo siguiente a la lista existente `using` de instrucciones:</span><span class="sxs-lookup"><span data-stu-id="4113a-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="4113a-157">Dentro de `static void Main(...)` , agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4113a-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="4113a-158">Seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="4113a-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="4113a-159">Abra una ventana del símbolo del sistema y cd en la carpeta que contiene el archivo .exe compilado (por ejemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="4113a-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="4113a-160">Ejecute el archivo ejecutable y proporcione la dirección IP del dispositivo como argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4113a-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="4113a-161">(Si está conectado mediante USB, puede usar 127.0.0.1; de lo contrario, use la dirección IP Wi-Fi del dispositivo).  Por ejemplo, "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="4113a-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="4113a-162">Una vez que la herramienta ha salido sin ningún mensaje (esto solo debería tardar unos segundos), ahora podrá implementar y depurar desde Visual Studio 2017 o posterior.</span><span class="sxs-lookup"><span data-stu-id="4113a-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="4113a-163">No es necesario seguir utilizando la herramienta.</span><span class="sxs-lookup"><span data-stu-id="4113a-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="4113a-164">Se proporcionarán más actualizaciones a medida que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="4113a-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="4113a-165">Problemas al iniciar el Microsoft Store y las aplicaciones en HoloLens</span><span class="sxs-lookup"><span data-stu-id="4113a-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="4113a-166">Última actualización: 4/2 @ 10 a. m.: problema resuelto.</span><span class="sxs-lookup"><span data-stu-id="4113a-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="4113a-167">Puede experimentar problemas al intentar iniciar el Microsoft Store aplicaciones en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4113a-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="4113a-168">Hemos determinado que el problema se produce cuando las actualizaciones de aplicaciones en segundo plano implementan una versión más reciente de los paquetes de marco en secuencias específicas mientras una o varias de sus aplicaciones dependientes todavía se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4113a-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="4113a-169">En este caso, una actualización automática de la aplicación entregó una nueva versión de .NET Native Framework (versión 10.0.25531 a 10.0.27413) hizo que las aplicaciones que se ejecutan no se actualizaran correctamente para todas las aplicaciones en ejecución que consuman la versión anterior del marco.</span><span class="sxs-lookup"><span data-stu-id="4113a-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="4113a-170">El flujo para la actualización del marco es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="4113a-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="4113a-171">El nuevo paquete de marco se descarga del almacén y se instala.</span><span class="sxs-lookup"><span data-stu-id="4113a-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="4113a-172">Todas las aplicaciones que usan el marco anterior se "actualizan" para usar la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="4113a-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="4113a-173">Si se interrumpe el paso 2 antes de la finalización, las aplicaciones para las que no se registró el marco más reciente no podrán iniciarse desde el menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="4113a-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="4113a-174">Creemos que cualquier aplicación de HoloLens podría verse afectada por este problema.</span><span class="sxs-lookup"><span data-stu-id="4113a-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="4113a-175">Algunos usuarios han informado de que el cierre de aplicaciones que se han cerrado e iniciando otras aplicaciones como Centro de opiniones, Visor 3D o Fotos resuelve el problema para ellas; sin embargo, esto no funciona el 100 % del tiempo.</span><span class="sxs-lookup"><span data-stu-id="4113a-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="4113a-176">La raíz ha provocado que este problema no se haya debido a la propia actualización, sino a un error en el sistema operativo que ha provocado que la actualización del marco de trabajo de .NET Native se controle incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="4113a-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="4113a-177">Nos complace anunciar que hemos identificado una corrección y que hemos publicado una actualización (versión del sistema operativo 17763.380) que contiene la corrección.</span><span class="sxs-lookup"><span data-stu-id="4113a-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="4113a-178">Para ver si el dispositivo puede realizar la actualización:</span><span class="sxs-lookup"><span data-stu-id="4113a-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="4113a-179">Vaya a la aplicación Configuración y abra **Update & Security**.</span><span class="sxs-lookup"><span data-stu-id="4113a-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="4113a-180">Seleccione **Buscar actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="4113a-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="4113a-181">Si la actualización a 17763.380 está disponible, actualice a esta compilación para recibir la corrección del error de app hang.</span><span class="sxs-lookup"><span data-stu-id="4113a-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="4113a-182">Tras actualizar a esta versión del sistema operativo, las aplicaciones deben funcionar según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="4113a-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="4113a-183">Además, como hacemos con cada versión HoloLens sistema operativo, hemos publicado la imagen de FFU en el Centro [de descarga de Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).</span><span class="sxs-lookup"><span data-stu-id="4113a-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="4113a-184">Si no desea realizar la actualización, hemos publicado una nueva versión de la aplicación Microsoft Store UWP a partir del 29/3.</span><span class="sxs-lookup"><span data-stu-id="4113a-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="4113a-185">Una vez actualizada la versión de Store:</span><span class="sxs-lookup"><span data-stu-id="4113a-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="4113a-186">Abra store y confirme que se carga.</span><span class="sxs-lookup"><span data-stu-id="4113a-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="4113a-187">Use el gesto de Bloom para abrir el menú.</span><span class="sxs-lookup"><span data-stu-id="4113a-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="4113a-188">Intente abrir aplicaciones previamente rotas.</span><span class="sxs-lookup"><span data-stu-id="4113a-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="4113a-189">Si todavía no se puede iniciar, mantenga presionado el icono de la aplicación rota y seleccione Desinstalar.</span><span class="sxs-lookup"><span data-stu-id="4113a-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="4113a-190">Vuelva a instalar estas aplicaciones desde la tienda.</span><span class="sxs-lookup"><span data-stu-id="4113a-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="4113a-191">Si el dispositivo sigue sin poder cargar aplicaciones, puede realizar la instalación local de una versión de .NET Native Framework y Runtime a través del centro de descarga siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4113a-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="4113a-192">Descargue este [archivo ZIP desde](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4113a-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="4113a-193">La descomprimir producirá dos archivos.</span><span class="sxs-lookup"><span data-stu-id="4113a-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="4113a-194">Microsoft .NET.Native.Runtime.1.7.appx y Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="4113a-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="4113a-195">Compruebe que el dispositivo está dev desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="4113a-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="4113a-196">Si no lo ha hecho antes, consulte Uso de [la Windows Portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="4113a-196">If you haven't done that before, see [Using the Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="4113a-197">A continuación, quiere entrar en el Windows Portal de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4113a-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="4113a-198">Nuestra recomendación es hacerlo a través de USB y lo haría escribiendo http://127.0.0.1:10080 en el explorador.</span><span class="sxs-lookup"><span data-stu-id="4113a-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="4113a-199">Una vez que haya Windows Portal de dispositivos, es necesario que "cargue en paralelo" los dos archivos que descargó.</span><span class="sxs-lookup"><span data-stu-id="4113a-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="4113a-200">Para ello, debe bajar la barra lateral izquierda hasta llegar a la **sección Aplicaciones** y seleccionar **Aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="4113a-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="4113a-201">A continuación, verá una pantalla similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="4113a-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="4113a-202">Quiere ir a la sección que indica **Instalar** aplicación y ir a donde descomprimió esos dos archivos APPX.</span><span class="sxs-lookup"><span data-stu-id="4113a-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="4113a-203">Solo puede hacer una a la vez, por lo que después de seleccionar la primera, haga clic en "Ir" en la sección Implementar.</span><span class="sxs-lookup"><span data-stu-id="4113a-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="4113a-204">A continuación, haga esto para el segundo archivo APPX.</span><span class="sxs-lookup"><span data-stu-id="4113a-204">Then do this for the second APPX file.</span></span>

   ![Windows Portal de dispositivos instalar la Side-Loaded aplicación](images/20190322-DevicePortal.png)

1. <span data-ttu-id="4113a-206">En este momento creemos que las aplicaciones deben empezar a funcionar de nuevo y que también puede acceder a la Tienda.</span><span class="sxs-lookup"><span data-stu-id="4113a-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="4113a-207">En algunos casos, es necesario ejecutar el paso adicional de inicio de Visor 3D aplicación antes de que se inicien las aplicaciones afectadas.</span><span class="sxs-lookup"><span data-stu-id="4113a-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="4113a-208">Agradecemos su paciencia a medida que hemos pasado por el proceso para resolver este problema y esperamos seguir trabajando con nuestra comunidad para crear experiencias de Mixed Reality correctas.</span><span class="sxs-lookup"><span data-stu-id="4113a-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="4113a-209">Actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="4113a-209">Device Update</span></span>

- <span data-ttu-id="4113a-210">30 segundos después de una nueva actualización, el shell puede desaparecer una vez.</span><span class="sxs-lookup"><span data-stu-id="4113a-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="4113a-211">Realice el gesto **de Bloom** para reanudar la sesión.</span><span class="sxs-lookup"><span data-stu-id="4113a-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="4113a-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4113a-212">Visual Studio</span></span>

- <span data-ttu-id="4113a-213">Consulte [Instalación de las herramientas](/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Visual Studio que se recomienda para HoloLens desarrollo.</span><span class="sxs-lookup"><span data-stu-id="4113a-213">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="4113a-214">Al implementar una aplicación de Visual Studio a su HoloLens, es posible que vea el error: La operación solicitada no se puede realizar en un archivo con una sección asignada por el **usuario abierta. (Excepción de HRESULT: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="4113a-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="4113a-215">Si esto sucede, inténtelo de nuevo y la implementación generalmente se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="4113a-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="4113a-216">API</span><span class="sxs-lookup"><span data-stu-id="4113a-216">API</span></span>

- <span data-ttu-id="4113a-217">Si la aplicación establece el [punto](/windows/mixed-reality/focus-point-in-unity) de enfoque detrás del usuario o lo normal en camera.forward, los hologramas no aparecerán en Captura de realidad mixta fotos o vídeos.</span><span class="sxs-lookup"><span data-stu-id="4113a-217">If the application sets the [focus point](/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="4113a-218">Hasta que este error se corrigió en Windows, si las aplicaciones establecen activamente el punto de enfoque, deben asegurarse de que el plano normal se establece en el avance de la cámara opuesto (por ejemplo, normal = -camera.forward). [](/windows/mixed-reality/focus-point-in-unity)</span><span class="sxs-lookup"><span data-stu-id="4113a-218">Until this bug is fixed in Windows, if applications actively set the [focus point](/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="4113a-219">Controlador inalámbrico de Xbox</span><span class="sxs-lookup"><span data-stu-id="4113a-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="4113a-220">El controlador inalámbrico S de Xbox debe actualizarse para poder usarse con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4113a-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="4113a-221">Asegúrese de que [está actualizado antes](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) de intentar emparejar el controlador con un HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4113a-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="4113a-222">Si reinicia el HoloLens mientras el controlador inalámbrico de Xbox está conectado, el controlador no se volverá a conectar automáticamente a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4113a-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="4113a-223">La luz del botón Guía parpadeará lentamente hasta que el controlador se apague después de 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="4113a-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="4113a-224">Para volver a conectar el controlador inmediatamente, apague el controlador manteniendo presionado el botón Guía hasta que se apague la luz.</span><span class="sxs-lookup"><span data-stu-id="4113a-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="4113a-225">Cuando vuelva a encender el controlador, se volverá a conectar a HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4113a-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="4113a-226">Si el HoloLens entra en espera mientras el controlador inalámbrico de Xbox está conectado, cualquier entrada del controlador reactivará el HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4113a-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="4113a-227">Para evitarlo, apague el controlador cuando haya terminado de usarlo.</span><span class="sxs-lookup"><span data-stu-id="4113a-227">You can prevent this by powering off your controller when you are done using it.</span></span>

