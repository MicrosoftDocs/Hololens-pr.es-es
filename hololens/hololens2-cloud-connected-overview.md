---
title: Información general sobre las aplicaciones conectadas HoloLens 2 la nube con Remote Assist
description: Aprenda a inscribir dispositivos HoloLens 2 a través de una red conectada a la nube mediante Dynamics 365 Remote Assist.
keywords: HoloLens, administración, conexión a la nube, Remote Assist, AAD, Azure AD, MDM, Mobile Administración de dispositivos
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923540"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="38dde-104">Guía de implementación: información general HoloLens 2 conexión a la nube con Remote Assist: información general</span><span class="sxs-lookup"><span data-stu-id="38dde-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="38dde-105">Esta guía ayudará a los profesionales de TI a planear e implementar Microsoft HoloLens 2 dispositivos con Remote Assist en su organización.</span><span class="sxs-lookup"><span data-stu-id="38dde-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="38dde-106">Esto servirá como modelo para implementaciones de prueba de concepto en su organización en una variedad de HoloLens 2 casos de uso.</span><span class="sxs-lookup"><span data-stu-id="38dde-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="38dde-107">La configuración es similar a [Escenario A: Implementación en dispositivos de conexión a la nube.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="38dde-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="38dde-108">Durante la guía, se explica cómo inscribir los dispositivos en la administración de dispositivos, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar inmediatamente Remote Assist la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38dde-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="38dde-109">Para ello, remos por los elementos importantes de la infraestructura necesarios para configurarse y ejecutarse, logrando la implementación a escala con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="38dde-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="38dde-110">No se aplicarán otras restricciones o configuraciones de dispositivos en esta guía; sin embargo, le recomendamos que explore esas opciones después de finalizar.</span><span class="sxs-lookup"><span data-stu-id="38dde-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38dde-111">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="38dde-111">Prerequisites</span></span>

<span data-ttu-id="38dde-112">La siguiente infraestructura debe estar en su lugar para implementar el HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="38dde-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="38dde-113">Si no es así, la configuración de Azure e Intune se incluye en esta guía:</span><span class="sxs-lookup"><span data-stu-id="38dde-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="38dde-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="38dde-114">Wi-Fi</span></span>
    - <span data-ttu-id="38dde-115">Las redes suelen estar abiertas a internet y a los servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="38dde-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="38dde-116">Azure Active Directory (Azure AD) Unirse a la inscripción automática de MDM[(Azure AD suscripción P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) necesaria)</span><span class="sxs-lookup"><span data-stu-id="38dde-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="38dde-117">MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="38dde-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="38dde-118">Una o varias aplicaciones se implementan a través de MDM.</span><span class="sxs-lookup"><span data-stu-id="38dde-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="38dde-119">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="38dde-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="38dde-120">Se admiten uno o varios usuarios por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38dde-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Escenario conectado a la nube" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="38dde-122">Más información sobre Remote Assist</span><span class="sxs-lookup"><span data-stu-id="38dde-122">Learn about Remote Assist</span></span>

<span data-ttu-id="38dde-123">Remote Assist permite el mantenimiento y la reparación colaborativos, la inspección remota, así como el uso compartido de conocimientos y el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="38dde-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="38dde-124">Al conectar a personas en distintos roles y ubicaciones, un Remote Assist puede conectarse con un colaborador remoto en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38dde-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="38dde-125">Pueden combinar vídeo, capturas de pantalla y anotaciones para resolver problemas en tiempo real incluso cuando&#39;están en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="38dde-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="38dde-126">Los colaboradores remotos pueden insertar imágenes de referencia, esquemas y otra información útil del espacio físico del técnico&#39;para que puedan hacer referencia al esquema mientras trabajan de forma rápida y sin manos en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="38dde-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="38dde-127">Remote Assist licencias y requisitos</span><span class="sxs-lookup"><span data-stu-id="38dde-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="38dde-128">Azure AD cuenta (necesaria para comprar la suscripción y asignar licencias)</span><span class="sxs-lookup"><span data-stu-id="38dde-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="38dde-129">[Remote Assist suscripción](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o Remote Assist [prueba)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="38dde-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="38dde-130">Dynamics 365 Remote Assist usuario</span><span class="sxs-lookup"><span data-stu-id="38dde-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="38dde-131">Remote Assist licencia</span><span class="sxs-lookup"><span data-stu-id="38dde-131">Remote Assist license</span></span>
- <span data-ttu-id="38dde-132">Conectividad de red</span><span class="sxs-lookup"><span data-stu-id="38dde-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="38dde-133">Usuario de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38dde-133">Microsoft Teams user</span></span>

- <span data-ttu-id="38dde-134">Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="38dde-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="38dde-135">Conectividad de red</span><span class="sxs-lookup"><span data-stu-id="38dde-135">Network connectivity</span></span>

<span data-ttu-id="38dde-136">Si planea implementar este escenario [entre](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)inquilinos, puede que necesite una licencia de Barreras de información.</span><span class="sxs-lookup"><span data-stu-id="38dde-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="38dde-137">Consulte [este artículo para](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) determinar si se requiere una licencia de Barrera de información.</span><span class="sxs-lookup"><span data-stu-id="38dde-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="38dde-138">Esta guía le permitirá:</span><span class="sxs-lookup"><span data-stu-id="38dde-138">In this guide you will:</span></span>

<span data-ttu-id="38dde-139">Preparación:</span><span class="sxs-lookup"><span data-stu-id="38dde-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="38dde-140">Obtenga información sobre los aspectos básicos de la infraestructura HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="38dde-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="38dde-141">Obtenga más información Azure AD configurar una si no&#39;la tiene.</span><span class="sxs-lookup"><span data-stu-id="38dde-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="38dde-142">Obtenga información sobre la administración de identidades y cómo configurar mejor Azure AD cuentas.</span><span class="sxs-lookup"><span data-stu-id="38dde-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="38dde-143">Obtenga más información sobre MDM y configure intune si no&#39;ya tiene uno listo.</span><span class="sxs-lookup"><span data-stu-id="38dde-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="38dde-144">Obtenga información sobre los requisitos de red de Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="38dde-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="38dde-145">Opcionalmente: VPN para conectarse a recursos de la organización</span><span class="sxs-lookup"><span data-stu-id="38dde-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="38dde-146">Configurar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38dde-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="38dde-147">Cómo crear usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="38dde-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="38dde-148">Configuración de la inscripción automática en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="38dde-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="38dde-149">Asignación de licencias de aplicación.</span><span class="sxs-lookup"><span data-stu-id="38dde-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="38dde-150">Implementación:</span><span class="sxs-lookup"><span data-stu-id="38dde-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="38dde-151">Configure la cuenta HoloLens 2 y valide la inscripción.</span><span class="sxs-lookup"><span data-stu-id="38dde-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="38dde-152">Valide que puede realizar una Remote Assist llamada.</span><span class="sxs-lookup"><span data-stu-id="38dde-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="38dde-153">Mantener:</span><span class="sxs-lookup"><span data-stu-id="38dde-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="38dde-154">Actualización de Remote Assist con la Microsoft Store aplicación.</span><span class="sxs-lookup"><span data-stu-id="38dde-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="38dde-155">Realización de un plan de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="38dde-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="38dde-156">Plan de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="38dde-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="38dde-157">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="38dde-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="38dde-158">Implementación conectada a la nube: preparación</span><span class="sxs-lookup"><span data-stu-id="38dde-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

