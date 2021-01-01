---
title: 'Guía de implementación: HoloLens conectado a la nube con ayuda remota: información general'
description: Inscribir dispositivos HoloLens en una red conectada en la nube
keywords: HoloLens, administración, nube conectada, asistencia remota, AAD, Azure AD, MDM, administración de dispositivos móviles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7d954347c7c274b844d436c0d6fc96e8bbc59f10
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253187"
---
# <span data-ttu-id="7a29b-104">Guía de implementación: HoloLens conectado a la nube con asistencia remota (información general)</span><span class="sxs-lookup"><span data-stu-id="7a29b-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="7a29b-105">Esta guía ayuda a los profesionales de ti a planear e implementar dispositivos Microsoft HoloLens 2 a su organización con el objetivo general de tener esos dispositivos conectados en la nube a la organización con el asistente remoto de Dynamics 365 listo para usar.</span><span class="sxs-lookup"><span data-stu-id="7a29b-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="7a29b-106">Tenga en cuenta que este es un modelo para las implementaciones de prueba de concepto para su organización en una variedad de casos de uso de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7a29b-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="7a29b-107">Durante la guía, describiremos cómo inscribir sus dispositivos en la administración del dispositivo, aplicar licencias según sea necesario y comprobar que los usuarios finales pueden usar inmediatamente asistencia remota al configurar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a29b-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="7a29b-108">Para hacerlo, repasaremos las importantes partes de infraestructura necesarias para configurar y ejecutar: Cómo lograr la implementación a escala con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7a29b-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="7a29b-109">En esta guía</span><span class="sxs-lookup"><span data-stu-id="7a29b-109">In this Guide</span></span>

<span data-ttu-id="7a29b-110">Esta guía tiene el objetivo específico de configurar asistencia remota en tu organización en tus dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7a29b-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="7a29b-111">Cubriremos las Necessities necesarias para alcanzar ese objetivo.</span><span class="sxs-lookup"><span data-stu-id="7a29b-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="7a29b-112">Para mantener el foco en este objetivo, se preseleccionarán ciertas opciones de preparación y configuración para poder optimizar esta implementación o reducir los elementos necesarios para configurar.</span><span class="sxs-lookup"><span data-stu-id="7a29b-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="7a29b-113">Se le informará de estas elecciones y podrá personalizar su implementación según las necesidades de su empresa.</span><span class="sxs-lookup"><span data-stu-id="7a29b-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="7a29b-114">Se trata de una configuración similar a la del [escenario a: implementar en dispositivos de conexión en la nube](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que es una buena opción para una prueba de implementaciones de concepto, que incluirá:</span><span class="sxs-lookup"><span data-stu-id="7a29b-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="7a29b-115">Las redes Wi-Fi suelen estar totalmente abiertas con los servicios de Internet y de la nube</span><span class="sxs-lookup"><span data-stu-id="7a29b-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="7a29b-116">Unirse a Azure AD con inscripción automática de MDM: MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="7a29b-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="7a29b-117">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7a29b-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="7a29b-118">Compatible con uno o varios usuarios por dispositivo</span><span class="sxs-lookup"><span data-stu-id="7a29b-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="7a29b-119">Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierta a la única.</span><span class="sxs-lookup"><span data-stu-id="7a29b-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Escenario de conexión a la nube](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="7a29b-121">En esta guía no se aplicarán otras restricciones ni configuraciones de dispositivo, pero le recomendamos que explore dichas opciones después de finalizar.</span><span class="sxs-lookup"><span data-stu-id="7a29b-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="7a29b-122">Obtener más información sobre asistencia remota</span><span class="sxs-lookup"><span data-stu-id="7a29b-122">Learn about Remote Assist</span></span>

<span data-ttu-id="7a29b-123">El asistente remoto permite el mantenimiento y la reparación de colaboración, la inspección remota, así como la formación y el uso compartido de la información.</span><span class="sxs-lookup"><span data-stu-id="7a29b-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="7a29b-124">Al conectar personas en diferentes roles y ubicaciones, un técnico que use el asistente remoto puede conectarse con un colaborador remoto en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a29b-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="7a29b-125">Pueden combinar vídeo, capturas de pantalla y anotaciones para resolver problemas en tiempo real, incluso cuando no&#39;en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="7a29b-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="7a29b-126">Los colaboradores remotos pueden insertar imágenes de referencia, esquemas y otra información útil el técnico&#39;s espacio físico para que puedan consultar el esquema mientras se trabaja con los cabezales y las manos libres en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7a29b-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="7a29b-127">En esta guía, usted podrá:</span><span class="sxs-lookup"><span data-stu-id="7a29b-127">In this guide you will:</span></span>

<span data-ttu-id="7a29b-128">Preparar</span><span class="sxs-lookup"><span data-stu-id="7a29b-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7a29b-129">Más información sobre los conceptos básicos de infraestructura para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7a29b-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="7a29b-130">Obtenga más información sobre Azure AD y configure uno si no&#39;lo tiene.</span><span class="sxs-lookup"><span data-stu-id="7a29b-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="7a29b-131">Obtén más información sobre la administración de identidades y sobre cómo configurar mejor las cuentas de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7a29b-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="7a29b-132">Obtenga más información sobre MDM y configúrelo con Intune si no&#39;ya hay una lista.</span><span class="sxs-lookup"><span data-stu-id="7a29b-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="7a29b-133">Obtenga más información sobre los requisitos de red de asistencia remota.</span><span class="sxs-lookup"><span data-stu-id="7a29b-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="7a29b-134">Opcionalmente: VPN para conectarse a los recursos de la organización</span><span class="sxs-lookup"><span data-stu-id="7a29b-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="7a29b-135">Volver</span><span class="sxs-lookup"><span data-stu-id="7a29b-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7a29b-136">Cómo crear usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="7a29b-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="7a29b-137">Cómo configurar la inscripción automática en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7a29b-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="7a29b-138">Cómo asignar las licencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7a29b-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="7a29b-139">Implement</span><span class="sxs-lookup"><span data-stu-id="7a29b-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7a29b-140">Configura tu HoloLens 2 y valida la inscripción.</span><span class="sxs-lookup"><span data-stu-id="7a29b-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="7a29b-141">Validar: puede hacer una llamada de asistencia remota.</span><span class="sxs-lookup"><span data-stu-id="7a29b-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="7a29b-142">Mantener</span><span class="sxs-lookup"><span data-stu-id="7a29b-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7a29b-143">Cómo actualizar asistencia remota mediante la aplicación Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="7a29b-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="7a29b-144">Realizar un plan de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="7a29b-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="7a29b-145">Plan de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7a29b-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="7a29b-146">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7a29b-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7a29b-147">Implementación con conexión en la nube-preparación</span><span class="sxs-lookup"><span data-stu-id="7a29b-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

