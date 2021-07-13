---
title: Configuración de HoloLens 2
description: Aprenda a configurar HoloLens 2 por primera vez través de una red Wi-Fi con una cuenta de Microsoft (MSA) o de Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923918"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="a2141-104">Configuración de HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a2141-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="a2141-105">La primera vez que encienda su HoloLens, se le guiará por la configuración del dispositivo, el inicio de sesión con una cuenta de usuario y la calibración de HoloLens a sus ojos.</span><span class="sxs-lookup"><span data-stu-id="a2141-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="a2141-106">En esta sección se explica la experiencia de configuración inicial de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a2141-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="a2141-107">En la siguiente sección aprenderá a trabajar con HoloLens y a interactuar con hologramas.</span><span class="sxs-lookup"><span data-stu-id="a2141-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="a2141-108">Para ir directamente a ese artículo, consulte [Familiarización con HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="a2141-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a2141-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="a2141-109">Before you start</span></span>

<span data-ttu-id="a2141-110">Antes de empezar, debe asegurarse de que cuenta con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2141-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="a2141-111">**Una conexión de red**.</span><span class="sxs-lookup"><span data-stu-id="a2141-111">**A network connection**.</span></span> <span data-ttu-id="a2141-112">Tendrá que conectar su HoloLens a una red para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="a2141-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="a2141-113">Con HoloLens 2, puede conectarse a una red Wi-Fi o a través de Ethernet (necesitará un adaptador USB-C a Ethernet).</span><span class="sxs-lookup"><span data-stu-id="a2141-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="a2141-114">La primera vez que se conecte, necesitará una red abierta o protegida por contraseña que no requiera ir a ningún sitio web ni usar certificados para conectarse.</span><span class="sxs-lookup"><span data-stu-id="a2141-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="a2141-115">[Obtenga más información sobre los sitios web que usa HoloLens](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="a2141-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="a2141-116">**Una cuenta de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a2141-116">**A Microsoft account**.</span></span> <span data-ttu-id="a2141-117">También tendrá que iniciar sesión en HoloLens con una cuenta de Microsoft (o con la cuenta profesional, si el dispositivo es propiedad de su organización).</span><span class="sxs-lookup"><span data-stu-id="a2141-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="a2141-118">Si no tiene una cuenta de Microsoft, vaya a [account.microsoft.com](https://account.microsoft.com) y configure una de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="a2141-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="a2141-119">**Un espacio seguro y bien iluminado sin peligro de accidentes**.</span><span class="sxs-lookup"><span data-stu-id="a2141-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="a2141-120">[Información sobre la salud y la seguridad](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="a2141-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="a2141-121">**Los accesorios de confort opcionales** que se incluyen con el dispositivo HoloLens, para ayudarle a conseguir el ajuste más cómodo.</span><span class="sxs-lookup"><span data-stu-id="a2141-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="a2141-122">[Más información sobre el ajuste y la comodidad](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="a2141-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="a2141-123">Configurar Windows</span><span class="sxs-lookup"><span data-stu-id="a2141-123">Set up Windows</span></span>

<span data-ttu-id="a2141-124">La primera vez que inicie HoloLens 2, lo primero que hará será configurar Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="a2141-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="a2141-125">Cuando inicie el dispositivo HoloLens, oirá música y verá un logotipo de Windows.</span><span class="sxs-lookup"><span data-stu-id="a2141-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Primera pantalla durante el primer arranque](images/01-magic-moment.png)

<span data-ttu-id="a2141-127">HoloLens 2 le guiará por los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="a2141-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="a2141-128">Seleccione el idioma.</span><span class="sxs-lookup"><span data-stu-id="a2141-128">Select your language.</span></span>

    ![Seleccionar idioma](images/04-language.png)

1. <span data-ttu-id="a2141-130">Seleccione la región.</span><span class="sxs-lookup"><span data-stu-id="a2141-130">Select your region.</span></span>

    ![Selección de una región](images/05-region.png)

1. <span data-ttu-id="a2141-132">Calibre el dispositivo HoloLens a sus ojos.</span><span class="sxs-lookup"><span data-stu-id="a2141-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="a2141-133">Si decide omitir la calibración, se le pedirá la próxima vez que inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="a2141-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="a2141-134">En primer lugar, ajustará el visor.</span><span class="sxs-lookup"><span data-stu-id="a2141-134">First, you'll adjust your visor.</span></span>
    
        ![Pantalla de selección de calibración](images/06-et-corners.png)

    2. <span data-ttu-id="a2141-136">Para calibrar, se le mostrarán un conjunto de objetivos (denominados gemas).</span><span class="sxs-lookup"><span data-stu-id="a2141-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="a2141-137">No pasa nada si parpadea o cierra los ojos durante la calibración, pero intente no mirar otros objetos de la sala o del espacio físico.</span><span class="sxs-lookup"><span data-stu-id="a2141-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="a2141-138">HoloLens usa este proceso para obtener información acerca de la posición del ojo para poder representar mejor su mundo holográfico.</span><span class="sxs-lookup"><span data-stu-id="a2141-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Ajuste para los ojos](images/07-adjust-eyes.png)

        <span data-ttu-id="a2141-140">Tras la calibración, los hologramas aparecerán correctamente incluso si el visor se desplaza por la cabeza.</span><span class="sxs-lookup"><span data-stu-id="a2141-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="a2141-141">La información de calibración se almacena localmente en el dispositivo y no está asociada a ninguna información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="a2141-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="a2141-142">Para obtener más información, consulte [Seguridad y datos de calibración](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="a2141-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![La calibración ha finalizado](images/calibration-complete.png)

1. <span data-ttu-id="a2141-144">Conéctese a Internet (seleccione Wi-Fi o la conexión Ethernet).</span><span class="sxs-lookup"><span data-stu-id="a2141-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="a2141-145">El dispositivo HoloLens establece la zona horaria automáticamente en función de la información obtenida de la red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a2141-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="a2141-146">Una vez finalizada la instalación, puede cambiar la zona horaria con la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="a2141-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Conexión a Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="a2141-148">Si avanza más allá del paso de Wi-Fi y más tarde necesita cambiar a una red diferente mientras está todavía en el proceso de configuración, puede presionar a la vez los botones de **bajar volumen** y **encendido** para volver a este paso, si ejecuta una versión de sistema operativo de octubre de 2019 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a2141-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="a2141-149">En versiones anteriores, es posible que debe [restablecer el dispositivo](hololens-recovery.md) o reiniciarlo en una ubicación en la que la red Wi-Fi no esté disponible para impedir que se conecte a ella automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a2141-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="a2141-150">Tenga en cuenta también que durante la configuración de HoloLens, hay un tiempo de espera por las credenciales de dos minutos.</span><span class="sxs-lookup"><span data-stu-id="a2141-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="a2141-151">El nombre de usuario y la contraseña se deben escribir en un intervalo de dos minutos; de lo contrario, el campo de nombre de usuario se borrará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a2141-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="a2141-152">HoloLens 2 buscará y aplicará un perfil de Autopilot si existe.</span><span class="sxs-lookup"><span data-stu-id="a2141-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="a2141-153">No se necesita ninguna acción en esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="a2141-153">No action is needed on this screen.</span></span>
 
    ![Búsqueda del perfil de Autopilot](images/autopilot-profile-search.png) 

1. <span data-ttu-id="a2141-155">Haga clic en **Aceptar** en la pantalla de licencias.</span><span class="sxs-lookup"><span data-stu-id="a2141-155">Click **Accept** on the licensing screen.</span></span>

    ![Contrato de licencia de Windows](images/windows-license-agreement.png)

1. <span data-ttu-id="a2141-157">Inicie sesión con su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="a2141-157">Sign in to your user account.</span></span> <span data-ttu-id="a2141-158">Deberá elegir entre **Es propiedad de mi trabajo o escuela** y **Es mío**.</span><span class="sxs-lookup"><span data-stu-id="a2141-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="a2141-159">Si eliges **Es propiedad de mi trabajo o escuela**, iniciarás sesión con una cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a2141-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="a2141-160">Si su organización usa Azure AD Premium y ha configurado la inscripción automática de MDM, HoloLens se inscribe automáticamente en MDM.</span><span class="sxs-lookup"><span data-stu-id="a2141-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="a2141-161">Si la organización no usa Azure AD Premium, la inscripción automática de MDM no está disponible.</span><span class="sxs-lookup"><span data-stu-id="a2141-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="a2141-162">En ese caso, debe [inscribir manualmente el dispositivo HoloLens en la administración de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="a2141-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="a2141-163">Escriba la información de la cuenta de la organización.</span><span class="sxs-lookup"><span data-stu-id="a2141-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="a2141-164">Acepte la declaración de privacidad y el contrato de licencia para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="a2141-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="a2141-165">Inicie sesión con sus credenciales de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a2141-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="a2141-166">Esto puede redirigirte a la página de inicio de sesión de tu organización.</span><span class="sxs-lookup"><span data-stu-id="a2141-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="a2141-167">Continúe configurando el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a2141-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="a2141-168">Si eliges **Es mía**, iniciarás sesión con una cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2141-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="a2141-169">Una vez completada la configuración, puede [inscribir el dispositivo HoloLens en la administración de dispositivos manualmente](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="a2141-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="a2141-170">Escriba la información de su cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a2141-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="a2141-171">Especifique la contraseña.</span><span class="sxs-lookup"><span data-stu-id="a2141-171">Enter your password.</span></span> <span data-ttu-id="a2141-172">Si tu cuenta de Microsoft requiere una [comprobación de dos pasos (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) (vínculo en inglés), completa el proceso de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a2141-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Establecimiento del usuario](images/13-device-owner.png)

1. <span data-ttu-id="a2141-174">Configure el inicio de sesión de Iris: para ello, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a2141-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="a2141-175">Pasará por una experiencia similar a la de calibración de los ojos.</span><span class="sxs-lookup"><span data-stu-id="a2141-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="a2141-176">Seleccione **Listo** cuando se complete el escaneo.</span><span class="sxs-lookup"><span data-stu-id="a2141-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="a2141-177">También puede seleccionar **Omitir** para saltar este paso.</span><span class="sxs-lookup"><span data-stu-id="a2141-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="a2141-178">![Configuración de Iris](images/setup-iris.png) ![ Finalización de la configuración de Iris](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="a2141-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="a2141-179">Configurará un PIN para iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a2141-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="a2141-180">Este PIN es específico del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a2141-180">This PIN is device specific.</span></span> 

    ![Configuración de Windows Hello](images/setup-windows-hello.png)

    ![Configuración de PIN de Windows Hello](images/windows-hello-pin.png)

    ![Configuración de Windows Hello correcta](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="a2141-184">Seleccione si desea habilitar la voz en HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a2141-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Habilitación de Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="a2141-186">Seleccione si desea habilitar la ubicación en HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a2141-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Habilitación de servicios de localización](images/setup-location-services.png)

1. <span data-ttu-id="a2141-188">Seleccione el nivel de telemetría.</span><span class="sxs-lookup"><span data-stu-id="a2141-188">Select your telemetry level.</span></span> <span data-ttu-id="a2141-189">Si es posible, habilite la telemetría opcional.</span><span class="sxs-lookup"><span data-stu-id="a2141-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="a2141-190">Esta información es de gran ayuda para el equipo de ingeniería de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2141-190">This information really helps the HoloLens engineering team.</span></span>

     ![Nivel de telemetría](images/24-telemetry.png)

1. <span data-ttu-id="a2141-192">Aprenda a usar el gesto Inicio en HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a2141-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Aprenda a usar el gesto Inicio, imagen 1](images/26-01-startmenu-learning.png)

     ![Aprenda a usar el gesto Inicio, imagen 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="a2141-195">Enhorabuena.</span><span class="sxs-lookup"><span data-stu-id="a2141-195">Congratulations!</span></span>  <span data-ttu-id="a2141-196">La configuración se ha completado y ya puede usar el dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a2141-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2141-197">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a2141-197">Next steps</span></span>

1. <span data-ttu-id="a2141-198">Empiece a interactuar inmediatamente con Mixed Reality y a recorrer Windows 10 con HoloLens: eche un vistazo a la aplicación **Recomendaciones** para ver tutoriales prácticos sobre cómo interactuar con las manos.</span><span class="sxs-lookup"><span data-stu-id="a2141-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="a2141-199">Use el gesto Inicio para ir a Inicio o diga "Ir a Inicio" y seleccione Recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="a2141-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="a2141-200">Haga clic a continuación para seguir leyendo sobre cómo usar HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a2141-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a2141-201">Familiarización con HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a2141-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
