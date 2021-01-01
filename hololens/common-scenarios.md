---
title: Escenarios habituales de implementación de infraestructura
description: Algunos escenarios de implementación comunes basados en diferentes infraestructuras comunes
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
ms.openlocfilehash: a7d847e2d2d335f2e2388535a5cf9d5246bb330b
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253077"
---
# <span data-ttu-id="1ac20-104">Introducción a los escenarios de implementación de infraestructura comunes</span><span class="sxs-lookup"><span data-stu-id="1ac20-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="1ac20-105">Esta información proporciona una descripción general de la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar dispositivos de Microsoft HoloLens 2 dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="1ac20-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="1ac20-106">A menudo, la forma en que se administran los dispositivos y el acceso a los recursos de la organización vienen determinadas en gran medida por factores ya instalados.</span><span class="sxs-lookup"><span data-stu-id="1ac20-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="1ac20-107">En función de la infraestructura existente, le invitamos a revisar el estilo de administración de dispositivos común en los siguientes escenarios, y probar nuestras guías para implementar en el escenario que se ajuste a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="1ac20-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="1ac20-108">Escenarios</span><span class="sxs-lookup"><span data-stu-id="1ac20-108">Scenarios</span></span>

<span data-ttu-id="1ac20-109">El diagrama siguiente representa tres escenarios típicos para las implementaciones de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1ac20-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![Diagrama de escenarios](images/scenarios.jpg)

### <span data-ttu-id="1ac20-111">Escenario A: implementar en dispositivos de conexión en la nube</span><span class="sxs-lookup"><span data-stu-id="1ac20-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="1ac20-112">HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="1ac20-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="1ac20-113">No se puede acceder a los recursos corporativos o pueden estar limitados a través de VPN.</span><span class="sxs-lookup"><span data-stu-id="1ac20-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="1ac20-114">Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="1ac20-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="1ac20-115">Configuraciones básicas comunes</span><span class="sxs-lookup"><span data-stu-id="1ac20-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="1ac20-116">Las redes Wi-Fi suelen estar totalmente abiertas a Internet y a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="1ac20-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="1ac20-117">Unirse a Azure AD con inscripción automática de MDM: MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="1ac20-117">Azure AD Join with MDM Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="1ac20-118">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="1ac20-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="1ac20-119">Compatible con uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="1ac20-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="1ac20-120">Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierto a la única.</span><span class="sxs-lookup"><span data-stu-id="1ac20-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="1ac20-121">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="1ac20-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="1ac20-122">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="1ac20-122">Common Challenges</span></span>
   * <span data-ttu-id="1ac20-123">Determinando las configuraciones de MDM que se aplicarán a HoloLens 2 en función de los requisitos del escenario.</span><span class="sxs-lookup"><span data-stu-id="1ac20-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="1ac20-124">Para obtener una guía de implementación similar a la del escenario a, revise nuestra guía de [HoloLens 2 conectada en la nube con asistencia remota](hololens2-cloud-connected-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1ac20-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1ac20-125">Guía de implementación: HoloLens 2 conectado en la nube con asistencia remota</span><span class="sxs-lookup"><span data-stu-id="1ac20-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="1ac20-126">Escenario B: implementar dentro de la red de su organización</span><span class="sxs-lookup"><span data-stu-id="1ac20-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="1ac20-127">HoloLens 2 se ha implementado para usarlo principalmente en la red corporativa con acceso a recursos internos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="1ac20-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="1ac20-128">Es posible que los servicios de Internet y de nube estén limitados.</span><span class="sxs-lookup"><span data-stu-id="1ac20-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="1ac20-129">Esta implementación es una implementación típica de la mayoría de equipos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1ac20-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="1ac20-130">Configuraciones básicas comunes</span><span class="sxs-lookup"><span data-stu-id="1ac20-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="1ac20-131">Wi-Fi red es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="1ac20-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="1ac20-132">Unirse a Azure AD con inscripción automática de MDM</span><span class="sxs-lookup"><span data-stu-id="1ac20-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="1ac20-133">MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="1ac20-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="1ac20-134">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="1ac20-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="1ac20-135">Compatible con uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="1ac20-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="1ac20-136">Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierto a la única.</span><span class="sxs-lookup"><span data-stu-id="1ac20-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="1ac20-137">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="1ac20-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="1ac20-138">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="1ac20-138">Common Challenges</span></span>
   * <span data-ttu-id="1ac20-139">HoloLens 2 no admite la Unión de AD local o SCCM.</span><span class="sxs-lookup"><span data-stu-id="1ac20-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="1ac20-140">Solo unirse a Azure AD con MDM.</span><span class="sxs-lookup"><span data-stu-id="1ac20-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="1ac20-141">Muchas empresas en la actualidad implementan equipos con Windows 10 en este escenario como locales de los dispositivos Unidos a AD, administrados por System Center Configuration Manager (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos internos de Windows 10 a través de soluciones MDM basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="1ac20-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="1ac20-142">Como HoloLens 2 es un dispositivo en la nube, depende en gran medida de los servicios conectados a la nube y de Internet para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, etc. Al conectarse a una red corporativa, es probable que las reglas de proxy o firewall se ajusten para habilitar el acceso a HoloLens 2 y las aplicaciones que se ejecutan en él.</span><span class="sxs-lookup"><span data-stu-id="1ac20-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="1ac20-143">La conectividad corporativa Wi-Fi generalmente requiere certificados para autenticar el dispositivo o el usuario en la red.</span><span class="sxs-lookup"><span data-stu-id="1ac20-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="1ac20-144">La configuración o la infraestructura requerida para implementar certificados en dispositivos con Windows 10 a través de MDM puede ser difícil de configurar.</span><span class="sxs-lookup"><span data-stu-id="1ac20-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="1ac20-145">Escenario C: implementar en un entorno seguro sin conexión</span><span class="sxs-lookup"><span data-stu-id="1ac20-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="1ac20-146">HoloLens 2 se ha implementado para usarlo principalmente sin conexión y sin acceso a la red ni a Internet.</span><span class="sxs-lookup"><span data-stu-id="1ac20-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="1ac20-147">Esta es una implementación típica para ubicaciones de alta seguridad o confidenciales.</span><span class="sxs-lookup"><span data-stu-id="1ac20-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="1ac20-148">Configuraciones básicas comunes</span><span class="sxs-lookup"><span data-stu-id="1ac20-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="1ac20-149">La conectividad de Wi-Fi está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="1ac20-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="1ac20-150">Es posible habilitar Ethernet por USB para conectividad de LAN si es necesario.</span><span class="sxs-lookup"><span data-stu-id="1ac20-150">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="1ac20-151">No administrado.</span><span class="sxs-lookup"><span data-stu-id="1ac20-151">Not Managed.</span></span>
   * <span data-ttu-id="1ac20-152">Cuenta de usuario local para el inicio de sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ac20-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="1ac20-153">HoloLens 2 solo admite una cuenta local.</span><span class="sxs-lookup"><span data-stu-id="1ac20-153">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="1ac20-154">Se aplican diversos niveles de configuración de bloqueo de dispositivo mediante paquetes de aprovisionamiento basados en casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="1ac20-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="1ac20-155">Por lo general, estas configuraciones están muy restringidas a causa de requisitos de entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="1ac20-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="1ac20-156">Una o más aplicaciones se implementan mediante el paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="1ac20-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="1ac20-157">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="1ac20-157">Common Challenges</span></span>
   * <span data-ttu-id="1ac20-158">Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="1ac20-158">There is a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="1ac20-159">Los servicios en la nube no se pueden aprovechar y, por lo tanto, limitan las capacidades de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1ac20-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="1ac20-160">Mayor overhead administrativo ya que estos dispositivos se deben configurar, configurar y actualizar de forma manual.</span><span class="sxs-lookup"><span data-stu-id="1ac20-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="1ac20-161">Para obtener una guía de implementación similar a este escenario, revise nuestra [Guía de implementación segura sin conexión](hololens-common-scenarios-offline-secure.md).</span><span class="sxs-lookup"><span data-stu-id="1ac20-161">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1ac20-162">Guía de implementación: HoloLens con conexión segura 2</span><span class="sxs-lookup"><span data-stu-id="1ac20-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
