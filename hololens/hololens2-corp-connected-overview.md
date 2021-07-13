---
title: 'Guía de implementación: información general HoloLens 2 con Dynamics 365 Guides corporativos'
description: Obtenga información sobre cómo inscribir HoloLens 2 dispositivos con Dynamics 365 Guides a través de una red conectada corporativa.
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637020"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="e37f8-104">Guía de implementación: Información general HoloLens 2 con Dynamics 365 Guides corporativo</span><span class="sxs-lookup"><span data-stu-id="e37f8-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="e37f8-105">Esta guía ayudará a los profesionales de TI a planear e implementar Microsoft HoloLens 2 dispositivos con Dynamics 365 Guides (Guías) en su organización.</span><span class="sxs-lookup"><span data-stu-id="e37f8-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="e37f8-106">Esta guía es excelente para pilotos, así como para implementaciones de producción, y es similar a la guía Escenario [B:](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) Implementación dentro de la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="e37f8-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="e37f8-107">Después de probar la prueba de concepto, use esta guía para avanzar en la integración de HoloLens en su organización.</span><span class="sxs-lookup"><span data-stu-id="e37f8-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="e37f8-108">En esta guía, se explica cómo inscribir los dispositivos en la administración de dispositivos existente, aplicar licencias según sea necesario y validar que los usuarios finales pueden trabajar con una guía de Dynamics 365, así como usar aplicaciones de línea de negocio personalizadas, después de configurar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e37f8-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e37f8-109">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="e37f8-109">Prerequisites</span></span>

<span data-ttu-id="e37f8-110">La siguiente infraestructura ya debe estar en su lugar:</span><span class="sxs-lookup"><span data-stu-id="e37f8-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="e37f8-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e37f8-111">Wi-Fi</span></span>
    - <span data-ttu-id="e37f8-112">Red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="e37f8-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="e37f8-113">Autenticación de certificados basada en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e37f8-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="e37f8-114">Azure Active Directory (Azure AD) Unirse a la inscripción automática de MDM[(Azure AD suscripción P1](/azure/active-directory/fundamentals/active-directory-whatis) necesaria)</span><span class="sxs-lookup"><span data-stu-id="e37f8-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="e37f8-115">MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="e37f8-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="e37f8-116">Una o varias aplicaciones se implementan a través de MDM.</span><span class="sxs-lookup"><span data-stu-id="e37f8-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="e37f8-117">Red</span><span class="sxs-lookup"><span data-stu-id="e37f8-117">Network</span></span> 
    - <span data-ttu-id="e37f8-118">Certificados (SCEP o PKCS)</span><span class="sxs-lookup"><span data-stu-id="e37f8-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="e37f8-119">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="e37f8-119">Proxy configuration</span></span>
- <span data-ttu-id="e37f8-120">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e37f8-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="e37f8-121">Se admiten uno o varios usuarios por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e37f8-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="e37f8-122">Distintos niveles de configuraciones de bloqueo de dispositivos aplicadas en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="e37f8-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="e37f8-123">Guías de licencias y requisitos</span><span class="sxs-lookup"><span data-stu-id="e37f8-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="e37f8-124">Cuenta de Azure AD</span><span class="sxs-lookup"><span data-stu-id="e37f8-124">Azure AD account</span></span>
- <span data-ttu-id="e37f8-125">Dynamics 365 Guides aplicaciones PC y HoloLens</span><span class="sxs-lookup"><span data-stu-id="e37f8-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="e37f8-126">Dynamics 365 Guides suscripción</span><span class="sxs-lookup"><span data-stu-id="e37f8-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="e37f8-127">Microsoft Dataverse (incluido)</span><span class="sxs-lookup"><span data-stu-id="e37f8-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="e37f8-128">Power Apps (incluido)</span><span class="sxs-lookup"><span data-stu-id="e37f8-128">Power Apps (included)</span></span>
- <span data-ttu-id="e37f8-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="e37f8-129">Power BI Desktop</span></span>
- <span data-ttu-id="e37f8-130">Conectividad de red</span><span class="sxs-lookup"><span data-stu-id="e37f8-130">Network Connectivity</span></span>

<span data-ttu-id="e37f8-131">[![Diagrama de red conectada corp, fase 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e37f8-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="e37f8-132">[![Diagrama de red conectada corp, fase 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e37f8-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="e37f8-133">Esta guía le permitirá:</span><span class="sxs-lookup"><span data-stu-id="e37f8-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="e37f8-134">Preparación</span><span class="sxs-lookup"><span data-stu-id="e37f8-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="e37f8-135">Obtenga información sobre los aspectos básicos de la infraestructura HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e37f8-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="e37f8-136">Obtenga más información Azure AD y configurar uno si no lo tiene.</span><span class="sxs-lookup"><span data-stu-id="e37f8-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="e37f8-137">Obtenga información sobre la administración de identidades y cómo configurar mejor Azure AD cuentas.</span><span class="sxs-lookup"><span data-stu-id="e37f8-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="e37f8-138">Obtenga más información sobre MDM y configure con Intune si aún no tiene uno listo.</span><span class="sxs-lookup"><span data-stu-id="e37f8-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="e37f8-139">Familiarícese con la Red Wi-Fi basada en certificados.</span><span class="sxs-lookup"><span data-stu-id="e37f8-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="e37f8-140">Familiarícese con el proxy.</span><span class="sxs-lookup"><span data-stu-id="e37f8-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="e37f8-141">Comprenda cómo puede usar aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="e37f8-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="e37f8-142">Obtenga más información sobre la forma en que puede usar guías para su organización.</span><span class="sxs-lookup"><span data-stu-id="e37f8-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="e37f8-143">Configuración</span><span class="sxs-lookup"><span data-stu-id="e37f8-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="e37f8-144">Cómo crear usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="e37f8-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="e37f8-145">Configuración de la inscripción automática.</span><span class="sxs-lookup"><span data-stu-id="e37f8-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="e37f8-146">Configuración de certificados Wi-Fi perfiles para la conectividad de Wi-Fi corporativa.</span><span class="sxs-lookup"><span data-stu-id="e37f8-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="e37f8-147">Upload y asignar paquetes de aplicaciones de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="e37f8-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="e37f8-148">Configuración Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="e37f8-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="e37f8-149">Configuración del modo de pantalla completa (opcional).</span><span class="sxs-lookup"><span data-stu-id="e37f8-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="e37f8-150">Configuración de WDAC (opcional).</span><span class="sxs-lookup"><span data-stu-id="e37f8-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="e37f8-151">Implementar</span><span class="sxs-lookup"><span data-stu-id="e37f8-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="e37f8-152">Valide la inscripción a través del dispositivo y MDM.</span><span class="sxs-lookup"><span data-stu-id="e37f8-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="e37f8-153">Valide Wi-Fi certificados.</span><span class="sxs-lookup"><span data-stu-id="e37f8-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="e37f8-154">Valide la instalación de la aplicación lob.</span><span class="sxs-lookup"><span data-stu-id="e37f8-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="e37f8-155">Valide las guías mediante la creación y el funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="e37f8-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="e37f8-156">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="e37f8-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="e37f8-157">Actualice HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e37f8-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="e37f8-158">Cómo actualizar guías (almacenar aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="e37f8-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="e37f8-159">Actualización de aplicaciones de LOB.</span><span class="sxs-lookup"><span data-stu-id="e37f8-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="e37f8-160">Plan de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e37f8-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="e37f8-161">Crear un plan de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e37f8-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="e37f8-162">Opciones de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e37f8-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="e37f8-163">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e37f8-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="e37f8-164">Implementación conectada corporativa: preparación</span><span class="sxs-lookup"><span data-stu-id="e37f8-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
