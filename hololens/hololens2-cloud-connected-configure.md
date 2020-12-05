---
title: 'Guía de implementación: implementación de la nube conectada a HoloLens 2 a escala con asistencia remota-configurar'
description: Cómo configurar las configuraciones para inscribir dispositivos HoloLens en una red conectada en la nube
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196379"
---
# <span data-ttu-id="bf789-104">Configurar-guía conectada a la nube</span><span class="sxs-lookup"><span data-stu-id="bf789-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="bf789-105">En esta sección de la guía,&#39;emos cómo configurar la inscripción automática para su espacio empresarial y cómo aplicar licencias tanto para Intune como para asistencia remota.</span><span class="sxs-lookup"><span data-stu-id="bf789-105">In this section of the guide we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="bf789-106">Usuarios y grupos de Azure</span><span class="sxs-lookup"><span data-stu-id="bf789-106">Azure Users and Groups</span></span>

<span data-ttu-id="bf789-107">Azure e Intune con esa extensión, usa usuarios y grupos para ayudar a asignar configuraciones y licencias.</span><span class="sxs-lookup"><span data-stu-id="bf789-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="bf789-108">Para validar este flujo de implementación y poder hacer una llamada de asistencia remota desde un usuario a otro&#39;necesita 2 cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="bf789-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need 2 user accounts.</span></span>

<span data-ttu-id="bf789-109">Podemos crear un solo grupo de usuarios con el propósito de asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="bf789-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="bf789-110">Podemos unir ambos usuarios al mismo grupo y aplicar una licencia de Intune y asistencia remota a ese grupo.</span><span class="sxs-lookup"><span data-stu-id="bf789-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="bf789-111">Si no&#39;ya tiene acceso a dos cuentas de AAD en un grupo de usuarios que puede usar; Estas son las guías de inicio rápido para:</span><span class="sxs-lookup"><span data-stu-id="bf789-111">If you don&#39;t already have access to two AAD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="bf789-112">Cómo crear un usuario</span><span class="sxs-lookup"><span data-stu-id="bf789-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="bf789-113">Cómo crear un grupo</span><span class="sxs-lookup"><span data-stu-id="bf789-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="bf789-114">[Agregar usuarios a un grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : agregar usuarios creados a crear grupo</span><span class="sxs-lookup"><span data-stu-id="bf789-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="bf789-115">[Configurar AAD para permitir que un grupo de usuarios se una](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) a los dispositivos: Asegúrese de que el nuevo grupo de usuarios tiene permiso para inscribir dispositivos en AAD</span><span class="sxs-lookup"><span data-stu-id="bf789-115">[Configure AAD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to AAD</span></span>

## <span data-ttu-id="bf789-116">Inscripción automática en HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bf789-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="bf789-117">Para tener una experiencia fluida y fluida, la configuración de Azure Active Directory join (AADJ) y la inscripción automática en Intune para HoloLens 2 es la manera de ir.</span><span class="sxs-lookup"><span data-stu-id="bf789-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="bf789-118">Esto permitirá a los usuarios simplemente introducir las credenciales de inicio de sesión de su organización durante OOBE y se registrarán automáticamente con AAD e inscribirán el dispositivo en MDM.</span><span class="sxs-lookup"><span data-stu-id="bf789-118">This will allow users to simply input their organization log-in credentials during OOBE and automatically register with AAD and enroll the device into MDM.</span></span>

<span data-ttu-id="bf789-119">Al usar [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) , podemos seleccionar servicios y navegar por unas pocas páginas hasta que podamos seleccionar obtener una prueba Premium.</span><span class="sxs-lookup"><span data-stu-id="bf789-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="bf789-120">Muchas notificaciones: Azure Active Directory Premium 1 y 2, para la inscripción automática P1 es suficiente.</span><span class="sxs-lookup"><span data-stu-id="bf789-120">You many notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="bf789-121">Podemos seleccionar Intune y seleccionar el ámbito de usuario para la inscripción automática y seleccionar el grupo que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bf789-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="bf789-122">Para obtener más detalles y pasos, lea la guía sobre [Cómo habilitar la inscripción automática para Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span><span class="sxs-lookup"><span data-stu-id="bf789-122">For full details and steps please read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="bf789-123">Licencias de aplicación</span><span class="sxs-lookup"><span data-stu-id="bf789-123">Application Licenses</span></span>

<span data-ttu-id="bf789-124">Una licencia de aplicación permite a un usuario instalar aplicaciones compradas por la empresa o actualizar de una prueba gratuita a la versión completa de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf789-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="bf789-125">Las licencias de aplicación se pueden aplicar a usuarios, grupos de usuarios o grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf789-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="bf789-126">&#39;s necesita que las licencias de asistencia remota para los usuarios de su organización utilicen asistencia remota.</span><span class="sxs-lookup"><span data-stu-id="bf789-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="bf789-127">Para el propósito de esta guía, asignaremos licencias de asistencia remota al grupo de usuarios que hemos creado anteriormente en [usuarios y grupos de Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span><span class="sxs-lookup"><span data-stu-id="bf789-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="bf789-128">Los requisitos para las licencias pueden variar según si el usuario realizará la llamada de asistencia remota desde un dispositivo o será un colaborador remoto de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bf789-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="bf789-129">De forma predeterminada, están marcadas las casillas asistencia remota y equipos.</span><span class="sxs-lookup"><span data-stu-id="bf789-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="bf789-130">Para los fines de esta guía, sugerimos que dejen las casillas predeterminadas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="bf789-130">For the purposes of this guide, we suggest to leave the default boxes checked.</span></span>

1. <span data-ttu-id="bf789-131">Obtenga más información sobre los diferentes [requisitos de licencias y productos por rol](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span><span class="sxs-lookup"><span data-stu-id="bf789-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="bf789-132">Existen varios tipos diferentes de licencias de asistencia remota, así que asegúrese de tomar las correctas para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="bf789-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="bf789-133">&#39;necesario [adquirir la licencia](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span><span class="sxs-lookup"><span data-stu-id="bf789-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="bf789-134">[Aplicar las licencias](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) al grupo.</span><span class="sxs-lookup"><span data-stu-id="bf789-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="bf789-135">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="bf789-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf789-136">Implementación de nube conectada-implementar</span><span class="sxs-lookup"><span data-stu-id="bf789-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)