---
title: Escenarios habituales de implementación de infraestructura
description: Obtenga información sobre algunos de los escenarios de implementación más comunes basados en distintas implementaciones de infraestructura para realidad mixta.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448498"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="74665-104">Introducción a escenarios comunes de implementación de infraestructura</span><span class="sxs-lookup"><span data-stu-id="74665-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="74665-105">Esta siguiente información proporciona una introducción a la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar dispositivos de Microsoft HoloLens 2 dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="74665-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="74665-106">A menudo, la forma de administrar los dispositivos y cómo obtener acceso a los recursos de la organización se determina en gran medida por factores que ya están en marcha.</span><span class="sxs-lookup"><span data-stu-id="74665-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="74665-107">En función de la infraestructura existente, te invitamos a revisar el estilo de administración de dispositivos común en los siguientes escenarios y probar nuestras guías para implementar en el escenario que coincida con tus necesidades.</span><span class="sxs-lookup"><span data-stu-id="74665-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="74665-108">Escenarios</span><span class="sxs-lookup"><span data-stu-id="74665-108">Scenarios</span></span>

<span data-ttu-id="74665-109">El diagrama siguiente representa tres escenarios típicos para implementaciones de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="74665-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagrama de escenarios](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="74665-111">Escenario A: Implementar en dispositivos de conexión en la nube</span><span class="sxs-lookup"><span data-stu-id="74665-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="74665-112">HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="74665-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="74665-113">Los recursos corporativos no tienen acceso o pueden estar limitados a través de VPN.</span><span class="sxs-lookup"><span data-stu-id="74665-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="74665-114">Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="74665-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="74665-115">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="74665-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="74665-116">Wi-Fi las redes suelen estar totalmente abiertas a los servicios de Internet y la nube.</span><span class="sxs-lookup"><span data-stu-id="74665-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="74665-117">Unirse a Azure AD con la inscripción automática de Administración de dispositivos móviles (MDM): MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="74665-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="74665-118">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="74665-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="74665-119">Se admiten usuarios únicos o múltiples por dispositivo</span><span class="sxs-lookup"><span data-stu-id="74665-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="74665-120">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="74665-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="74665-121">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="74665-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="74665-122">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="74665-122">Common Challenges</span></span>
   * <span data-ttu-id="74665-123">Determinación de qué configuraciones MDM se aplicarán a HoloLens 2 en función de los requisitos del escenario.</span><span class="sxs-lookup"><span data-stu-id="74665-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="74665-124">Para obtener una guía de implementación similar al escenario A revise nuestra guía para [HoloLens 2](hololens2-cloud-connected-overview.md)conectado a la nube con asistencia remota.</span><span class="sxs-lookup"><span data-stu-id="74665-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="74665-125">Guía de implementación: HoloLens 2 conectado a la nube con asistencia remota</span><span class="sxs-lookup"><span data-stu-id="74665-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="74665-126">Escenario B: Implementar dentro de la red de la organización</span><span class="sxs-lookup"><span data-stu-id="74665-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="74665-127">HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="74665-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="74665-128">Es posible que los servicios de Internet y la nube sean limitados.</span><span class="sxs-lookup"><span data-stu-id="74665-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="74665-129">Esta implementación es una implementación típica para la mayoría de los equipos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="74665-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="74665-130">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="74665-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="74665-131">Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="74665-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="74665-132">Unirse a Azure AD con la inscripción automática de MDM</span><span class="sxs-lookup"><span data-stu-id="74665-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="74665-133">Mdm (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="74665-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="74665-134">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="74665-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="74665-135">Se admiten usuarios únicos o múltiples por dispositivo</span><span class="sxs-lookup"><span data-stu-id="74665-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="74665-136">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="74665-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="74665-137">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="74665-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="74665-138">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="74665-138">Common Challenges</span></span>
   * <span data-ttu-id="74665-139">HoloLens 2 no admite la unión a AD local o SCCM.</span><span class="sxs-lookup"><span data-stu-id="74665-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="74665-140">Solo se une Azure AD con MDM.</span><span class="sxs-lookup"><span data-stu-id="74665-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="74665-141">Muchas empresas aún implementan equipos con Windows 10 en este escenario como dispositivos locales unidos a AD, administrados por System Center Configuration Manager (SCCM) y pueden no tener la infraestructura implementada o configurada para administrar dispositivos Internos de Windows 10 a través de soluciones MDM basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="74665-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="74665-142">Como HoloLens 2 es un primer dispositivo en la nube, depende en gran medida de los servicios conectados a Internet y la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, entre otros.</span><span class="sxs-lookup"><span data-stu-id="74665-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="74665-143">Al conectarse a una red corporativa, es muy probable que las reglas de proxy/firewall deban ajustarse para habilitar el acceso a HoloLens 2 y a las aplicaciones que se ejecutan en ella.</span><span class="sxs-lookup"><span data-stu-id="74665-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="74665-144">La Wi-Fi corporativa suele requerir certificados para autenticar el dispositivo o el usuario en la red.</span><span class="sxs-lookup"><span data-stu-id="74665-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="74665-145">La infraestructura o la configuración necesarias para implementar certificados en dispositivos Windows 10 a través de MDM puede ser difícil de configurar.</span><span class="sxs-lookup"><span data-stu-id="74665-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="74665-146">Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="74665-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="74665-147">Escenario C: Implementar en un entorno sin conexión seguro</span><span class="sxs-lookup"><span data-stu-id="74665-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="74665-148">HoloLens 2 se implementa para su uso principalmente sin conexión sin red ni acceso a Internet.</span><span class="sxs-lookup"><span data-stu-id="74665-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="74665-149">Se trata de una implementación típica para ubicaciones extremadamente seguras o confidenciales.</span><span class="sxs-lookup"><span data-stu-id="74665-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="74665-150">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="74665-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="74665-151">Wi-Fi conectividad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="74665-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="74665-152">Ethernet a través de USB puede estar habilitado para la conectividad de LAN si es necesario.</span><span class="sxs-lookup"><span data-stu-id="74665-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="74665-153">No administrado.</span><span class="sxs-lookup"><span data-stu-id="74665-153">Not Managed.</span></span>
   * <span data-ttu-id="74665-154">Cuenta de usuario local para el inicio de sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74665-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="74665-155">HoloLens 2 solo admite una cuenta local.</span><span class="sxs-lookup"><span data-stu-id="74665-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="74665-156">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="74665-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="74665-157">Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="74665-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="74665-158">Una o más aplicaciones se implementan a través del paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="74665-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="74665-159">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="74665-159">Common Challenges</span></span>
   * <span data-ttu-id="74665-160">Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="74665-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="74665-161">Los servicios en la nube no se pueden usar, lo que limita las capacidades de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="74665-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="74665-162">Mayor sobrecarga administrativa ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="74665-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="74665-163">Para obtener una guía de implementación similar a este escenario, consulte nuestra Guía de implementación segura [sin conexión.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="74665-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="74665-164">Guía de implementación: HoloLens seguro sin conexión 2</span><span class="sxs-lookup"><span data-stu-id="74665-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
