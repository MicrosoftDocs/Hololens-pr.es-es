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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397430"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="14db2-104">Información general sobre escenarios comunes de implementación de infraestructura</span><span class="sxs-lookup"><span data-stu-id="14db2-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="14db2-105">Esta información siguiente proporciona información general sobre la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar Microsoft HoloLens 2 dispositivos dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="14db2-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="14db2-106">A menudo, la forma en que administra los dispositivos y cómo acceder a los recursos de la organización viene determinada en gran medida por factores ya establecidos.</span><span class="sxs-lookup"><span data-stu-id="14db2-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="14db2-107">En función de la infraestructura existente, le invitamos a revisar el estilo común de administración de dispositivos en los escenarios siguientes y probar nuestras guías para implementar en el escenario que se acoda a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="14db2-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="14db2-108">Escenarios</span><span class="sxs-lookup"><span data-stu-id="14db2-108">Scenarios</span></span>

<span data-ttu-id="14db2-109">El diagrama siguiente representa dos escenarios administrados típicos para HoloLens 2 implementaciones.</span><span class="sxs-lookup"><span data-stu-id="14db2-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="14db2-110">También hay un tercer escenario que permite implementaciones seguras sin conexión.</span><span class="sxs-lookup"><span data-stu-id="14db2-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="14db2-111">Escenario A: Implementación en dispositivos conectados a la nube</span><span class="sxs-lookup"><span data-stu-id="14db2-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="14db2-112">HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="14db2-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="14db2-113">No se accede a los recursos corporativos o se puede limitar a través de VPN.</span><span class="sxs-lookup"><span data-stu-id="14db2-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="14db2-114">Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="14db2-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="14db2-115">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="14db2-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="14db2-116">Wi-Fi las redes están completamente abiertas a Internet y a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="14db2-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="14db2-117">Azure AD unirse a la inscripción automática de Administración de dispositivos móviles (MDM): MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="14db2-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="14db2-118">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="14db2-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="14db2-119">Se admiten uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="14db2-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="14db2-120">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Pantalla completa de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="14db2-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="14db2-121">Una o varias aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="14db2-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="14db2-122">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="14db2-122">Common Challenges</span></span>
   * <span data-ttu-id="14db2-123">Determinar qué configuraciones de MDM se aplicarán a la HoloLens 2 en función de los requisitos del escenario.</span><span class="sxs-lookup"><span data-stu-id="14db2-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="14db2-124">[![Diagrama del escenario A ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="14db2-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="14db2-125">Para obtener una guía de implementación similar a este escenario, revise nuestra guía de la guía de implementación del entorno [conectado a la nube](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="14db2-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14db2-126">Guía de implementación del entorno conectado a la nube</span><span class="sxs-lookup"><span data-stu-id="14db2-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="14db2-127">Guía de implementación del entorno conectado a la nube (clientes externos)</span><span class="sxs-lookup"><span data-stu-id="14db2-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="14db2-128">Escenario B: Implementación dentro de la red de la organización</span><span class="sxs-lookup"><span data-stu-id="14db2-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="14db2-129">HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="14db2-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="14db2-130">Internet y los servicios en la nube pueden estar limitados.</span><span class="sxs-lookup"><span data-stu-id="14db2-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="14db2-131">Esta implementación es una implementación típica para la mayoría Windows 10 equipos.</span><span class="sxs-lookup"><span data-stu-id="14db2-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="14db2-132">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="14db2-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="14db2-133">Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="14db2-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="14db2-134">Azure AD unirse a la inscripción automática de MDM</span><span class="sxs-lookup"><span data-stu-id="14db2-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="14db2-135">MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="14db2-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="14db2-136">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="14db2-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="14db2-137">Se admiten uno o varios usuarios por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14db2-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="14db2-138">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="14db2-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="14db2-139">Una o varias aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="14db2-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="14db2-140">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="14db2-140">Common Challenges</span></span>
   * <span data-ttu-id="14db2-141">HoloLens 2 no admite la unión a AD local ni SCCM.</span><span class="sxs-lookup"><span data-stu-id="14db2-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="14db2-142">Solo Azure AD unirse a MDM.</span><span class="sxs-lookup"><span data-stu-id="14db2-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="14db2-143">En la actualidad, muchas empresas todavía implementan equipos Windows 10 en este escenario como dispositivos unidos a AD local, administrados por System Center Administrador de configuración (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="14db2-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="14db2-144">Como HoloLens 2 es un primer dispositivo en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, entre otros.</span><span class="sxs-lookup"><span data-stu-id="14db2-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="14db2-145">Al conectarse a una red corporativa, lo más probable es que las reglas de proxy o firewall deban ajustarse para permitir el acceso a HoloLens 2 y a las aplicaciones que se ejecutan en ella.</span><span class="sxs-lookup"><span data-stu-id="14db2-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="14db2-146">La Wi-Fi corporativa normalmente requiere certificados para autenticar el dispositivo o el usuario en la red.</span><span class="sxs-lookup"><span data-stu-id="14db2-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="14db2-147">La infraestructura o la configuración necesarias para implementar certificados en Windows 10 dispositivos a través de MDM puede ser difícil de configurar.</span><span class="sxs-lookup"><span data-stu-id="14db2-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="14db2-148">[![Diagrama del escenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="14db2-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="14db2-149">[![Diagrama del escenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="14db2-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="14db2-150">Para obtener una guía de implementación similar a este escenario, revise nuestra guía de guía [de implementación de red corporativa](hololens2-corp-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="14db2-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14db2-151">Guía de implementación de redes corporativas</span><span class="sxs-lookup"><span data-stu-id="14db2-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="14db2-152">Escenario C: Implementación en un entorno sin conexión seguro</span><span class="sxs-lookup"><span data-stu-id="14db2-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="14db2-153">HoloLens 2 se implementa para su uso principalmente sin conexión sin acceso a la red o a Internet.</span><span class="sxs-lookup"><span data-stu-id="14db2-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="14db2-154">Se trata de una implementación típica para ubicaciones altamente seguras o confidenciales.</span><span class="sxs-lookup"><span data-stu-id="14db2-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="14db2-155">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="14db2-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="14db2-156">Wi-Fi conectividad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="14db2-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="14db2-157">Ethernet a través de USB puede habilitarse para la conectividad LAN si es necesario.</span><span class="sxs-lookup"><span data-stu-id="14db2-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="14db2-158">No administrado.</span><span class="sxs-lookup"><span data-stu-id="14db2-158">Not Managed.</span></span>
   * <span data-ttu-id="14db2-159">Cuenta de usuario local para el inicio de sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14db2-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="14db2-160">HoloLens 2 solo admite una cuenta local.</span><span class="sxs-lookup"><span data-stu-id="14db2-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="14db2-161">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="14db2-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="14db2-162">Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="14db2-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="14db2-163">Una o varias aplicaciones se implementan a través del paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="14db2-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="14db2-164">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="14db2-164">Common Challenges</span></span>
   * <span data-ttu-id="14db2-165">Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="14db2-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="14db2-166">Los servicios en la nube no se pueden usar, por lo que se limitan las funcionalidades HoloLens 2 nube.</span><span class="sxs-lookup"><span data-stu-id="14db2-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="14db2-167">Mayor sobrecarga administrativa, ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="14db2-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="14db2-168">[![Diagrama seguro sin conexión 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="14db2-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="14db2-169">Para obtener una guía de implementación similar a este escenario, revise nuestra guía de implementación de entorno seguro [sin conexión](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="14db2-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14db2-170">Guía de implementación de entornos seguros sin conexión</span><span class="sxs-lookup"><span data-stu-id="14db2-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
