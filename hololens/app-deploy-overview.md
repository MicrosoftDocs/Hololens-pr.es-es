---
title: 'Información general: Administración de aplicaciones'
description: Introducción a la administración de aplicaciones de realidad mixta con la administración de dispositivos móviles, la Microsoft Store para Empresas y los paquetes de aprovisionamiento.
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283711"
---
# <span data-ttu-id="a42d1-104">Administración de aplicaciones: información general</span><span class="sxs-lookup"><span data-stu-id="a42d1-104">App Management: Overview</span></span>

<span data-ttu-id="a42d1-105">Puedes implementar aplicaciones en cuatro rutas diferentes: Administración de dispositivos móviles **(MDM),** **Microsoft Store**para Empresas, **Microsoft Store**o si las instalas a través del **aprovisionamiento.**</span><span class="sxs-lookup"><span data-stu-id="a42d1-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="a42d1-106">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="a42d1-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="a42d1-107">Una solución MDM permite a los responsables de la toma de decisiones de TI y a los administradores instalar automáticamente (insertar) de forma privada sus aplicaciones de línea de negocio, o comprar aplicaciones a través de la tienda para un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a42d1-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="a42d1-108">Los dispositivos HoloLens funcionan mejor con Microsoft Endpoint Manager (Intune) para la [administración de aplicaciones.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="a42d1-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="a42d1-109">Intune también ofrece a los usuarios un control más preciso sobre las aplicaciones administradas por IT a través de la experiencia descargable del Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="a42d1-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="a42d1-110">Las siguientes instrucciones son para los usuarios que desean administrar sus aplicaciones con Intune.</span><span class="sxs-lookup"><span data-stu-id="a42d1-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="a42d1-111">Microsoft recomienda usar Intune para la administración de aplicaciones y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a42d1-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="a42d1-112">La administración de dispositivos móviles (MDM) se aplica a:</span><span class="sxs-lookup"><span data-stu-id="a42d1-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="a42d1-113">MDM implementado + Portal de empresa</span><span class="sxs-lookup"><span data-stu-id="a42d1-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="a42d1-114">Aplicaciones de línea de negocio (no públicas)</span><span class="sxs-lookup"><span data-stu-id="a42d1-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="a42d1-115">Instalación manual de aplicaciones disponibles a través del Portal de empresa</span><span class="sxs-lookup"><span data-stu-id="a42d1-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="a42d1-116">Inserción de administrador a través de la directiva MDM</span><span class="sxs-lookup"><span data-stu-id="a42d1-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="a42d1-117">Actualización automática a través de MDM</span><span class="sxs-lookup"><span data-stu-id="a42d1-117">Auto update through MDM</span></span>

## <span data-ttu-id="a42d1-118">Microsoft Store para Business</span><span class="sxs-lookup"><span data-stu-id="a42d1-118">Microsoft Store for Business</span></span>

<span data-ttu-id="a42d1-119">La [Microsoft Store para Empresas](app-deploy-store-business.md) proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas la capacidad de buscar, adquirir, administrar y distribuir aplicaciones gratuitas y de pago.</span><span class="sxs-lookup"><span data-stu-id="a42d1-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="a42d1-120">Los administradores de TI pueden administrar aplicaciones de Microsoft Store y aplicaciones de línea de negocio privadas en un inventario, además de asignar y reutilizar licencias según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a42d1-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="a42d1-121">Para obtener más información, visita [Requisitos previos para usar la Microsoft Store para Empresas.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="a42d1-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="a42d1-122">La Microsoft Store para Empresas se aplica a:</span><span class="sxs-lookup"><span data-stu-id="a42d1-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="a42d1-123">Aplicaciones públicas o de línea de negocio</span><span class="sxs-lookup"><span data-stu-id="a42d1-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="a42d1-124">Instalación automática de aplicaciones necesarias a través de la asociación MDM</span><span class="sxs-lookup"><span data-stu-id="a42d1-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="a42d1-125">El usuario descarga aplicaciones manualmente</span><span class="sxs-lookup"><span data-stu-id="a42d1-125">User manually downloads apps</span></span>
* <span data-ttu-id="a42d1-126">Actualización automática</span><span class="sxs-lookup"><span data-stu-id="a42d1-126">Auto Update</span></span>

## <span data-ttu-id="a42d1-127">Aplicaciones de MicrosoftStore</span><span class="sxs-lookup"><span data-stu-id="a42d1-127">Microsoft Store apps</span></span>

<span data-ttu-id="a42d1-128">Microsoft Store proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas la capacidad de buscar, adquirir, administrar y distribuir aplicaciones públicas.</span><span class="sxs-lookup"><span data-stu-id="a42d1-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="a42d1-129">Esta Microsoft Store se aplica a:</span><span class="sxs-lookup"><span data-stu-id="a42d1-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="a42d1-130">Solo aplicaciones públicas</span><span class="sxs-lookup"><span data-stu-id="a42d1-130">Public apps only</span></span>
* <span data-ttu-id="a42d1-131">El usuario descarga aplicaciones manualmente</span><span class="sxs-lookup"><span data-stu-id="a42d1-131">User manually downloads apps</span></span>
* <span data-ttu-id="a42d1-132">Actualización automática si está conectado a Internet</span><span class="sxs-lookup"><span data-stu-id="a42d1-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="a42d1-133">Para obtener más información, visita [Aplicaciones de la Tienda Holográfica.](https://docs.microsoft.com/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="a42d1-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="a42d1-134">Instalar a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="a42d1-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="a42d1-135">[Los paquetes](app-deploy-provisioning-package.md) de aprovisionamiento te permiten instalar aplicaciones personalizadas o de línea de negocio, lo que permite a los profesionales de TI y administradores instalar rápidamente aplicaciones en un dispositivo local a través de USB.</span><span class="sxs-lookup"><span data-stu-id="a42d1-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="a42d1-136">Esta instalación se puede realizar sin una conexión a Internet y para cualquier tipo de identidad.</span><span class="sxs-lookup"><span data-stu-id="a42d1-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="a42d1-137">La instalación a través de paquetes de aprovisionamiento es aplicable para:</span><span class="sxs-lookup"><span data-stu-id="a42d1-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="a42d1-138">Línea de negocio/ aplicaciones autodese desarrolladas (no públicas)</span><span class="sxs-lookup"><span data-stu-id="a42d1-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="a42d1-139">Aplicaciones públicas (si el instalador sin conexión está disponible)</span><span class="sxs-lookup"><span data-stu-id="a42d1-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="a42d1-140">Solo carga lateral USB</span><span class="sxs-lookup"><span data-stu-id="a42d1-140">USB side-loading only</span></span>
* <span data-ttu-id="a42d1-141">Sin actualización automática (requiere actualizaciones manuales a través del paquete de aprovisionamiento)</span><span class="sxs-lookup"><span data-stu-id="a42d1-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="a42d1-142">Instalar aplicaciones en HoloLens 2 mediante el Instalador de aplicación</span><span class="sxs-lookup"><span data-stu-id="a42d1-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="a42d1-143">El [](app-deploy-app-installer.md) uso del Instalador de aplicación puede tener una experiencia sencilla para instalar aplicaciones en dispositivos locales o compartir una aplicación con otra persona que no esté familiarizado con otros métodos de instalación de aplicaciones en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a42d1-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="a42d1-144">Esto se puede hacer sin necesidad de habilitar el modo de desarrollador o usar Device Portal.</span><span class="sxs-lookup"><span data-stu-id="a42d1-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="a42d1-145">Este es un método sencillo de distribuir una aplicación completamente integrada.</span><span class="sxs-lookup"><span data-stu-id="a42d1-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="a42d1-146">Independientemente de si simplemente quieres realizar una demostración de la aplicación a otro usuario con un HoloLens, o quieres implementar tu aplicación, este método funciona fácilmente.</span><span class="sxs-lookup"><span data-stu-id="a42d1-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="a42d1-147">La instalación a través del Instalador de aplicación es aplicable para:</span><span class="sxs-lookup"><span data-stu-id="a42d1-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="a42d1-148">Línea de negocio/ aplicaciones auto desarrolladas (no públicas)</span><span class="sxs-lookup"><span data-stu-id="a42d1-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="a42d1-149">Solo carga lateral</span><span class="sxs-lookup"><span data-stu-id="a42d1-149">Side-load only</span></span>
* <span data-ttu-id="a42d1-150">No requiere el modo de desarrollador ni Device Portal</span><span class="sxs-lookup"><span data-stu-id="a42d1-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="a42d1-151">Fácil de instalar para el usuario final</span><span class="sxs-lookup"><span data-stu-id="a42d1-151">Easy for end user to install</span></span>
