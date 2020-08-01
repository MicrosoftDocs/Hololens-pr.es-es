---
title: Configurar tu HoloLens 2
description: Esta guía explica la configuración por primera vez.  Necesitarás una red Wi-Fi y una cuenta de Microsoft (MSA) o de Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: a0ba32e3caff7695cd284ee3752bb91d80da2194
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903246"
---
# <span data-ttu-id="8eccd-105">Configurar tu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8eccd-105">Set up your HoloLens 2</span></span>

<span data-ttu-id="8eccd-106">La primera vez que enciendas HoloLens, se te guiará a través de la configuración del dispositivo, iniciando sesión con una cuenta de usuario y calibrando HoloLens a tus ojos.</span><span class="sxs-lookup"><span data-stu-id="8eccd-106">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="8eccd-107">En esta sección explica la experiencia de configuración inicial de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8eccd-107">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="8eccd-108">En la siguiente sección, aprenderás a trabajar con HoloLens y a interactuar con hologramas.</span><span class="sxs-lookup"><span data-stu-id="8eccd-108">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="8eccd-109">Para ir directamente a ese artículo, consulta [Introducción a HoloLens 2](hololens2-basic-usage.md).</span><span class="sxs-lookup"><span data-stu-id="8eccd-109">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <span data-ttu-id="8eccd-110">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="8eccd-110">Before you start</span></span>

<span data-ttu-id="8eccd-111">Antes de empezar, debes asegurarte de que cuentas con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8eccd-111">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="8eccd-112">**Una conexión de red**.</span><span class="sxs-lookup"><span data-stu-id="8eccd-112">**A network connection**.</span></span> <span data-ttu-id="8eccd-113">Tendrás que conectar tu HoloLens a una red para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="8eccd-113">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="8eccd-114">Con HoloLens 2, puedes conectarte a una red Wi-Fi o a través de Ethernet (necesitarás un adaptador USB-C a Ethernet).</span><span class="sxs-lookup"><span data-stu-id="8eccd-114">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="8eccd-115">La primera vez que te conectes, necesitarás una red abierta o protegida por contraseña que no requiera ir a ningún sitio web ni usar certificados para conectarse.</span><span class="sxs-lookup"><span data-stu-id="8eccd-115">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="8eccd-116">[Más información sobre los sitios web que HoloLens usa](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="8eccd-116">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="8eccd-117">**Una cuenta de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="8eccd-117">**A Microsoft account**.</span></span> <span data-ttu-id="8eccd-118">También tendrás que iniciar sesión en HoloLens con una cuenta de Microsoft (o con tu cuenta profesional, si el dispositivo es propiedad de tu organización).</span><span class="sxs-lookup"><span data-stu-id="8eccd-118">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="8eccd-119">Si no dispones de una cuenta de Microsoft, ve a [account.microsoft.com](https://account.microsoft.com) y crea una de manera gratuita.</span><span class="sxs-lookup"><span data-stu-id="8eccd-119">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="8eccd-120">**Un espacio seguro y bien iluminado, sin riesgo de tropezones**.</span><span class="sxs-lookup"><span data-stu-id="8eccd-120">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="8eccd-121">[Información de salud y seguridad](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span><span class="sxs-lookup"><span data-stu-id="8eccd-121">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="8eccd-122">**Los accesorios de comodidad opcionales** incluidos con tu HoloLens, que te ayudarán a obtener el ajuste más cómodo.</span><span class="sxs-lookup"><span data-stu-id="8eccd-122">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="8eccd-123">[Más información sobre el ajuste y la comodidad](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="8eccd-123">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <span data-ttu-id="8eccd-124">Configurar Windows</span><span class="sxs-lookup"><span data-stu-id="8eccd-124">Set up Windows</span></span>

<span data-ttu-id="8eccd-125">La primera vez que inicies HoloLens 2, la primera tarea es configurar Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="8eccd-125">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="8eccd-126">Cuando inicies HoloLens, oirás música y verás un logotipo de Windows.</span><span class="sxs-lookup"><span data-stu-id="8eccd-126">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Primera pantalla durante el primer arranque](images/01-magic-moment.png)

<span data-ttu-id="8eccd-128">HoloLens 2 te guiará por los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8eccd-128">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="8eccd-129">Elige tu idioma.</span><span class="sxs-lookup"><span data-stu-id="8eccd-129">Select your language.</span></span>
    ![Seleccionar idioma](images/04-language.png)

1. <span data-ttu-id="8eccd-131">Elige tu región.</span><span class="sxs-lookup"><span data-stu-id="8eccd-131">Select your region.</span></span>
    ![Seleccionar región](images/05-region.png)

1. <span data-ttu-id="8eccd-133">Calibra HoloLens a tus ojos.</span><span class="sxs-lookup"><span data-stu-id="8eccd-133">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="8eccd-134">Si optas por omitir la calibración, se te pedirá la próxima vez que inicies sesión.</span><span class="sxs-lookup"><span data-stu-id="8eccd-134">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="8eccd-135">Para calibrar, veremos un conjunto de objetivos (denominados gemas).</span><span class="sxs-lookup"><span data-stu-id="8eccd-135">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="8eccd-136">Está bien si parpadeas o cierras los ojos durante la calibración, pero intenta no mirar a otros objetos de la sala o del espacio físico.</span><span class="sxs-lookup"><span data-stu-id="8eccd-136">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="8eccd-137">HoloLens usa este proceso para obtener información acerca de la posición de tu ojo para que pueda representar mejor tu mundo holográfico.</span><span class="sxs-lookup"><span data-stu-id="8eccd-137">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="8eccd-138">Tras la calibración, los hologramas aparecerán correctamente incluso a medida que el visor se desplace en tu cabeza.</span><span class="sxs-lookup"><span data-stu-id="8eccd-138">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="8eccd-139">La información de calibración se almacena localmente en el dispositivo y no está asociada a ninguna información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="8eccd-139">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="8eccd-140">Para obtener más información, consulta [Seguridad y datos de calibración](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="8eccd-140">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Pantalla de selección de calibración](images/06-et-corners.png)

1. <span data-ttu-id="8eccd-142">Conéctate a Internet (selecciona Wi-Fi o tu conexión Ethernet).</span><span class="sxs-lookup"><span data-stu-id="8eccd-142">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="8eccd-143">HoloLens establece tu zona horaria automáticamente en función de la información obtenida de la red Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="8eccd-143">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="8eccd-144">Una vez finalizada la instalación, puedes cambiar la zona horaria con la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="8eccd-144">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Conectarte a Wi-Fi](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="8eccd-146">Si progresas más allá del paso de Wi-Fi y necesitas cambiar más tarde a una red diferente mientras te encuentras en la configuración, puedes presionar los botones **Bajar el volumen** y **Inicio/apagado** a la vez para regresar a este paso si estás ejecutando una versión de sistema operativo de octubre de 2019 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8eccd-146">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="8eccd-147">En versiones anteriores, es posible que tengas que [restablecer el dispositivo](hololens-recovery.md) o reiniciarlo en una ubicación en la que la red Wi-Fi no esté disponible para impedir que se conecte automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8eccd-147">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="8eccd-148">Ten en cuenta también que durante la configuración de HoloLens, hay un tiempo de espera de credenciales de dos minutos.</span><span class="sxs-lookup"><span data-stu-id="8eccd-148">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="8eccd-149">El nombre de usuario y la contraseña se deben escribir en un intervalo de dos minutos, de lo contrario, el campo de nombre de usuario se borrará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8eccd-149">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="8eccd-150">Inicia sesión con tu cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="8eccd-150">Sign in to your user account.</span></span> <span data-ttu-id="8eccd-151">Elige entre **Pertenece a mi trabajo o escuela** y **Es mía**.</span><span class="sxs-lookup"><span data-stu-id="8eccd-151">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="8eccd-152">Si eliges **Pertenece a mi trabajo o escuela**, inicia sesión con una cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8eccd-152">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="8eccd-153">Si tu organización usa Azure AD Premium y ha configurado la inscripción automática de MDM, HoloLens se inscribe automáticamente en MDM.</span><span class="sxs-lookup"><span data-stu-id="8eccd-153">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="8eccd-154">Si tu organización no usa Azure AD Premium, la inscripción automática de MDM no está disponible.</span><span class="sxs-lookup"><span data-stu-id="8eccd-154">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="8eccd-155">En ese caso, debes [inscribir HoloLens manualmente en la administración de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="8eccd-155">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="8eccd-156">Escribe la información de la cuenta de la organización.</span><span class="sxs-lookup"><span data-stu-id="8eccd-156">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="8eccd-157">Acepta la declaración de privacidad y el contrato de licencia para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="8eccd-157">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="8eccd-158">Inicia sesión con tus credenciales de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8eccd-158">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="8eccd-159">Esto puede redirigirte a la página de inicio de sesión de tu organización.</span><span class="sxs-lookup"><span data-stu-id="8eccd-159">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="8eccd-160">Continúa configurando el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8eccd-160">Continue setting up the device.</span></span>
    - <span data-ttu-id="8eccd-161">Si eliges **Es mía**, iniciarás sesión con una cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8eccd-161">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="8eccd-162">Una vez completada la configuración, puedes [inscribir HoloLens manualmente en la administración de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).</span><span class="sxs-lookup"><span data-stu-id="8eccd-162">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="8eccd-163">Escribe la información de tu cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8eccd-163">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="8eccd-164">Escribe tu contraseña.</span><span class="sxs-lookup"><span data-stu-id="8eccd-164">Enter your password.</span></span> <span data-ttu-id="8eccd-165">Si tu cuenta de Microsoft requiere una [verificación en dos pasos (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completa el proceso de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8eccd-165">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Establecer usuario](images/13-device-owner.png)

1. <span data-ttu-id="8eccd-167">Selecciona si quieres habilitar la voz en HoloLens 2 y si quieres enviar telemetría de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="8eccd-167">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![Habilitar Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="8eccd-169">Selecciona el nivel de telemetría.</span><span class="sxs-lookup"><span data-stu-id="8eccd-169">Select your telemetry level.</span></span> <span data-ttu-id="8eccd-170">Si puedes, habilita la telemetría completa.</span><span class="sxs-lookup"><span data-stu-id="8eccd-170">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="8eccd-171">Esta información realmente ayuda al equipo de ingeniería de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8eccd-171">This information really helps the HoloLens engineering team.</span></span>
     ![Nivel de telemetría](images/24-telemetry.png)

1. <span data-ttu-id="8eccd-173">Más información sobre cómo usar el gesto Inicio en HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8eccd-173">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![Más información sobre cómo usar el gesto Inicio, imagen 1](images/26-01-startmenu-learning.png) ![Más información sobre cómo usar el gesto Inicio, imagen 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="8eccd-175">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="8eccd-175">Congratulations!</span></span>  <span data-ttu-id="8eccd-176">La configuración se ha completado y ya puedes usar HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8eccd-176">Setup is complete and you're ready to use HoloLens!</span></span>

## <span data-ttu-id="8eccd-177">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8eccd-177">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8eccd-178">Introducción a HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8eccd-178">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
