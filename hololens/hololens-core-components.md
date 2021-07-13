---
title: Planeamiento de la implementación de HoloLens 2 en un entorno comercial
description: Obtenga información sobre las necesidades básicas para implementar y administrar HoloLens en entornos empresariales, incluida la infraestructura, Azure Active Directory y la administración de dispositivos móviles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635796"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="156cb-103">Planeamiento de la implementación de HoloLens 2 en un entorno comercial</span><span class="sxs-lookup"><span data-stu-id="156cb-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="156cb-104">Información general</span><span class="sxs-lookup"><span data-stu-id="156cb-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="156cb-105">Esta información general está pensada para ayudar a los profesionales de TI a comprender las consideraciones para implementar y administrar Microsoft HoloLens 2 dispositivos dentro de una organización.</span><span class="sxs-lookup"><span data-stu-id="156cb-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="156cb-106">Para los usuarios finales del dispositivo, consulte [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started (Preparar la HoloLens 2 para empezar a usar).</span><span class="sxs-lookup"><span data-stu-id="156cb-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="156cb-107">HoloLens 2 se ejecuta en Windows 10 Holographic que proporciona a las organizaciones tecnologías sólidas, flexibles y integradas de administración de aplicaciones y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="156cb-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="156cb-108">Windows 10 Holographic admite la administración del ciclo de vida de los dispositivos de un extremo a otro para proporcionar a las empresas el control sobre sus dispositivos, datos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="156cb-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="156cb-109">La HoloLens 2 se puede incorporar fácilmente a las prácticas estándar del ciclo de vida, desde la inscripción de dispositivos, la configuración y la administración de aplicaciones hasta el mantenimiento y la retirada mediante una completa solución de administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="156cb-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="156cb-110">Los pasos y el vídeo siguientes pueden ayudarle a guiarlo a través del proceso de HoloLens 2 adopción dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="156cb-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![Paso 1](images/1green.png)| <br/> <span data-ttu-id="156cb-112">**[Escenarios de implementación comunes:](hololens-requirements.md)** comprenda los escenarios de implementación y explore los componentes principales necesarios para implementar HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="156cb-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Paso 2](images/2green.png)| <br/> <span data-ttu-id="156cb-114">**[Preparar:](#prepare)** familiarícese con los aspectos básicos de la infraestructura necesarios para HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="156cb-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Paso 3](images/3green.png) | <br/> <span data-ttu-id="156cb-116">**[Configurar:](#configure)** aprenda a configurar los componentes esenciales para una implementación basada en la nube.</span><span class="sxs-lookup"><span data-stu-id="156cb-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Paso 4](images/4green.png) | <br/> <span data-ttu-id="156cb-118">**[Implementar:](#deploy)** descubra cómo implementar los dispositivos y distribuir las aplicaciones de forma segura y eficaz.</span><span class="sxs-lookup"><span data-stu-id="156cb-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Paso 5](images/5green.png) | <br/> <span data-ttu-id="156cb-120">**[Mantener:](#maintain)** descubra lo que se necesita para mantener correctamente el estado de los dispositivos HoloLens 2 y garantizar el cumplimiento de la directiva corporativa.</span><span class="sxs-lookup"><span data-stu-id="156cb-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="156cb-121">Preparación</span><span class="sxs-lookup"><span data-stu-id="156cb-121">Prepare</span></span>

<span data-ttu-id="156cb-122">Obtenga información sobre los servicios de infraestructura esenciales necesarios para admitir el conjunto completo de HoloLens 2 funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="156cb-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="156cb-123">Componente</span><span class="sxs-lookup"><span data-stu-id="156cb-123">Component</span></span> | <span data-ttu-id="156cb-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="156cb-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="156cb-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="156cb-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="156cb-126">Proporciona administración de identidades y acceso para el HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="156cb-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="156cb-127">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="156cb-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="156cb-128">Administra HoloLens 2 dispositivos conectados al inquilino</span><span class="sxs-lookup"><span data-stu-id="156cb-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="156cb-129">Red Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="156cb-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="156cb-130">Wi-Fi está disponible y los dispositivos se pueden conectar a Internet</span><span class="sxs-lookup"><span data-stu-id="156cb-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="156cb-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="156cb-131">Configure</span></span>

<span data-ttu-id="156cb-132">Use Intune y Autopilot como soluciones poco táctiles para inscribir y configurar HoloLens 2 en el inquilino Azure AD la organización y MDM.</span><span class="sxs-lookup"><span data-stu-id="156cb-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="156cb-133">Componente</span><span class="sxs-lookup"><span data-stu-id="156cb-133">Component</span></span> | <span data-ttu-id="156cb-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="156cb-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="156cb-135">Inscripción automática</span><span class="sxs-lookup"><span data-stu-id="156cb-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="156cb-136">Después del inicio de sesión inicial, los dispositivos se registran automáticamente con Azure AD se inscriben en MDM.</span><span class="sxs-lookup"><span data-stu-id="156cb-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="156cb-137">Licencias de aplicación</span><span class="sxs-lookup"><span data-stu-id="156cb-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="156cb-138">Se puede aplicar a usuarios, grupos de usuarios o grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="156cb-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="156cb-139">Usuarios y grupos de Azure</span><span class="sxs-lookup"><span data-stu-id="156cb-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="156cb-140">Ayuda a asignar configuraciones y licencias para el HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="156cb-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="156cb-141">Implementar</span><span class="sxs-lookup"><span data-stu-id="156cb-141">Deploy</span></span>

<span data-ttu-id="156cb-142">Distribuya los HoloLens 2 dispositivos y valide su configuración.</span><span class="sxs-lookup"><span data-stu-id="156cb-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="156cb-143">Componente</span><span class="sxs-lookup"><span data-stu-id="156cb-143">Component</span></span> | <span data-ttu-id="156cb-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="156cb-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="156cb-145">Validación de inscripción</span><span class="sxs-lookup"><span data-stu-id="156cb-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="156cb-146">Validación de que el dispositivo Azure AD unido desde Configuración o Azure Portal</span><span class="sxs-lookup"><span data-stu-id="156cb-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="156cb-147">Validación de certificados</span><span class="sxs-lookup"><span data-stu-id="156cb-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="156cb-148">Comprobar la configuración y validar que se han distribuido correctamente</span><span class="sxs-lookup"><span data-stu-id="156cb-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="156cb-149">Validación de las instalaciones de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="156cb-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="156cb-150">Confirme que la aplicación está presente y trabajando en su HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="156cb-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="156cb-151">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="156cb-151">Maintain</span></span>

<span data-ttu-id="156cb-152">Use Windows Update for Business junto con el sistema MDM o el Microsoft Store para mantener actualizada la flota de HoloLens 2 y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="156cb-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="156cb-153">Componente</span><span class="sxs-lookup"><span data-stu-id="156cb-153">Component</span></span> | <span data-ttu-id="156cb-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="156cb-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="156cb-155">Actualizar HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="156cb-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="156cb-156">Configurar las actualizaciones según sea necesario a través Windows actualizaciones para empresas</span><span class="sxs-lookup"><span data-stu-id="156cb-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="156cb-157">Actualización de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="156cb-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="156cb-158">Configuración mediante el sistema MDM o la Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="156cb-158">Configure through your MDM system or the Microsoft Store</span></span>
