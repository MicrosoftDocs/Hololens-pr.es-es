---
title: Escenarios comunes de implementación de infraestructura
description: Obtenga información sobre algunos de los escenarios de implementación más comunes basados en diferentes implementaciones de infraestructura para la realidad mixta.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310158"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="e4906-104">Introducción a los escenarios comunes de implementación de infraestructura</span><span class="sxs-lookup"><span data-stu-id="e4906-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="e4906-105">Esta información siguiente proporciona información general sobre la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar Microsoft HoloLens 2 dispositivos dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="e4906-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="e4906-106">A menudo, la forma en que administra los dispositivos y cómo acceder a los recursos de la organización viene determinada en gran medida por factores ya establecidos.</span><span class="sxs-lookup"><span data-stu-id="e4906-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="e4906-107">En función de la infraestructura existente, le invitamos a revisar el estilo común de administración de dispositivos en los escenarios siguientes y probar nuestras guías para implementar en el escenario que se acote a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="e4906-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="e4906-108">Escenarios</span><span class="sxs-lookup"><span data-stu-id="e4906-108">Scenarios</span></span>

<span data-ttu-id="e4906-109">El diagrama siguiente representa tres escenarios típicos para HoloLens 2 implementaciones.</span><span class="sxs-lookup"><span data-stu-id="e4906-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
<span data-ttu-id="e4906-110">![Diagrama de escenarios](images/scenarios.jpg)</span><span class="sxs-lookup"><span data-stu-id="e4906-110">![Scenarios diagram](images/scenarios.jpg)</span></span>

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="e4906-111">Escenario A: Implementación en dispositivos de conexión a la nube</span><span class="sxs-lookup"><span data-stu-id="e4906-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="e4906-112">HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="e4906-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="e4906-113">No se accede a los recursos corporativos o se puede limitar a través de VPN.</span><span class="sxs-lookup"><span data-stu-id="e4906-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="e4906-114">Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="e4906-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="e4906-115">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="e4906-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="e4906-116">Wi-Fi las redes están totalmente abiertas a Internet y a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="e4906-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="e4906-117">Azure AD unirse a mobile Administración de dispositivos (MDM) Auto Enrollment--MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="e4906-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="e4906-118">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e4906-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="e4906-119">Se admiten uno o varios usuarios por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e4906-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="e4906-120">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="e4906-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="e4906-121">Una o varias aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="e4906-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="e4906-122">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="e4906-122">Common Challenges</span></span>
   * <span data-ttu-id="e4906-123">Determinar qué configuraciones de MDM se aplicarán al HoloLens 2 en función de los requisitos del escenario.</span><span class="sxs-lookup"><span data-stu-id="e4906-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="e4906-124">Para obtener una guía de implementación similar al escenario A revise nuestra guía de cloud [connected HoloLens 2 con Remote Assist](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e4906-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e4906-125">Guía de implementación: conexión a la nube HoloLens 2 con Remote Assist</span><span class="sxs-lookup"><span data-stu-id="e4906-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="e4906-126">Escenario B: Implementación dentro de la red de la organización</span><span class="sxs-lookup"><span data-stu-id="e4906-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="e4906-127">HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="e4906-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="e4906-128">Internet y los servicios en la nube pueden estar limitados.</span><span class="sxs-lookup"><span data-stu-id="e4906-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="e4906-129">Esta implementación es una implementación típica para la mayoría Windows 10 equipos.</span><span class="sxs-lookup"><span data-stu-id="e4906-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="e4906-130">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="e4906-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="e4906-131">Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="e4906-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="e4906-132">Azure AD unirse a la inscripción automática de MDM</span><span class="sxs-lookup"><span data-stu-id="e4906-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="e4906-133">MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="e4906-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="e4906-134">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e4906-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="e4906-135">Se admiten uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="e4906-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="e4906-136">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Pantalla completa de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="e4906-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="e4906-137">Una o varias aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="e4906-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="e4906-138">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="e4906-138">Common Challenges</span></span>
   * <span data-ttu-id="e4906-139">HoloLens 2 no admite la unión a AD local o SCCM.</span><span class="sxs-lookup"><span data-stu-id="e4906-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="e4906-140">Solo Azure AD unirse a MDM.</span><span class="sxs-lookup"><span data-stu-id="e4906-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="e4906-141">Actualmente, muchas empresas aún implementan equipos Windows 10 en este escenario como dispositivos unidos a AD local, administrados por System Center Administrador de configuración (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="e4906-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="e4906-142">Como HoloLens 2 es un dispositivo en primer lugar en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="e4906-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="e4906-143">Al conectarse a una red corporativa, es probable que las reglas de proxy o firewall deban ajustarse para habilitar el acceso a HoloLens 2 y a las aplicaciones que se ejecutan en ella.</span><span class="sxs-lookup"><span data-stu-id="e4906-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="e4906-144">La Wi-Fi corporativa normalmente requiere certificados para autenticar el dispositivo o el usuario en la red.</span><span class="sxs-lookup"><span data-stu-id="e4906-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="e4906-145">La infraestructura o la configuración necesarias para implementar certificados en Windows 10 dispositivos a través de MDM puede ser difícil de configurar.</span><span class="sxs-lookup"><span data-stu-id="e4906-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e4906-146">Guía de implementación: guía de HoloLens 2 corporativas con las guías de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4906-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="e4906-147">Escenario C: Implementación en un entorno sin conexión seguro</span><span class="sxs-lookup"><span data-stu-id="e4906-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="e4906-148">HoloLens 2 se implementa para su uso principalmente sin conexión sin acceso a la red o a Internet.</span><span class="sxs-lookup"><span data-stu-id="e4906-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="e4906-149">Se trata de una implementación típica para ubicaciones altamente seguras o confidenciales.</span><span class="sxs-lookup"><span data-stu-id="e4906-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="e4906-150">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="e4906-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="e4906-151">Wi-Fi conectividad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e4906-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="e4906-152">Ethernet a través de USB puede habilitarse para la conectividad LAN si es necesario.</span><span class="sxs-lookup"><span data-stu-id="e4906-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="e4906-153">No administrado.</span><span class="sxs-lookup"><span data-stu-id="e4906-153">Not Managed.</span></span>
   * <span data-ttu-id="e4906-154">Cuenta de usuario local para el inicio de sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e4906-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="e4906-155">HoloLens 2 solo admite una cuenta local.</span><span class="sxs-lookup"><span data-stu-id="e4906-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="e4906-156">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="e4906-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="e4906-157">Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="e4906-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="e4906-158">Una o varias aplicaciones se implementan a través del paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="e4906-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="e4906-159">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="e4906-159">Common Challenges</span></span>
   * <span data-ttu-id="e4906-160">Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="e4906-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="e4906-161">Los servicios en la nube no se pueden usar, por lo que se limitan las funcionalidades HoloLens 2 nube.</span><span class="sxs-lookup"><span data-stu-id="e4906-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="e4906-162">Mayor sobrecarga administrativa, ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="e4906-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="e4906-163">Para obtener una guía de implementación similar a este escenario, revise nuestra [Guía de implementación segura sin conexión](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="e4906-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e4906-164">Guía de implementación: seguridad sin conexión HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e4906-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
