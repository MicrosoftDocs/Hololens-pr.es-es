---
title: Escenarios de implementación de infraestructura común
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857924"
---
# <span data-ttu-id="9f86e-103">Escenarios de implementación de infraestructura común</span><span class="sxs-lookup"><span data-stu-id="9f86e-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="9f86e-104">Esta información proporciona una descripción general de la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar dispositivos de Microsoft HoloLens 2 dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="9f86e-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="9f86e-105">Escenarios</span><span class="sxs-lookup"><span data-stu-id="9f86e-105">Scenarios</span></span>

<span data-ttu-id="9f86e-106">El diagrama siguiente representa tres escenarios típicos para las implementaciones de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9f86e-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![escenarios](images/scenarios.jpg)

### <span data-ttu-id="9f86e-108">Escenario A</span><span class="sxs-lookup"><span data-stu-id="9f86e-108">Scenario A</span></span>

<span data-ttu-id="9f86e-109">HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="9f86e-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="9f86e-110">No se puede acceder a los recursos corporativos o pueden estar limitados a través de VPN.</span><span class="sxs-lookup"><span data-stu-id="9f86e-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="9f86e-111">Esta es una implementación muy similar a la de los dispositivos móviles administrados dentro de una empresa.</span><span class="sxs-lookup"><span data-stu-id="9f86e-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="9f86e-112">Configuraciones básicas comunes</span><span class="sxs-lookup"><span data-stu-id="9f86e-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="9f86e-113">Las redes Wi-Fi suelen estar totalmente abiertas a Internet y a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="9f86e-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="9f86e-114">Unirse a Azure AD con inscripción automática de MDM: MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="9f86e-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="9f86e-115">Los usuarios inician sesión con su propia cuenta corporativa (AAD)</span><span class="sxs-lookup"><span data-stu-id="9f86e-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="9f86e-116">Compatible con uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="9f86e-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="9f86e-117">Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierto a la única.</span><span class="sxs-lookup"><span data-stu-id="9f86e-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="9f86e-118">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="9f86e-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="9f86e-119">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="9f86e-119">Common Challenges</span></span>
   * <span data-ttu-id="9f86e-120">Determinando las configuraciones de MDM que se aplicarán a HoloLens 2 en función de los requisitos del escenario.</span><span class="sxs-lookup"><span data-stu-id="9f86e-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="9f86e-121">Escenario B</span><span class="sxs-lookup"><span data-stu-id="9f86e-121">Scenario B</span></span>

<span data-ttu-id="9f86e-122">HoloLens 2 se ha implementado para usarlo principalmente en la red corporativa con acceso a recursos internos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="9f86e-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="9f86e-123">Es posible que los servicios de Internet y de nube estén limitados.</span><span class="sxs-lookup"><span data-stu-id="9f86e-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="9f86e-124">Esta es una implementación típica para la mayoría de equipos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9f86e-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="9f86e-125">Configuraciones básicas comunes</span><span class="sxs-lookup"><span data-stu-id="9f86e-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="9f86e-126">Red Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o a los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="9f86e-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="9f86e-127">Unirse a Azure AD con inscripción automática de MDM</span><span class="sxs-lookup"><span data-stu-id="9f86e-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="9f86e-128">MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="9f86e-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="9f86e-129">Los usuarios inician sesión con su propia cuenta corporativa (AAD)</span><span class="sxs-lookup"><span data-stu-id="9f86e-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="9f86e-130">Compatible con uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="9f86e-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="9f86e-131">Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierto a la única.</span><span class="sxs-lookup"><span data-stu-id="9f86e-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="9f86e-132">Una o más aplicaciones se implementan a través de MDM</span><span class="sxs-lookup"><span data-stu-id="9f86e-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="9f86e-133">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="9f86e-133">Common Challenges</span></span>
   * <span data-ttu-id="9f86e-134">HoloLens 2 no admite la Unión de AD local o SCCM.</span><span class="sxs-lookup"><span data-stu-id="9f86e-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="9f86e-135">Solo unirse a Azure AD con MDM.</span><span class="sxs-lookup"><span data-stu-id="9f86e-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="9f86e-136">Muchas empresas en la actualidad implementan equipos con Windows 10 en este escenario como locales de los dispositivos Unidos a AD, administrados por System Center Configuration Manager (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos internos de Windows 10 a través de soluciones MDM basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="9f86e-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="9f86e-137">Como HoloLens 2 es un dispositivo en la nube, depende en gran medida de los servicios conectados a la nube y de Internet para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, etc. Al conectarse a una red corporativa, es probable que las reglas de proxy o firewall se ajusten para habilitar el acceso a HoloLens 2 y las aplicaciones que se ejecutan en él.</span><span class="sxs-lookup"><span data-stu-id="9f86e-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="9f86e-138">La conectividad Wi-Fi corporativa suele requerir certificados para autenticar el dispositivo o el usuario en la red.</span><span class="sxs-lookup"><span data-stu-id="9f86e-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="9f86e-139">La configuración o la infraestructura requerida para implementar certificados en dispositivos con Windows 10 a través de MDM puede ser difícil de configurar.</span><span class="sxs-lookup"><span data-stu-id="9f86e-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="9f86e-140">Escenario C</span><span class="sxs-lookup"><span data-stu-id="9f86e-140">Scenario C</span></span>

<span data-ttu-id="9f86e-141">HoloLens 2 se ha implementado para usarlo principalmente sin conexión y sin acceso a la red ni a Internet.</span><span class="sxs-lookup"><span data-stu-id="9f86e-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="9f86e-142">Esta es una implementación típica para ubicaciones de alta seguridad o confidenciales.</span><span class="sxs-lookup"><span data-stu-id="9f86e-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="9f86e-143">Configuraciones básicas comunes</span><span class="sxs-lookup"><span data-stu-id="9f86e-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="9f86e-144">La conectividad Wi-Fi está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="9f86e-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="9f86e-145">Si es necesario, puede habilitarse Ethernet por USB para conectividad de LAN.</span><span class="sxs-lookup"><span data-stu-id="9f86e-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="9f86e-146">No administrado.</span><span class="sxs-lookup"><span data-stu-id="9f86e-146">Not Managed.</span></span>
   * <span data-ttu-id="9f86e-147">Cuenta de usuario local para el inicio de sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9f86e-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="9f86e-148">HoloLens 2 solo admite 1 cuenta local.</span><span class="sxs-lookup"><span data-stu-id="9f86e-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="9f86e-149">Se aplican diversos niveles de configuración de bloqueo de dispositivo mediante paquetes de aprovisionamiento basados en casos de uso específicos.</span><span class="sxs-lookup"><span data-stu-id="9f86e-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="9f86e-150">Por lo general, estas configuraciones están muy restringidas a causa de requisitos de entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="9f86e-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="9f86e-151">Una o más aplicaciones se implementan mediante el paquete de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="9f86e-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="9f86e-152">Desafíos comunes</span><span class="sxs-lookup"><span data-stu-id="9f86e-152">Common Challenges</span></span>
   * <span data-ttu-id="9f86e-153">Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="9f86e-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="9f86e-154">Los servicios en la nube no se pueden aprovechar y, por lo tanto, limitan las capacidades de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9f86e-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="9f86e-155">Mayor overhead administrativo ya que estos dispositivos se deben configurar, configurar y actualizar de forma manual.</span><span class="sxs-lookup"><span data-stu-id="9f86e-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
