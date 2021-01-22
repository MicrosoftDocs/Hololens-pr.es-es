---
title: Escenarios habituales de implementación de infraestructura
description: Obtenga información sobre algunos de los escenarios de implementación más comunes basados en distintas implementaciones de infraestructura para realidad mixta.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283631"
---
# <span data-ttu-id="42045-104">Introducción a los escenarios comunes de implementación de infraestructura</span><span class="sxs-lookup"><span data-stu-id="42045-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="42045-105">Esta siguiente información proporciona una introducción a la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar dispositivos De Microsoft HoloLens 2 en la empresa.</span><span class="sxs-lookup"><span data-stu-id="42045-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="42045-106">A menudo, la forma en que administras los dispositivos y cómo acceder a los recursos de la organización se determina en gran medida por factores ya establecidos.</span><span class="sxs-lookup"><span data-stu-id="42045-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="42045-107">En función de la infraestructura existente, te invitamos a revisar el estilo común de administración de dispositivos en los siguientes escenarios y probar nuestras guías para la implementación en el escenario que se asememe a tus necesidades.</span><span class="sxs-lookup"><span data-stu-id="42045-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="42045-108">Escenarios</span><span class="sxs-lookup"><span data-stu-id="42045-108">Scenarios</span></span>

<span data-ttu-id="42045-109">El siguiente diagrama representa tres escenarios típicos para implementaciones de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="42045-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagrama de escenarios](images/scenarios.jpg)

### <span data-ttu-id="42045-111">Escenario A: Implementar en dispositivos de conexión en la nube</span><span class="sxs-lookup"><span data-stu-id="42045-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="42045-112">HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="42045-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="42045-113">No se tiene acceso a los recursos corporativos o pueden estar limitados a través de VPN.</span><span class="sxs-lookup"><span data-stu-id="42045-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="42045-114">Esta implementación es similar a los dispositivos móviles administrados de una empresa.</span><span class="sxs-lookup"><span data-stu-id="42045-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="42045-115">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="42045-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="42045-116">Wi-Fi las redes están completamente abiertas a Internet y a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="42045-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="42045-117">Unión a Azure AD con inscripción automática de administración de dispositivos móviles (MDM): MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="42045-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="42045-118">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="42045-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="42045-119">Se admiten uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="42045-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="42045-120">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="42045-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="42045-121">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="42045-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="42045-122">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="42045-122">Common Challenges</span></span>
   * <span data-ttu-id="42045-123">Determinar qué configuraciones de MDM se deben aplicar a HoloLens 2 en función de los requisitos del escenario.</span><span class="sxs-lookup"><span data-stu-id="42045-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="42045-124">Para obtener una guía de implementación similar al escenario A, revise nuestra guía de [HoloLens 2](hololens2-cloud-connected-overview.md)conectado a la nube con asistencia remota.</span><span class="sxs-lookup"><span data-stu-id="42045-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42045-125">Guía de implementación: HoloLens 2 conectado en la nube con asistencia remota</span><span class="sxs-lookup"><span data-stu-id="42045-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="42045-126">Escenario B: Implementar dentro de la red de la organización</span><span class="sxs-lookup"><span data-stu-id="42045-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="42045-127">HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos.</span><span class="sxs-lookup"><span data-stu-id="42045-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="42045-128">Es posible que los servicios de Internet y la nube sean limitados.</span><span class="sxs-lookup"><span data-stu-id="42045-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="42045-129">Esta implementación es una implementación típica para la mayoría de los equipos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="42045-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="42045-130">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="42045-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="42045-131">Wi-Fi red es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="42045-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="42045-132">Unión a Azure AD con inscripción automática de MDM</span><span class="sxs-lookup"><span data-stu-id="42045-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="42045-133">MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="42045-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="42045-134">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="42045-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="42045-135">Se admiten uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="42045-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="42045-136">Los distintos niveles de configuración de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.</span><span class="sxs-lookup"><span data-stu-id="42045-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="42045-137">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="42045-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="42045-138">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="42045-138">Common Challenges</span></span>
   * <span data-ttu-id="42045-139">HoloLens 2 no admite la unión local a AD o SCCM.</span><span class="sxs-lookup"><span data-stu-id="42045-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="42045-140">Solo unirse a Azure AD con MDM.</span><span class="sxs-lookup"><span data-stu-id="42045-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="42045-141">Actualmente, muchas empresas siguen implementando equipos con Windows 10 en este escenario como dispositivos unidos a AD local, administrados por System Center Configuration Manager (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="42045-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="42045-142">Como HoloLens 2 es un primer dispositivo en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="42045-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="42045-143">Al conectarse a una red corporativa, es muy probable que las reglas de proxy o firewall deban ajustarse para habilitar el acceso para HoloLens 2 y las aplicaciones que se ejecutan en ella.</span><span class="sxs-lookup"><span data-stu-id="42045-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="42045-144">La Wi-Fi corporativa suele requerir certificados para autenticar el dispositivo o el usuario en la red.</span><span class="sxs-lookup"><span data-stu-id="42045-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="42045-145">La infraestructura o configuración necesaria para implementar certificados en dispositivos Windows 10 a través de MDM puede ser difícil de configurar.</span><span class="sxs-lookup"><span data-stu-id="42045-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="42045-146">Escenario C: Implementar en un entorno sin conexión seguro</span><span class="sxs-lookup"><span data-stu-id="42045-146">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="42045-147">HoloLens 2 se implementa para su uso principalmente sin conexión sin acceso a la red o a Internet.</span><span class="sxs-lookup"><span data-stu-id="42045-147">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="42045-148">Se trata de una implementación típica para ubicaciones extremadamente seguras o confidenciales.</span><span class="sxs-lookup"><span data-stu-id="42045-148">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="42045-149">Configuraciones comunes básicas</span><span class="sxs-lookup"><span data-stu-id="42045-149">Basic Common Configurations</span></span>
   * <span data-ttu-id="42045-150">Wi-Fi conectividad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="42045-150">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="42045-151">Ethernet a través de USB puede estar habilitado para la conectividad LAN si es necesario.</span><span class="sxs-lookup"><span data-stu-id="42045-151">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="42045-152">No administrado.</span><span class="sxs-lookup"><span data-stu-id="42045-152">Not Managed.</span></span>
   * <span data-ttu-id="42045-153">Cuenta de usuario local para el inicio de sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42045-153">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="42045-154">HoloLens 2 solo admite una cuenta local.</span><span class="sxs-lookup"><span data-stu-id="42045-154">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="42045-155">Los distintos niveles de configuración de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="42045-155">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="42045-156">Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="42045-156">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="42045-157">Una o más aplicaciones se implementan a través del paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="42045-157">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="42045-158">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="42045-158">Common Challenges</span></span>
   * <span data-ttu-id="42045-159">Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="42045-159">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="42045-160">Los servicios en la nube no se pueden usar, lo que limita las capacidades de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="42045-160">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="42045-161">Mayor sobrecarga administrativa, ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="42045-161">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="42045-162">Para obtener una guía de implementación similar a este escenario, consulte nuestra Guía de implementación segura [sin conexión.](hololens-common-scenarios-offline-secure.md)</span><span class="sxs-lookup"><span data-stu-id="42045-162">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42045-163">Guía de implementación: HoloLens seguro sin conexión 2</span><span class="sxs-lookup"><span data-stu-id="42045-163">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
