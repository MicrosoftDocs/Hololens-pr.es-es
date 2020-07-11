---
title: Configurar HoloLens en un entorno comercial
description: Más información sobre cómo implementar y administrar HoloLens en entornos empresariales.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865569"
---
# <span data-ttu-id="dbc3f-103">Implementar HoloLens en un entorno comercial</span><span class="sxs-lookup"><span data-stu-id="dbc3f-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="dbc3f-104">Puedes implementar y configurar HoloLens a escala en una configuración comercial.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="dbc3f-105">En este artículo se proporcionan instrucciones para implementar dispositivos HoloLens en un entorno comercial.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="dbc3f-106">En esta guía se presupone la familiaridad básica con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="dbc3f-107">Sigue la [Guía](hololens1-setup.md) introducción para configurar HoloLens por primera vez.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="dbc3f-108">En este documento también se supone que los equipos de seguridad han evaluado la función HoloLens como segura para usarse en la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span>  
> [!Tip]
> <span data-ttu-id="dbc3f-109">Más información sobre la [seguridad de HoloLens](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dbc3f-109">Learn more about [HoloLens security](security-overview.md).</span></span>
> <span data-ttu-id="dbc3f-110">Para obtener la seguridad de HoloLens (1ª generación), consulta [esta pregunta frecuente](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="dbc3f-110">For HoloLens (1st Gen) security please review [this FAQ](hololens1-faq-security.md).</span></span>

## <span data-ttu-id="dbc3f-111">Información general sobre los pasos de implementación</span><span class="sxs-lookup"><span data-stu-id="dbc3f-111">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="dbc3f-112">Determinar qué características necesita</span><span class="sxs-lookup"><span data-stu-id="dbc3f-112">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="dbc3f-113">Determinar qué licencias se necesitan</span><span class="sxs-lookup"><span data-stu-id="dbc3f-113">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="dbc3f-114">[Configura tu red para HoloLens](hololens-commercial-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="dbc3f-114">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="dbc3f-115">Esta sección incluye los requisitos de ancho de banda, la dirección URL y los puertos que deben permitirse en el Firewall; Guía de Azure AD; Guía de administración de dispositivos móviles (MDM); Guía de implementación y administración de aplicaciones; y la guía de certificados.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-115">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="dbc3f-116">Faculta [Configurar HoloLens con un paquete de aprovisionamiento](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="dbc3f-116">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="dbc3f-117">Dispositivo de inscripción</span><span class="sxs-lookup"><span data-stu-id="dbc3f-117">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="dbc3f-118">Configurar actualizaciones de HoloLens basadas en anillos</span><span class="sxs-lookup"><span data-stu-id="dbc3f-118">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="dbc3f-119">Habilitar el cifrado de dispositivo de Bitlocker para HoloLens</span><span class="sxs-lookup"><span data-stu-id="dbc3f-119">Enable Bitlocker device encryption for HoloLens</span></span>](security-encryption-data-protection.md)

## <span data-ttu-id="dbc3f-120">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-120">Step 1.</span></span> <span data-ttu-id="dbc3f-121">Determinar lo que necesita</span><span class="sxs-lookup"><span data-stu-id="dbc3f-121">Determine what you need</span></span>

<span data-ttu-id="dbc3f-122">Antes de implementar HoloLens en el entorno, es importante determinar primero qué características, aplicaciones y tipo de identidades son necesarias.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-122">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="dbc3f-123">También es importante asegurarse de que el equipo de seguridad haya aprobado el uso de HoloLens en la red de la empresa.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-123">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="dbc3f-124">Para obtener más información sobre seguridad, consulta [HoloLens2 seguridad](security-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="dbc3f-124">Please see [HoloLens2 security](security-overview.md) for additional security information.</span></span>

### <span data-ttu-id="dbc3f-125">Tipo de identidad</span><span class="sxs-lookup"><span data-stu-id="dbc3f-125">Type of Identity</span></span>

<span data-ttu-id="dbc3f-126">Determine el tipo de identidad que se usará para iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-126">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="dbc3f-127">**Cuentas locales:** Esta cuenta es local para el dispositivo (como una cuenta de administrador local en un equipo con Windows).</span><span class="sxs-lookup"><span data-stu-id="dbc3f-127">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="dbc3f-128">Esto permitirá que solo 1 usuario inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-128">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="dbc3f-129">**MSA:** Esta es una cuenta personal (como Outlook, hotmail, gmail, Yahoo, etc.) Esto permitirá que solo 1 usuario inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-129">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="dbc3f-130">**Cuentas de Azure Active Directory (Azure ad):** Esta es una cuenta creada en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-130">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="dbc3f-131">Esto otorga a su corporación la capacidad de administrar el dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-131">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="dbc3f-132">Esto permitirá que varios usuarios inicien sesión en el dispositivo de la primera generación comercial de HoloLens/HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-132">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="dbc3f-133">Para obtener información más detallada sobre los tipos de identidad, visita nuestro artículo de [identidad de HoloLens](hololens-identity.md) .</span><span class="sxs-lookup"><span data-stu-id="dbc3f-133">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="dbc3f-134">Tipo de características</span><span class="sxs-lookup"><span data-stu-id="dbc3f-134">Type of Features</span></span>

<span data-ttu-id="dbc3f-135">Los requisitos de tu característica determinarán qué HoloLens necesitas.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-135">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="dbc3f-136">Una característica popular que vemos implementada en entornos de cliente con frecuencia es el modo de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-136">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="dbc3f-137">[Aquí](hololens-commercial-features.md)puedes encontrar una lista de características clave de hololens y las ediciones de HoloLens que las admiten.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-137">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="dbc3f-138">¿Qué es el modo de pantalla completa?</span><span class="sxs-lookup"><span data-stu-id="dbc3f-138">What is Kiosk Mode?</span></span>**

<span data-ttu-id="dbc3f-139">El modo de pantalla completa es una forma de restringir las aplicaciones a las que tiene acceso los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-139">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="dbc3f-140">Esto significa que los usuarios solo tendrán permiso para acceder a determinadas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-140">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="dbc3f-141">¿Qué modo de quiosco necesito?</span><span class="sxs-lookup"><span data-stu-id="dbc3f-141">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="dbc3f-142">Existen dos tipos de modos de pantalla completa: una sola aplicación y varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-142">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="dbc3f-143">El modo de pantalla única de la aplicación permite que el usuario solo tenga acceso a una aplicación mientras que el modo quiosco de varias aplicaciones permite a los usuarios acceder a varias aplicaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-143">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="dbc3f-144">Para determinar qué modo de pantalla completa es adecuado para su corporación, deben contestarse las dos preguntas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dbc3f-144">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="dbc3f-145">¿Diferentes usuarios necesitan diferentes experiencias y restricciones?</span><span class="sxs-lookup"><span data-stu-id="dbc3f-145">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="dbc3f-146">Considere el ejemplo siguiente: el usuario A es un ingeniero de servicio de campo que solo necesita acceso a asistencia remota.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-146">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="dbc3f-147">El usuario B es un aprendiz que solo necesita acceder a las guías.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-147">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="dbc3f-148">En caso afirmativo, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dbc3f-148">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="dbc3f-149">Cuentas de Azure AD como método para iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-149">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="dbc3f-150">Modo quiosco **de varias aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="dbc3f-150">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="dbc3f-151">En caso de no hacerlo, continúa con la pregunta dos</span><span class="sxs-lookup"><span data-stu-id="dbc3f-151">If no, continue to question two</span></span>
1. **<span data-ttu-id="dbc3f-152">¿Necesita una experiencia de varias aplicaciones?</span><span class="sxs-lookup"><span data-stu-id="dbc3f-152">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="dbc3f-153">Si el valor es sí, se necesita la pantalla completa **de varias aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="dbc3f-153">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="dbc3f-154">Si su respuesta a las preguntas 1 y 2 no es así, puede usar el modo de pantalla completa **de una sola aplicación** .</span><span class="sxs-lookup"><span data-stu-id="dbc3f-154">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="dbc3f-155">Cómo configurar el modo de pantalla completa:</span><span class="sxs-lookup"><span data-stu-id="dbc3f-155">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="dbc3f-156">Hay dos formas principales ([paquetes de aprovisionamiento](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) y [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) para implementar el modo de pantalla completa para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-156">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="dbc3f-157">Estas opciones se tratarán más adelante en el documento; sin embargo, puedes usar los vínculos anteriores para ir a las secciones respectivas de este documento.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-157">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="dbc3f-158">Escenarios específicos de aplicaciones y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dbc3f-158">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="dbc3f-159">La mayoría de los pasos que se encuentran en este documento también se aplicarán a las siguientes aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="dbc3f-159">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="dbc3f-160">Aplicación</span><span class="sxs-lookup"><span data-stu-id="dbc3f-160">App</span></span> | <span data-ttu-id="dbc3f-161">Escenarios específicos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dbc3f-161">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="dbc3f-162">Asistencia remota</span><span class="sxs-lookup"><span data-stu-id="dbc3f-162">Remote Assist</span></span> | [<span data-ttu-id="dbc3f-163">Comunicación entre inquilinos</span><span class="sxs-lookup"><span data-stu-id="dbc3f-163">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="dbc3f-164">Guías</span><span class="sxs-lookup"><span data-stu-id="dbc3f-164">Guides</span></span>  | *<span data-ttu-id="dbc3f-165">Próximamente</span><span class="sxs-lookup"><span data-stu-id="dbc3f-165">Coming Soon</span></span>* |
|<span data-ttu-id="dbc3f-166">Aplicaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="dbc3f-166">Custom Apps</span></span> | *<span data-ttu-id="dbc3f-167">Próximamente</span><span class="sxs-lookup"><span data-stu-id="dbc3f-167">Coming Soon</span></span>* |

### <span data-ttu-id="dbc3f-168">Determinar el método de inscripción</span><span class="sxs-lookup"><span data-stu-id="dbc3f-168">Determine your enrollment method</span></span>

1. <span data-ttu-id="dbc3f-169">Inscripción en masa con un token de seguridad en un paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-169">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="dbc3f-170">Ventajas: este es el enfoque más automatizado </span><span class="sxs-lookup"><span data-stu-id="dbc3f-170">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="dbc3f-171">Cons: toma la configuración inicial del servidor</span><span class="sxs-lookup"><span data-stu-id="dbc3f-171">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="dbc3f-172">Inscriba automáticamente en el inicio de sesión de usuario.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-172">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="dbc3f-173">Ventajas: enfoque más fácil</span><span class="sxs-lookup"><span data-stu-id="dbc3f-173">Pros: easiest approach</span></span>  
  <span data-ttu-id="dbc3f-174">Cons: los usuarios deberán completar la configuración una vez que se haya aplicado el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-174">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="dbc3f-175">_no recomendado_ : inscriba manualmente después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-175">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="dbc3f-176">Ventajas: posible inscripción después de la configuración</span><span class="sxs-lookup"><span data-stu-id="dbc3f-176">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="dbc3f-177">Cons: la mayoría de los métodos y los dispositivos manuales no se pueden administrar de forma centralizada hasta que se inscriban de forma manual.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-177">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="dbc3f-178">Puede encontrar más información [aquí](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="dbc3f-178">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="dbc3f-179">Determinar si necesita crear un paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="dbc3f-179">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="dbc3f-180">Existen dos métodos para configurar un dispositivo HoloLens (paquetes de aprovisionamiento y MDMs).</span><span class="sxs-lookup"><span data-stu-id="dbc3f-180">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="dbc3f-181">Te sugerimos que uses tu MDM para configurar el dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-181">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="dbc3f-182">Sin embargo, hay algunos escenarios en los que el uso de un paquete de aprovisionamiento es la mejor opción:</span><span class="sxs-lookup"><span data-stu-id="dbc3f-182">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="dbc3f-183">Deseas configurar HoloLens para omitir la configuración rápida (OOBE)</span><span class="sxs-lookup"><span data-stu-id="dbc3f-183">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="dbc3f-184">Tiene problemas para implementar un certificado en una red compleja.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-184">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="dbc3f-185">La mayoría de las veces, puede implementar certificados con MDM (incluso en entornos complejos).</span><span class="sxs-lookup"><span data-stu-id="dbc3f-185">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="dbc3f-186">Sin embargo, algunos escenarios requieren que los certificados se implementen a través del paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-186">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="dbc3f-187">Algunas de las configuraciones de HoloLens que se pueden aplicar en un paquete de aprovisionamiento son:</span><span class="sxs-lookup"><span data-stu-id="dbc3f-187">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="dbc3f-188">Aplicar certificados al dispositivo</span><span class="sxs-lookup"><span data-stu-id="dbc3f-188">Apply certificates to the device</span></span>
- <span data-ttu-id="dbc3f-189">Configuración de una conexión Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="dbc3f-189">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="dbc3f-190">Dudas preconfiguradas (como el idioma y la configuración regional)</span><span class="sxs-lookup"><span data-stu-id="dbc3f-190">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="dbc3f-191">(HoloLens 2) inscripción en masa en la administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="dbc3f-191">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="dbc3f-192">(HoloLens V1) Aplicar la clave para habilitar Windows Holographic para Empresas</span><span class="sxs-lookup"><span data-stu-id="dbc3f-192">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="dbc3f-193">Si decide usar paquetes de aprovisionamiento, siga [esta guía](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="dbc3f-193">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="dbc3f-194">Obtener soporte técnico</span><span class="sxs-lookup"><span data-stu-id="dbc3f-194">Get support</span></span>

<span data-ttu-id="dbc3f-195">Obtenga asistencia a través del sitio de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dbc3f-195">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="dbc3f-196">Archivar una solicitud de asistencia</span><span class="sxs-lookup"><span data-stu-id="dbc3f-196">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
