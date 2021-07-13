---
title: 'Guía de implementación: HoloLens 2 con conexión corporativa con Dynamics 365 Guides: implementación'
description: Aprenda a configurar implementaciones de dispositivos HoloLens 2 a través de una red conectada corporativa con Dynamics 365 Guides.
keywords: HoloLens, administración, con conexión corporativa, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Administración de dispositivos
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637071"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="82e31-104">Implementación: Guía de conexión corporativa</span><span class="sxs-lookup"><span data-stu-id="82e31-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="82e31-105">Una parte importante de cada implementación es asegurarse de que la implementación está configurada correctamente antes de probarla usted mismo para garantizar una experiencia sin problemas para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="82e31-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="82e31-106">Dado que estamos implementando el certificado de Wi-Fi a través de MDM, es necesario configurar inicialmente HoloLens e inscribir dispositivos en una red Wi-Fi abierta o en una red que no requiera el certificado.</span><span class="sxs-lookup"><span data-stu-id="82e31-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="82e31-107">Una vez que el HoloLens haya finalizado la OOBE y la inscripción, el dispositivo recibirá el certificado de red y el LOB configurados previamente y podremos validar que el dispositivo recibió ambos.</span><span class="sxs-lookup"><span data-stu-id="82e31-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="82e31-108">Después, podrá confirmar que puede crear y usar una guía de prueba.</span><span class="sxs-lookup"><span data-stu-id="82e31-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="82e31-109">Validación de inscripción</span><span class="sxs-lookup"><span data-stu-id="82e31-109">Enrollment Validation</span></span>

<span data-ttu-id="82e31-110">Ahora que todo está configurado correctamente para la Azure AD y la inscripción de MDM, el resto debería ser ahora un poco.</span><span class="sxs-lookup"><span data-stu-id="82e31-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="82e31-111">Necesitará una conexión de Wi-Fi y el dispositivo HoloLens, y una de las cuentas de usuario Azure AD configuradas previamente.</span><span class="sxs-lookup"><span data-stu-id="82e31-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="82e31-112">Si el dispositivo no está actualmente en un estado de configuración de fábrica, ahora sería un buen momento para volver a [actualizar el dispositivo.](/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="82e31-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="82e31-113">Una vez que el dispositivo esté en OOBE, deberá empezar a interactuar y seguir las indicaciones.</span><span class="sxs-lookup"><span data-stu-id="82e31-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="82e31-114">Conectar a una red Wi-Fi que no requiera certificados para unirse a la red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="82e31-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="82e31-115">Esto permitirá que el dispositivo descargue el certificado para que se utilice en el equipo de la Wi-Fi después de la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="82e31-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="82e31-116">El mensaje crítico será cuando se le pregunte **si Quién posee este HoloLens?**</span><span class="sxs-lookup"><span data-stu-id="82e31-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="82e31-117">Seleccione **My work or school owns it (Mi** trabajo o escuela es el propietario) y escriba sus Azure AD de cuenta.</span><span class="sxs-lookup"><span data-stu-id="82e31-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="82e31-118">Cuando la inscripción se realiza correctamente, se le pedirá que configure un PIN.</span><span class="sxs-lookup"><span data-stu-id="82e31-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="82e31-119">Este PIN es único para este dispositivo para este usuario.</span><span class="sxs-lookup"><span data-stu-id="82e31-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="82e31-120">También se le pedirán exámenes de Iris, datos de voz y configuración de telemetría y, por último, podrá obtener información sobre cómo abrir el menú Inicio y completar OOBE.</span><span class="sxs-lookup"><span data-stu-id="82e31-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="82e31-121">Una vez que haya pasado a Mixed Reality inicio, abra el menú Inicio con el **gesto Iniciar** que acaba de aprender.</span><span class="sxs-lookup"><span data-stu-id="82e31-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="82e31-122">Seleccione la **Configuración** y seleccione **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="82e31-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="82e31-123">La primera parte de la información que verá es el nombre del dispositivo, que para el dispositivo HoloLens 2 será HOLOLENS, seguido de una cadena &quot; &quot; de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="82e31-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="82e31-124">Tome nota de este nombre.</span><span class="sxs-lookup"><span data-stu-id="82e31-124">Take note of this name.</span></span>

    ![HoloLens 2 Configuración pantalla](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="82e31-126">Compruebe que el dispositivo se ha unido correctamente a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82e31-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="82e31-127">Hay dos maneras:</span><span class="sxs-lookup"><span data-stu-id="82e31-127">There are two ways;</span></span>

    1.  <span data-ttu-id="82e31-128">La Configuración aplicación.</span><span class="sxs-lookup"><span data-stu-id="82e31-128">The Settings app.</span></span> <span data-ttu-id="82e31-129">En **Configuración seleccione** **Cuentas Acceder** a trabajo o  ->  **escuela.**</span><span class="sxs-lookup"><span data-stu-id="82e31-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="82e31-130">En esta pantalla, puede comprobar que se inscribió correctamente; para ello, vea Conectado a &quot; nameofAAD&#39;de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82e31-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="82e31-131">Conectado por *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="82e31-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="82e31-132">Esto comprobará que el dispositivo está unido a la organización&#39;de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82e31-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="82e31-133">[Azure Portal](https://portal.azure.com/#home)</span><span class="sxs-lookup"><span data-stu-id="82e31-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="82e31-134">Vaya a **Azure Active Directory**  ->  **dispositivos todos** los  ->  **dispositivos** y busque el nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="82e31-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="82e31-135">En Tipo de combinación, se mostrará como "Azure AD Unido".</span><span class="sxs-lookup"><span data-stu-id="82e31-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="82e31-136">![Comprobar el tipo de combinación en Azure AD](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="82e31-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="82e31-137">Compruebe que el dispositivo está inscrito con MDM.</span><span class="sxs-lookup"><span data-stu-id="82e31-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="82e31-138">Hay dos maneras:</span><span class="sxs-lookup"><span data-stu-id="82e31-138">There are two ways;</span></span>

    1. <span data-ttu-id="82e31-139">En **Configuración**, seleccione **Cuentas Acceder** a trabajo o  ->  **escuela.**</span><span class="sxs-lookup"><span data-stu-id="82e31-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="82e31-140">En esta pantalla, puede comprobar que se inscribió correctamente; para ello, vea Conectado a &quot; nameofAAD&#39;de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82e31-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="82e31-141">Conectado por *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="82e31-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="82e31-142">En esta cuenta de trabajo o educativa de Access, seleccione &quot; Conectado a nameofAAD&#39;de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82e31-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="82e31-143">Conectado por yourusername@nameofAAD.onmicrosoft.com &quot; y seleccione el **botón** Información.</span><span class="sxs-lookup"><span data-stu-id="82e31-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="82e31-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span><span class="sxs-lookup"><span data-stu-id="82e31-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="82e31-145">Inicie sesión y seleccione **Dispositivos y, a** **continuación, Todos los dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="82e31-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="82e31-146">Desde aquí, puede buscar en el HoloLens dispositivo&#39;nombre.</span><span class="sxs-lookup"><span data-stu-id="82e31-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="82e31-147">Debería poder ver la lista de HoloLens en Intune.</span><span class="sxs-lookup"><span data-stu-id="82e31-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Comprobación administrada por Intune en Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="82e31-149">Wi-Fi de certificados</span><span class="sxs-lookup"><span data-stu-id="82e31-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="82e31-150">Por ahora, el dispositivo debería haber recibido el Wi-Fi certificado.</span><span class="sxs-lookup"><span data-stu-id="82e31-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="82e31-151">La validación más sencilla que puede hacer es intentar conectarse a la conexión Wi-Fi para la que&#39;ha recibido el certificado.</span><span class="sxs-lookup"><span data-stu-id="82e31-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="82e31-152">Abra la aplicación **Configuración,** vaya a **Red &amp; Wi-Fi** de Internet  ->   y seleccione la conexión Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="82e31-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="82e31-153">Una vez conectado, abra la aplicación Microsoft Edge y confirme que puede navegar a un sitio web.</span><span class="sxs-lookup"><span data-stu-id="82e31-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="82e31-154">Para confirmar que ha recibido el certificado en el dispositivo, puede usar el Administrador [de certificados](/hololens/certificate-manager).</span><span class="sxs-lookup"><span data-stu-id="82e31-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="82e31-155">Validación de la instalación de la aplicación lob</span><span class="sxs-lookup"><span data-stu-id="82e31-155">Validate LOB app install</span></span>

<span data-ttu-id="82e31-156">Para ver el progreso de la instalación de una aplicación administrada, puede ver si la aplicación está instalada o comprobar Configuración.</span><span class="sxs-lookup"><span data-stu-id="82e31-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="82e31-157">Al configurar una aplicación de LOB como una instalación necesaria para nuestro grupo, después de inscribir el HoloLens con un usuario en el grupo asignado, la aplicación se descargará automáticamente en el HoloLens.</span><span class="sxs-lookup"><span data-stu-id="82e31-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="82e31-158">Abra el menú Inicio y seleccione **Todas las aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="82e31-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="82e31-159">Dependiendo del número de aplicaciones que tenga,  puede que tenga que usar los botones subir o **bajar página.**</span><span class="sxs-lookup"><span data-stu-id="82e31-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="82e31-160">Para validar la instalación de la aplicación en el dispositivo, puede hacerlo a través de **acceso a** cuentas de Configuración profesionales o educativas; seleccione la cuenta y luego el botón Información y desplácese hacia abajo para ver diferentes configuraciones y aplicaciones aplicadas al dispositivo desde  ->    ->  MDM. </span><span class="sxs-lookup"><span data-stu-id="82e31-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="82e31-161">Para validar la instalación desde Intune, vaya a la página de estado de instalación aplicaciones -> del portal de [MEM](https://endpoint.microsoft.com/#home)  ->     -> *TheNameOfYourApp*  ->  **Device.**</span><span class="sxs-lookup"><span data-stu-id="82e31-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="82e31-162">Vea más: [Implementación de aplicaciones de Intune para HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="82e31-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="82e31-163">Validar Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="82e31-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="82e31-164">Hay modos para la aplicación Guides en HoloLens, creación y funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="82e31-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="82e31-165">Tendrá que terminar de crear una guía antes de operarla.</span><span class="sxs-lookup"><span data-stu-id="82e31-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="82e31-166">Creación de la guía</span><span class="sxs-lookup"><span data-stu-id="82e31-166">Authoring the Guide</span></span>

<span data-ttu-id="82e31-167">No es necesario hacer mucho para esta validación rápida.</span><span class="sxs-lookup"><span data-stu-id="82e31-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="82e31-168">Solo tiene que seleccionar la guía que preparó en el equipo.</span><span class="sxs-lookup"><span data-stu-id="82e31-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="82e31-169">Deberá delimitar la [guía,](/dynamics365/mixed-reality/guides/hololens-app-anchor)para una validación rápida puede usar un delimitador holográfico.</span><span class="sxs-lookup"><span data-stu-id="82e31-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="82e31-170">Después, debe colocar [los pasos y modelos](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span><span class="sxs-lookup"><span data-stu-id="82e31-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="82e31-171">Necesitará el rol **de creación para iniciar** sesión en el equipo y crear en el HoloLens.</span><span class="sxs-lookup"><span data-stu-id="82e31-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="82e31-172">El rol Operador es de solo lectura y no tiene acceso a la aplicación de PC.</span><span class="sxs-lookup"><span data-stu-id="82e31-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="82e31-173">Funcionamiento de la guía</span><span class="sxs-lookup"><span data-stu-id="82e31-173">Operating the Guide</span></span>

<span data-ttu-id="82e31-174">Una vez que los hologramas estén en su lugar, puede probar el funcionamiento de la guía.</span><span class="sxs-lookup"><span data-stu-id="82e31-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="82e31-175">Seleccionar **modo de operador**</span><span class="sxs-lookup"><span data-stu-id="82e31-175">Select **Operator mode**</span></span>
- <span data-ttu-id="82e31-176">Haga clic en los pasos de la guía.</span><span class="sxs-lookup"><span data-stu-id="82e31-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="82e31-177">Para obtener instrucciones más detalladas sobre cómo usar una guía, consulte estos recursos:</span><span class="sxs-lookup"><span data-stu-id="82e31-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="82e31-178">Introducción al funcionamiento de una guía en Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="82e31-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="82e31-179">Orientación con la tarjeta Paso como operador en Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="82e31-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="82e31-180">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="82e31-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="82e31-181">Implementación conectada corporativa: mantener</span><span class="sxs-lookup"><span data-stu-id="82e31-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
