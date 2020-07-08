---
title: 'Información general: administración de aplicaciones'
description: App, administración, administración de aplicaciones
keywords: HoloLens, usuario, cuenta, aplicación, administración de aplicaciones
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857958"
---
# <span data-ttu-id="23ed9-104">Administración de aplicaciones: información general</span><span class="sxs-lookup"><span data-stu-id="23ed9-104">App Management: Overview</span></span>

<span data-ttu-id="23ed9-105">Puede implementar aplicaciones en cuatro rutas diferentes: **Administración de dispositivos móviles (MDM)**, **Microsoft Store para empresas**, **Microsoft Store**o instalarlas a través del **aprovisionamiento**.</span><span class="sxs-lookup"><span data-stu-id="23ed9-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="23ed9-106">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="23ed9-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="23ed9-107">Una solución MDM permite que los responsables de tomar decisiones de ti y los administradores se instalen automáticamente (push) sus aplicaciones internas, de línea de negocio o las aplicaciones de compra a través de la tienda para un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="23ed9-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="23ed9-108">Los dispositivos HoloLens funcionan mejor con Microsoft Endpoint Manager (Intune) para la [Administración de aplicaciones](app-deploy-intune.md).</span><span class="sxs-lookup"><span data-stu-id="23ed9-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="23ed9-109">Intune también ofrece a los usuarios un control más preciso sobre las aplicaciones administradas por ti a través de la experiencia descargable del portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="23ed9-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="23ed9-110">Las siguientes instrucciones son para los usuarios que desean administrar sus aplicaciones con Intune.</span><span class="sxs-lookup"><span data-stu-id="23ed9-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="23ed9-111">Microsoft recomienda usar Intune para la administración de aplicaciones y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="23ed9-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="23ed9-112">La administración de dispositivos móviles (MDM) es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="23ed9-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="23ed9-113">Implementación de MDM y portal de empresa</span><span class="sxs-lookup"><span data-stu-id="23ed9-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="23ed9-114">Línea de aplicaciones Buisness (no públicas)</span><span class="sxs-lookup"><span data-stu-id="23ed9-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="23ed9-115">Instalación manual de las aplicaciones disponibles a través del portal de la empresa</span><span class="sxs-lookup"><span data-stu-id="23ed9-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="23ed9-116">Administrador Push a través de la Directiva MDM</span><span class="sxs-lookup"><span data-stu-id="23ed9-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="23ed9-117">Actualización automática a través de MDM</span><span class="sxs-lookup"><span data-stu-id="23ed9-117">Auto update through MDM</span></span>

## <span data-ttu-id="23ed9-118">Microsoft Store para Business</span><span class="sxs-lookup"><span data-stu-id="23ed9-118">Microsoft Store for Business</span></span>

<span data-ttu-id="23ed9-119">[Microsoft Store para empresas](app-deploy-store-business.md) proporciona a los responsables de la toma de decisiones de ti y a los administradores de las empresas la búsqueda, la adquisición, la administración y la distribución de aplicaciones gratuitas y de dinero.</span><span class="sxs-lookup"><span data-stu-id="23ed9-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="23ed9-120">Los administradores de TI pueden administrar aplicaciones de Microsoft Store y aplicaciones de líneas de negocio privadas en un inventario, además de asignar y volver a usar licencias según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="23ed9-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="23ed9-121">Para obtener más información, visite [el apartado requisitos previos para usar Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="23ed9-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="23ed9-122">Microsoft Store para empresas es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="23ed9-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="23ed9-123">Aplicaciones públicas o de línea de negocio</span><span class="sxs-lookup"><span data-stu-id="23ed9-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="23ed9-124">Instalación automática de las aplicaciones necesarias a través de la Asociación de MDM</span><span class="sxs-lookup"><span data-stu-id="23ed9-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="23ed9-125">El usuario descarga las aplicaciones de forma manual</span><span class="sxs-lookup"><span data-stu-id="23ed9-125">User manually downloads apps</span></span>
* <span data-ttu-id="23ed9-126">Actualización automática</span><span class="sxs-lookup"><span data-stu-id="23ed9-126">Auto Update</span></span>

## <span data-ttu-id="23ed9-127">Aplicaciones de MicrosoftStore</span><span class="sxs-lookup"><span data-stu-id="23ed9-127">Microsoft Store apps</span></span>

<span data-ttu-id="23ed9-128">Microsoft Store proporciona a los responsables de las decisiones y administradores de TI de las empresas la búsqueda, la adquisición, la administración y la distribución de aplicaciones públicas.</span><span class="sxs-lookup"><span data-stu-id="23ed9-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="23ed9-129">Esta Microsoft Store es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="23ed9-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="23ed9-130">Solo aplicaciones públicas</span><span class="sxs-lookup"><span data-stu-id="23ed9-130">Public apps only</span></span>
* <span data-ttu-id="23ed9-131">El usuario descarga las aplicaciones de forma manual</span><span class="sxs-lookup"><span data-stu-id="23ed9-131">User manually downloads apps</span></span>
* <span data-ttu-id="23ed9-132">Actualización automática si se conecta a Internet</span><span class="sxs-lookup"><span data-stu-id="23ed9-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="23ed9-133">Para obtener más información, visite aplicaciones de la [tienda holográfica](https://docs.microsoft.com/hololens/holographic-store-apps).</span><span class="sxs-lookup"><span data-stu-id="23ed9-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="23ed9-134">Instalar a través de paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="23ed9-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="23ed9-135">Los [paquetes de aprovisionamiento](app-deploy-provisioning-package.md) le permiten instalar aplicaciones personalizadas o de línea de negocios, lo que permite a los profesionales de ti y administradores instalar aplicaciones rápidamente en un dispositivo local a través de USB.</span><span class="sxs-lookup"><span data-stu-id="23ed9-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="23ed9-136">Esto puede hacerse sin una conexión a Internet y para cualquier tipo de identidad.</span><span class="sxs-lookup"><span data-stu-id="23ed9-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="23ed9-137">La instalación de los paquetes de provisioning es aplicable a:</span><span class="sxs-lookup"><span data-stu-id="23ed9-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="23ed9-138">Línea de aplicaciones Buisness (no públicas)</span><span class="sxs-lookup"><span data-stu-id="23ed9-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="23ed9-139">Aplicaciones públicas (si el instalador sin conexión está disponible)</span><span class="sxs-lookup"><span data-stu-id="23ed9-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="23ed9-140">Solo carga del lado USB</span><span class="sxs-lookup"><span data-stu-id="23ed9-140">USB side-load only</span></span>
* <span data-ttu-id="23ed9-141">No hay ninguna actualización automática (requiere actualizaciones manuales mediante el paquete de aprovisionamiento)</span><span class="sxs-lookup"><span data-stu-id="23ed9-141">No auto update (requires manual updates via Provisioning Package)</span></span>
