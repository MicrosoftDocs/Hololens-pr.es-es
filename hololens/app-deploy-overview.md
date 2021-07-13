---
title: 'Información general: Administración de aplicaciones'
description: Introducción a la administración de aplicaciones de realidad mixta con administración de dispositivos móviles, Microsoft Store para empresas y paquetes de aprovisionamiento.
keywords: HoloLens, usuario, cuenta, aplicación, administración de aplicaciones,
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635558"
---
# <a name="app-management-overview"></a><span data-ttu-id="e051a-104">Administración de aplicaciones: Información general</span><span class="sxs-lookup"><span data-stu-id="e051a-104">App Management: Overview</span></span>

<span data-ttu-id="e051a-105">Puede implementar aplicaciones en cuatro rutas de acceso diferentes: **Mobile Administración de dispositivos (MDM)**, **Microsoft Store para Empresas**, **Microsoft Store** o instalando mediante el **aprovisionamiento** de .</span><span class="sxs-lookup"><span data-stu-id="e051a-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="e051a-106">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="e051a-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="e051a-107">Una solución MDM permite a los responsables de la toma de decisiones de TI y a los administradores instalar automáticamente (insertar) de forma privada sus aplicaciones de línea de negocio interna o comprar aplicaciones a través de la tienda para un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="e051a-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="e051a-108">HoloLens dispositivos funcionan mejor con Microsoft Endpoint Manager (Intune) para la [administración de aplicaciones.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="e051a-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="e051a-109">Intune también ofrece a los usuarios un control más preciso sobre las aplicaciones administradas por IT a través Portal de empresa experiencia descargable.</span><span class="sxs-lookup"><span data-stu-id="e051a-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="e051a-110">Las instrucciones siguientes son para los usuarios que desean administrar sus aplicaciones con Intune.</span><span class="sxs-lookup"><span data-stu-id="e051a-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="e051a-111">Microsoft recomienda usar Intune para la administración de aplicaciones y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e051a-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="e051a-112">La Administración de dispositivos móvil (MDM) es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="e051a-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="e051a-113">MDM implementado + Portal de empresa</span><span class="sxs-lookup"><span data-stu-id="e051a-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="e051a-114">Aplicaciones de línea de negocio (no públicas)</span><span class="sxs-lookup"><span data-stu-id="e051a-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="e051a-115">Instalación manual de aplicaciones disponibles mediante Portal de empresa</span><span class="sxs-lookup"><span data-stu-id="e051a-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="e051a-116">Inserción de administración a través de la directiva MDM</span><span class="sxs-lookup"><span data-stu-id="e051a-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="e051a-117">Actualización automática a través de MDM</span><span class="sxs-lookup"><span data-stu-id="e051a-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="e051a-118">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="e051a-118">Microsoft Store for Business</span></span>

<span data-ttu-id="e051a-119">El [Microsoft Store para Empresas](app-deploy-store-business.md) proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas para buscar, adquirir, administrar y distribuir aplicaciones gratuitas y de pago.</span><span class="sxs-lookup"><span data-stu-id="e051a-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="e051a-120">Los administradores de TI pueden administrar Microsoft Store aplicaciones y aplicaciones de línea de negocio privadas en un inventario, además de asignar y reutilizar licencias según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e051a-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="e051a-121">Para obtener más información, visite [Requisitos previos para usar el Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="e051a-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="e051a-122">El Microsoft Store para Empresas es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="e051a-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="e051a-123">Aplicaciones públicas o de línea de negocio</span><span class="sxs-lookup"><span data-stu-id="e051a-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="e051a-124">Instalación automática de aplicaciones necesarias a través de la asociación mdm</span><span class="sxs-lookup"><span data-stu-id="e051a-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="e051a-125">El usuario descarga aplicaciones manualmente</span><span class="sxs-lookup"><span data-stu-id="e051a-125">User manually downloads apps</span></span>
* <span data-ttu-id="e051a-126">Actualización automática</span><span class="sxs-lookup"><span data-stu-id="e051a-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="e051a-127">Aplicaciones de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e051a-127">Microsoft Store apps</span></span>

<span data-ttu-id="e051a-128">El Microsoft Store proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas para buscar, adquirir, administrar y distribuir aplicaciones públicas.</span><span class="sxs-lookup"><span data-stu-id="e051a-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="e051a-129">Esta Microsoft Store es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="e051a-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="e051a-130">Solo aplicaciones públicas</span><span class="sxs-lookup"><span data-stu-id="e051a-130">Public apps only</span></span>
* <span data-ttu-id="e051a-131">El usuario descarga aplicaciones manualmente</span><span class="sxs-lookup"><span data-stu-id="e051a-131">User manually downloads apps</span></span>
* <span data-ttu-id="e051a-132">Actualización automática si está conectado a Internet</span><span class="sxs-lookup"><span data-stu-id="e051a-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="e051a-133">Para obtener más información, visite [Aplicaciones de la Tienda Holográfica](/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="e051a-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="e051a-134">Instalación a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="e051a-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="e051a-135">[Los paquetes](app-deploy-provisioning-package.md) de aprovisionamiento permiten instalar aplicaciones personalizadas o de línea de negocio, lo que permite a los profesionales de TI y administradores instalar rápidamente aplicaciones en un dispositivo local a través de USB.</span><span class="sxs-lookup"><span data-stu-id="e051a-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="e051a-136">Esta instalación se puede realizar sin conexión a Internet y para cualquier tipo de identidad.</span><span class="sxs-lookup"><span data-stu-id="e051a-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="e051a-137">La instalación a través de paquetes de aprovisionamiento es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="e051a-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="e051a-138">Línea de negocio/ aplicaciones auto-desarrolladas (no públicas)</span><span class="sxs-lookup"><span data-stu-id="e051a-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="e051a-139">Aplicaciones públicas (si el instalador sin conexión está disponible)</span><span class="sxs-lookup"><span data-stu-id="e051a-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="e051a-140">Solo carga lateral USB</span><span class="sxs-lookup"><span data-stu-id="e051a-140">USB side-loading only</span></span>
* <span data-ttu-id="e051a-141">Sin actualización automática (requiere actualizaciones manuales a través del paquete de aprovisionamiento)</span><span class="sxs-lookup"><span data-stu-id="e051a-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="e051a-142">Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación</span><span class="sxs-lookup"><span data-stu-id="e051a-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="e051a-143">Con el [Instalador de aplicación](app-deploy-app-installer.md) los usuarios pueden tener una experiencia sencilla para instalar aplicaciones en dispositivos locales o compartir una aplicación con otra persona que no esté familiarizado con otros métodos de instalación de aplicaciones en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e051a-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="e051a-144">Esto se puede hacer sin necesidad de habilitar el modo de desarrollador o usar Portal de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e051a-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="e051a-145">Se trata de un método sencillo de distribuir una aplicación completamente creada.</span><span class="sxs-lookup"><span data-stu-id="e051a-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="e051a-146">Independientemente de si simplemente desea realizar una demostración de la aplicación a otro usuario con un HoloLens, o si desea implementar la aplicación, este método funciona fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e051a-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="e051a-147">La instalación mediante Instalador de aplicación es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="e051a-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="e051a-148">Aplicaciones de línea de negocio/auto-desarrolladas (no públicas)</span><span class="sxs-lookup"><span data-stu-id="e051a-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="e051a-149">Solo carga lateral</span><span class="sxs-lookup"><span data-stu-id="e051a-149">Side-load only</span></span>
* <span data-ttu-id="e051a-150">No requiere el modo de desarrollador ni el portal de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e051a-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="e051a-151">Fácil de instalar para el usuario final</span><span class="sxs-lookup"><span data-stu-id="e051a-151">Easy for end user to install</span></span>
