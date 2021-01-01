---
title: 'Información general: administración de aplicaciones'
description: App, administración, administración de aplicaciones
keywords: HoloLens, usuario, cuenta, aplicación, administración de aplicaciones
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252671"
---
# <span data-ttu-id="0ec4e-104">Administración de aplicaciones: información general</span><span class="sxs-lookup"><span data-stu-id="0ec4e-104">App Management: Overview</span></span>

<span data-ttu-id="0ec4e-105">Puede implementar aplicaciones en cuatro rutas diferentes: **Administración de dispositivos móviles (MDM)**, **Microsoft Store para empresas**, **Microsoft Store**o instalarlas a través del **aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="0ec4e-106">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="0ec4e-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="0ec4e-107">Una solución MDM permite que los responsables de tomar decisiones de ti y los administradores se instalen automáticamente (push) sus aplicaciones internas, de línea de negocio o las aplicaciones de compra a través de la tienda para un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="0ec4e-108">Los dispositivos HoloLens funcionan mejor con Microsoft Endpoint Manager (Intune) para la [Administración de aplicaciones](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="0ec4e-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="0ec4e-109">Intune también ofrece a los usuarios un control más preciso sobre las aplicaciones administradas por ti a través de la experiencia descargable del portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec4e-110">Las siguientes instrucciones son para los usuarios que desean administrar sus aplicaciones con Intune.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="0ec4e-111">Microsoft recomienda usar Intune para la administración de aplicaciones y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="0ec4e-112">La administración de dispositivos móviles (MDM) es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="0ec4e-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="0ec4e-113">Implementación de MDM y portal de empresa</span><span class="sxs-lookup"><span data-stu-id="0ec4e-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="0ec4e-114">Aplicaciones de línea de negocio (no públicas)</span><span class="sxs-lookup"><span data-stu-id="0ec4e-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="0ec4e-115">Instalación manual de las aplicaciones disponibles a través del portal de la empresa</span><span class="sxs-lookup"><span data-stu-id="0ec4e-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="0ec4e-116">Administrador Push a través de la Directiva MDM</span><span class="sxs-lookup"><span data-stu-id="0ec4e-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="0ec4e-117">Actualización automática a través de MDM</span><span class="sxs-lookup"><span data-stu-id="0ec4e-117">Auto update through MDM</span></span>

## <span data-ttu-id="0ec4e-118">Microsoft Store para Business</span><span class="sxs-lookup"><span data-stu-id="0ec4e-118">Microsoft Store for Business</span></span>

<span data-ttu-id="0ec4e-119">[Microsoft Store para empresas](app-deploy-store-business.md) proporciona a los responsables de la toma de decisiones de ti y a los administradores de las empresas la búsqueda, la adquisición, la administración y la distribución de aplicaciones gratuitas y de dinero.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="0ec4e-120">Los administradores de TI pueden administrar las aplicaciones de Microsoft Store y las aplicaciones de línea de negocio privadas en un inventario, además de asignar y reutilizar licencias según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="0ec4e-121">Para obtener más información, visite [el apartado requisitos previos para usar Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="0ec4e-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="0ec4e-122">Microsoft Store para empresas es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="0ec4e-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="0ec4e-123">Aplicaciones públicas o de línea de negocio</span><span class="sxs-lookup"><span data-stu-id="0ec4e-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="0ec4e-124">Instalación automática de las aplicaciones necesarias a través de la Asociación de MDM</span><span class="sxs-lookup"><span data-stu-id="0ec4e-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="0ec4e-125">El usuario descarga las aplicaciones de forma manual</span><span class="sxs-lookup"><span data-stu-id="0ec4e-125">User manually downloads apps</span></span>
* <span data-ttu-id="0ec4e-126">Actualización automática</span><span class="sxs-lookup"><span data-stu-id="0ec4e-126">Auto Update</span></span>

## <span data-ttu-id="0ec4e-127">Aplicaciones de MicrosoftStore</span><span class="sxs-lookup"><span data-stu-id="0ec4e-127">Microsoft Store apps</span></span>

<span data-ttu-id="0ec4e-128">Microsoft Store proporciona a los responsables de las decisiones y administradores de TI de las empresas la búsqueda, la adquisición, la administración y la distribución de aplicaciones públicas.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="0ec4e-129">Esta Microsoft Store es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="0ec4e-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="0ec4e-130">Solo aplicaciones públicas</span><span class="sxs-lookup"><span data-stu-id="0ec4e-130">Public apps only</span></span>
* <span data-ttu-id="0ec4e-131">El usuario descarga las aplicaciones de forma manual</span><span class="sxs-lookup"><span data-stu-id="0ec4e-131">User manually downloads apps</span></span>
* <span data-ttu-id="0ec4e-132">Actualización automática si se conecta a Internet</span><span class="sxs-lookup"><span data-stu-id="0ec4e-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="0ec4e-133">Para obtener más información, visite aplicaciones de la [tienda holográfica](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="0ec4e-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="0ec4e-134">Instalar a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="0ec4e-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="0ec4e-135">Los [paquetes de aprovisionamiento](app-deploy-provisioning-package.md) le permiten instalar aplicaciones personalizadas o de línea de negocios, lo que permite a los profesionales de ti y administradores instalar aplicaciones rápidamente en un dispositivo local a través de USB.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="0ec4e-136">Esta instalación puede realizarse sin conexión a Internet y para cualquier tipo de identidad.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="0ec4e-137">La instalación de los paquetes de provisioning es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="0ec4e-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="0ec4e-138">Aplicaciones de línea de negocio/desarrolladas por sí mismos (no públicas)</span><span class="sxs-lookup"><span data-stu-id="0ec4e-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="0ec4e-139">Aplicaciones públicas (si el instalador sin conexión está disponible)</span><span class="sxs-lookup"><span data-stu-id="0ec4e-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="0ec4e-140">Solo carga del lado USB</span><span class="sxs-lookup"><span data-stu-id="0ec4e-140">USB side-loading only</span></span>
* <span data-ttu-id="0ec4e-141">No hay ninguna actualización automática (requiere actualizaciones manuales mediante el paquete de aprovisionamiento)</span><span class="sxs-lookup"><span data-stu-id="0ec4e-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="0ec4e-142">Instalar aplicaciones en HoloLens 2 a través del instalador de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0ec4e-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="0ec4e-143">Con el [instalador de aplicaciones](app-deploy-app-installer.md) , los usuarios pueden tener una experiencia que es sencilla para instalar aplicaciones en dispositivos locales o para compartir una aplicación con otra persona que no está familiarizado con otros métodos de instalación de aplicaciones en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="0ec4e-144">Esto puede hacerse sin necesidad de habilitar el modo de desarrollador ni usar Device portal.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="0ec4e-145">Este es un método simple para distribuir una aplicación completamente integrada.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="0ec4e-146">Independientemente de si simplemente deseas demostrar la aplicación a otro usuario con HoloLens o deseas implementar tu aplicación, este método funciona fácilmente.</span><span class="sxs-lookup"><span data-stu-id="0ec4e-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="0ec4e-147">La instalación mediante el instalador de la aplicación es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="0ec4e-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="0ec4e-148">Aplicaciones de línea de negocio/desarrolladas (no públicas)</span><span class="sxs-lookup"><span data-stu-id="0ec4e-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="0ec4e-149">Solo carga del lado</span><span class="sxs-lookup"><span data-stu-id="0ec4e-149">Side-load only</span></span>
* <span data-ttu-id="0ec4e-150">No requiere el modo de desarrollador ni el portal de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0ec4e-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="0ec4e-151">Fácil de instalar para el usuario final</span><span class="sxs-lookup"><span data-stu-id="0ec4e-151">Easy for end user to install</span></span>
