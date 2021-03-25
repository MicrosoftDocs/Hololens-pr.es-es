---
title: 'Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365: información general'
description: Obtenga información sobre cómo inscribir dispositivos HoloLens 2 con guías de Dynamics 365 a través de una red conectada corporativa.
keywords: HoloLens, administración, con conexión corporativa, Guías de Dynamics 365, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448627"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="eba66-104">Guía de implementación: HoloLens conectado corporativo 2 con guías de Dynamics 365: información general</span><span class="sxs-lookup"><span data-stu-id="eba66-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="eba66-105">Esta guía ayudará a los profesionales de TI a planear e implementar dispositivos de Microsoft HoloLens 2 con guías de Dynamics 365 en su organización.</span><span class="sxs-lookup"><span data-stu-id="eba66-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="eba66-106">Esta guía es ideal para pilotos, así como para implementaciones de producción y es similar a la Guía de red de escenario [B: Implementar](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="eba66-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="eba66-107">Después de probar la prueba de concepto, use esta guía para avanzar en la integración de HoloLens en su organización.</span><span class="sxs-lookup"><span data-stu-id="eba66-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="eba66-108">En esta guía, se explica cómo inscribir los dispositivos en la administración de dispositivos existente, aplicar licencias según sea necesario y validar que los usuarios finales puedan operar una Guía de Dynamics 365, así como usar aplicaciones de línea de negocio personalizadas, después de configurar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eba66-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="eba66-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="eba66-109">Prerequisites</span></span>

<span data-ttu-id="eba66-110">La siguiente infraestructura ya debe estar en su lugar:</span><span class="sxs-lookup"><span data-stu-id="eba66-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="eba66-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="eba66-111">Wi-Fi</span></span>
    - <span data-ttu-id="eba66-112">Red corporativa interna con acceso a recursos internos y acceso limitado a internet o servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="eba66-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="eba66-113">Autenticación de certificados basada en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="eba66-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="eba66-114">Azure Active Directory (Azure AD) Únase a la inscripción automática mdm (se necesita[una suscripción a Azure AD P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="eba66-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="eba66-115">Mdm (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="eba66-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="eba66-116">Una o varias aplicaciones se implementan a través de MDM.</span><span class="sxs-lookup"><span data-stu-id="eba66-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="eba66-117">Red</span><span class="sxs-lookup"><span data-stu-id="eba66-117">Network</span></span> 
    - <span data-ttu-id="eba66-118">Certificados (SCEP o PKCS)</span><span class="sxs-lookup"><span data-stu-id="eba66-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="eba66-119">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="eba66-119">Proxy configuration</span></span>
- <span data-ttu-id="eba66-120">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="eba66-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="eba66-121">Se admiten usuarios individuales o múltiples por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eba66-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="eba66-122">Distintos niveles de configuraciones de bloqueo de dispositivos aplicadas en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="eba66-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="eba66-123">Guías de licencias y requisitos</span><span class="sxs-lookup"><span data-stu-id="eba66-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="eba66-124">Cuenta de Azure AD</span><span class="sxs-lookup"><span data-stu-id="eba66-124">Azure AD account</span></span>
- <span data-ttu-id="eba66-125">Dynamics 365 Guía aplicaciones PC y HoloLens</span><span class="sxs-lookup"><span data-stu-id="eba66-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="eba66-126">Suscripción a Guías de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="eba66-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="eba66-127">Microsoft Dataverse (incluido)</span><span class="sxs-lookup"><span data-stu-id="eba66-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="eba66-128">Power Apps (incluido)</span><span class="sxs-lookup"><span data-stu-id="eba66-128">Power Apps (included)</span></span>
- <span data-ttu-id="eba66-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="eba66-129">Power BI Desktop</span></span>
- <span data-ttu-id="eba66-130">Conectividad de red</span><span class="sxs-lookup"><span data-stu-id="eba66-130">Network Connectivity</span></span>

![Diagrama de red conectada corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="eba66-132">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="eba66-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="eba66-133">Preparar</span><span class="sxs-lookup"><span data-stu-id="eba66-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="eba66-134">Obtenga información sobre los aspectos esenciales de la infraestructura para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="eba66-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="eba66-135">Obtenga más información sobre Azure AD y configure uno si no lo tiene.</span><span class="sxs-lookup"><span data-stu-id="eba66-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="eba66-136">Obtenga información sobre la administración de identidades y cómo configurar mejor las cuentas de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="eba66-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="eba66-137">Obtén más información sobre MDM y configura con Intune si aún no tienes uno listo.</span><span class="sxs-lookup"><span data-stu-id="eba66-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="eba66-138">Familiarícese con el Wi-Fi basado en certificados.</span><span class="sxs-lookup"><span data-stu-id="eba66-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="eba66-139">Familiarícese con proxy.</span><span class="sxs-lookup"><span data-stu-id="eba66-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="eba66-140">Comprenda cómo puede usar line of business apps.</span><span class="sxs-lookup"><span data-stu-id="eba66-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="eba66-141">Obtenga más información sobre la forma en que puede usar guías para su organización.</span><span class="sxs-lookup"><span data-stu-id="eba66-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="eba66-142">Configurar</span><span class="sxs-lookup"><span data-stu-id="eba66-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="eba66-143">Cómo crear usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="eba66-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="eba66-144">Cómo configurar la inscripción automática.</span><span class="sxs-lookup"><span data-stu-id="eba66-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="eba66-145">Cómo configurar Wi-Fi certificados y perfiles para la conectividad Wi-Fi corporativa.</span><span class="sxs-lookup"><span data-stu-id="eba66-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="eba66-146">Cargar y asignar paquetes de aplicaciones de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="eba66-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="eba66-147">Configurar guías de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="eba66-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="eba66-148">Cómo configurar el modo de pantalla completa (opcional).</span><span class="sxs-lookup"><span data-stu-id="eba66-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="eba66-149">Cómo configurar WDAC (opcional).</span><span class="sxs-lookup"><span data-stu-id="eba66-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="eba66-150">Implementar</span><span class="sxs-lookup"><span data-stu-id="eba66-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="eba66-151">Validar la inscripción a través del dispositivo y MDM.</span><span class="sxs-lookup"><span data-stu-id="eba66-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="eba66-152">Validar Wi-Fi certificados.</span><span class="sxs-lookup"><span data-stu-id="eba66-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="eba66-153">Validar la instalación de la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="eba66-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="eba66-154">Validar guías a través de la creación y el funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="eba66-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="eba66-155">Mantener</span><span class="sxs-lookup"><span data-stu-id="eba66-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="eba66-156">Actualizar HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="eba66-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="eba66-157">Cómo actualizar guías (almacenar aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="eba66-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="eba66-158">Cómo actualizar aplicaciones de LOB.</span><span class="sxs-lookup"><span data-stu-id="eba66-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="eba66-159">Plan de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="eba66-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="eba66-160">Crear un plan de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="eba66-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="eba66-161">Opciones de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="eba66-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="eba66-162">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="eba66-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="eba66-163">Implementación conectada corporativa: preparar</span><span class="sxs-lookup"><span data-stu-id="eba66-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
