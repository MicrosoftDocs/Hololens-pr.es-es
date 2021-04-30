---
title: Información general sobre las aplicaciones conectadas HoloLens 2 la nube con Remote Assist
description: Aprenda a inscribir dispositivos HoloLens 2 a través de una red conectada a la nube mediante Dynamics 365 Remote Assist.
keywords: HoloLens, administración, conexión a la nube, Remote Assist, AAD, Azure AD, MDM, Mobile Administración de dispositivos
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309109"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="fc38b-104">Guía de implementación: información general HoloLens 2 conexión a la nube con Remote Assist: información general</span><span class="sxs-lookup"><span data-stu-id="fc38b-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="fc38b-105">Esta guía ayuda a los profesionales de TI a planear e implementar Microsoft HoloLens 2 dispositivos en su organización con el objetivo general de que esos dispositivos estén conectados Microsoft HoloLens la nube a su organización con Dynamics 365 Remote Assist listo para su uso.</span><span class="sxs-lookup"><span data-stu-id="fc38b-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="fc38b-106">Tenga en cuenta que esto servirá como modelo para las implementaciones de prueba de concepto en su organización en una variedad de HoloLens 2 casos de uso.</span><span class="sxs-lookup"><span data-stu-id="fc38b-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="fc38b-107">Durante la guía se explica cómo inscribir los dispositivos en la administración de dispositivos, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar inmediatamente Remote Assist la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc38b-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="fc38b-108">Para ello, remos por los elementos importantes de infraestructura necesarios para configurarse y ejecutarse, lo que permite realizar la implementación a escala con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="fc38b-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![Banner conectado a la nube](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a><span data-ttu-id="fc38b-110">En esta guía</span><span class="sxs-lookup"><span data-stu-id="fc38b-110">In this Guide</span></span>

<span data-ttu-id="fc38b-111">Esta guía tiene el objetivo específico de configurar Remote Assist dentro de la organización en los dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fc38b-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="fc38b-112">Se cubrirán las necesidades necesarias para lograr ese objetivo.</span><span class="sxs-lookup"><span data-stu-id="fc38b-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="fc38b-113">Para mantener el foco en este objetivo, se seleccionarán previamente ciertas configuraciones y preparación con el fin de optimizar esta implementación o reducir los elementos necesarios para configurar.</span><span class="sxs-lookup"><span data-stu-id="fc38b-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="fc38b-114">Se le informará de estas opciones y podrá personalizar la implementación en función de sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="fc38b-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="fc38b-115">Se trata de una configuración similar a Escenario [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implementación en dispositivos de conexión a la nube, que es una buena opción para muchas implementaciones de prueba de concepto, que incluirá:</span><span class="sxs-lookup"><span data-stu-id="fc38b-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="fc38b-116">Wi-Fi las redes están totalmente abiertas a Internet y a los servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="fc38b-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="fc38b-117">Azure AD unirse a la inscripción automática de MDM: MDM (Intune) administrado</span><span class="sxs-lookup"><span data-stu-id="fc38b-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="fc38b-118">Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="fc38b-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="fc38b-119">Se admiten uno o varios usuarios por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc38b-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="fc38b-120">Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto a Pantalla completa de aplicación única</span><span class="sxs-lookup"><span data-stu-id="fc38b-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![Escenario conectado a la nube](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="fc38b-122">En esta guía no se aplicarán otras restricciones o configuraciones de dispositivos, pero le recomendamos que explore esas opciones después de finalizar.</span><span class="sxs-lookup"><span data-stu-id="fc38b-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="fc38b-123">Más información sobre Remote Assist</span><span class="sxs-lookup"><span data-stu-id="fc38b-123">Learn about Remote Assist</span></span>

<span data-ttu-id="fc38b-124">Remote Assist permite el mantenimiento y la reparación colaborativos, la inspección remota, así como el uso compartido de conocimientos y el entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="fc38b-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="fc38b-125">Al conectar a personas en distintos roles y ubicaciones, un Remote Assist puede conectarse con un colaborador remoto en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fc38b-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="fc38b-126">Pueden combinar vídeo, capturas de pantalla y anotaciones para resolver problemas en tiempo real, incluso cuando&#39;están en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="fc38b-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="fc38b-127">Los colaboradores remotos pueden insertar imágenes de referencia, esquemas y otra información útil del espacio físico del técnico&#39;para que puedan hacer referencia al esquema mientras trabajan de forma rápida y sin manos en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fc38b-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="fc38b-128">Esta guía le permitirá:</span><span class="sxs-lookup"><span data-stu-id="fc38b-128">In this guide you will:</span></span>

<span data-ttu-id="fc38b-129">Preparación:</span><span class="sxs-lookup"><span data-stu-id="fc38b-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="fc38b-130">Obtenga información sobre los aspectos básicos de la infraestructura HoloLens 2 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fc38b-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="fc38b-131">Obtenga más información Azure AD configurar una si&#39;no la tiene.</span><span class="sxs-lookup"><span data-stu-id="fc38b-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="fc38b-132">Obtenga información sobre la administración de identidades y cómo configurar mejor Azure AD cuentas.</span><span class="sxs-lookup"><span data-stu-id="fc38b-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="fc38b-133">Obtenga más información sobre MDM y configure con Intune si&#39;ya tiene uno listo.</span><span class="sxs-lookup"><span data-stu-id="fc38b-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="fc38b-134">Obtenga información sobre los requisitos de red de Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="fc38b-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="fc38b-135">Opcionalmente: VPN para conectarse a recursos organizativos</span><span class="sxs-lookup"><span data-stu-id="fc38b-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="fc38b-136">Configurar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc38b-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="fc38b-137">Cómo crear usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="fc38b-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="fc38b-138">Configuración de la inscripción automática en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fc38b-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="fc38b-139">Asignación de licencias de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc38b-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="fc38b-140">Implementación:</span><span class="sxs-lookup"><span data-stu-id="fc38b-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="fc38b-141">Configure la suscripción HoloLens 2 validar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fc38b-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="fc38b-142">Compruebe que puede realizar una Remote Assist llamada.</span><span class="sxs-lookup"><span data-stu-id="fc38b-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="fc38b-143">Mantener:</span><span class="sxs-lookup"><span data-stu-id="fc38b-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="fc38b-144">Actualización de Remote Assist mediante la Microsoft Store aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc38b-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="fc38b-145">Realización de un plan de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fc38b-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="fc38b-146">Plan de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="fc38b-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="fc38b-147">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="fc38b-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fc38b-148">Implementación conectada a la nube: preparación</span><span class="sxs-lookup"><span data-stu-id="fc38b-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

