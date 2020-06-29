---
title: Directrices de infraestructura de HoloLens
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 65403589fa3d612290fdd59a4843da27c12a956c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830154"
---
# <span data-ttu-id="b05ed-102">Configure su red para HoloLens</span><span class="sxs-lookup"><span data-stu-id="b05ed-102">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="b05ed-103">Esta parte del documento necesitará las personas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b05ed-103">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="b05ed-104">Administrador de red con permisos para realizar cambios en el servidor proxy o firewall</span><span class="sxs-lookup"><span data-stu-id="b05ed-104">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="b05ed-105">Administrador de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b05ed-105">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="b05ed-106">Administrador de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="b05ed-106">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="b05ed-107">Requisitos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="b05ed-107">Infrastructure Requirements</span></span>

<span data-ttu-id="b05ed-108">HoloLens es, en esencia, un dispositivo Windows Mobile integrado en Azure.</span><span class="sxs-lookup"><span data-stu-id="b05ed-108">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="b05ed-109">Su funcionamiento es mejor en entornos comerciales con disponibilidad de red inalámbrica (Wi-Fi) y acceso a los servicios Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b05ed-109">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="b05ed-110">Entre los servicios de nube críticos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="b05ed-110">Critical cloud services include:</span></span>

- <span data-ttu-id="b05ed-111">Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="b05ed-111">Azure active directory (AAD)</span></span>
- <span data-ttu-id="b05ed-112">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="b05ed-112">Windows Update (WU)</span></span>

<span data-ttu-id="b05ed-113">Para administrar los dispositivos HoloLens a escala, los clientes comerciales necesitarán una infraestructura de gestión de movilidad empresarial (EMM) o de gestión de dispositivos móviles (MDM).</span><span class="sxs-lookup"><span data-stu-id="b05ed-113">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="b05ed-114">En esta guía se usa[Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como ejemplo, aunque cualquier proveedor compatible con Microsoft Policy es compatible con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b05ed-114">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="b05ed-115">Pregunte a su proveedor de administración de dispositivos móviles si son compatibles con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b05ed-115">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="b05ed-116">HoloLens admite un conjunto limitado de experiencias desconectadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="b05ed-116">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="b05ed-117">Compatibilidad con EAP de red inalámbrica</span><span class="sxs-lookup"><span data-stu-id="b05ed-117">Wireless network EAP support</span></span>

- <span data-ttu-id="b05ed-118">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b05ed-118">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="b05ed-119">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="b05ed-119">PEAP-TLS</span></span>
- <span data-ttu-id="b05ed-120">TLS</span><span class="sxs-lookup"><span data-stu-id="b05ed-120">TLS</span></span>
- <span data-ttu-id="b05ed-121">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="b05ed-121">TTLS-CHAP</span></span>
- <span data-ttu-id="b05ed-122">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b05ed-122">TTLS-CHAPv2</span></span>
- <span data-ttu-id="b05ed-123">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b05ed-123">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="b05ed-124">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="b05ed-124">TTLS-PAP</span></span>
- <span data-ttu-id="b05ed-125">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="b05ed-125">TTLS-TLS</span></span>

### <span data-ttu-id="b05ed-126">Requisitos de red específicos de HoloLens</span><span class="sxs-lookup"><span data-stu-id="b05ed-126">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="b05ed-127">Asegúrese de que [esta lista](hololens-offline.md) de puntos de conexión se permiten en su Firewall de red.</span><span class="sxs-lookup"><span data-stu-id="b05ed-127">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="b05ed-128">Esto permitirá que HoloLens funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="b05ed-128">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="b05ed-129">Requisitos de la red específicos de Remote Assist</span><span class="sxs-lookup"><span data-stu-id="b05ed-129">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="b05ed-130">El ancho de banda recomendado para un rendimiento óptimo de Remote Assist es 1,5 Mbps.</span><span class="sxs-lookup"><span data-stu-id="b05ed-130">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="b05ed-131">Encontrará información sobre los requisitos de red e información adicional [aquí](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="b05ed-131">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="b05ed-132">(Tenga en cuenta que, si la velocidad de su red no es de al menos 1,5 Mbps, el asistente remoto seguirá funcionando.</span><span class="sxs-lookup"><span data-stu-id="b05ed-132">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="b05ed-133">Sin embargo, es posible que se vea afectada la calidad).</span><span class="sxs-lookup"><span data-stu-id="b05ed-133">However, quality may suffer).</span></span>**
1. <span data-ttu-id="b05ed-134">Asegúrese de que estos puertos y URL estén permitidos en el firewall de red.</span><span class="sxs-lookup"><span data-stu-id="b05ed-134">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="b05ed-135">Esto permitirá que Microsoft Teams funcione.</span><span class="sxs-lookup"><span data-stu-id="b05ed-135">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="b05ed-136">La lista más reciente se puede encontrar [aquí](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="b05ed-136">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

### <span data-ttu-id="b05ed-137">Requisitos de red específicos de Guías</span><span class="sxs-lookup"><span data-stu-id="b05ed-137">Guides Specific Network Requirements</span></span>

<span data-ttu-id="b05ed-138">Las guías solo necesitan acceso de red para descargar y usar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b05ed-138">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="b05ed-139">Instrucciones de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b05ed-139">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="b05ed-140">Este paso es necesario solo si su empresa tiene un plan para administrar las aplicaciones HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b05ed-140">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="b05ed-141">Asegúrese de que tiene una licencia de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b05ed-141">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="b05ed-142">Para obtener más información, vea los [requisitos de licencias de HoloLens](hololens-licenses-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b05ed-142">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="b05ed-143">Si tiene previsto usar la inscripción automática, tendrá que [configurar la inscripción a Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="b05ed-143">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="b05ed-144">Asegúrese de que los usuarios de su empresa se encuentren en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b05ed-144">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="b05ed-145">Encontrará instrucciones para agregar usuarios [aquí](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="b05ed-145">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="b05ed-146">Recomendamos que los usuarios que necesiten licencias similares se agreguen al mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="b05ed-146">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="b05ed-147">Crear un grupo</span><span class="sxs-lookup"><span data-stu-id="b05ed-147">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="b05ed-148">Agregar usuarios a grupos</span><span class="sxs-lookup"><span data-stu-id="b05ed-148">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="b05ed-149">Asegúrese de que los usuarios (o grupos de usuarios) de su empresa tienen asignadas las licencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="b05ed-149">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="b05ed-150">Encontrará las instrucciones para asignar licencias [aquí](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="b05ed-150">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="b05ed-151">Siga este paso sólo si espera que los usuarios inscriban su dispositivo HoloLens o móvil a través de usted (hay tres opciones). Estos pasos aseguran que los usuarios (o grupo de usuarios) de su empresa puedan agregar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b05ed-151">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="b05ed-152">**Opción 1:** Conceder permiso a todos los usuarios para unir dispositivos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b05ed-152">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="b05ed-153">**Inicie sesión en Microsoft Azure Portal como administrador** > **Azure Active Directory** > **Dispositivos** > **Configuración de dispositivos** >
**Establezca Los usuarios puedan unir dispositivos a Azure AD en *Todos***</span><span class="sxs-lookup"><span data-stu-id="b05ed-153">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="b05ed-154">**Opción 2:** Conceder permisos a los usuarios y grupos seleccionados para unir los dispositivos a Azure AD **Inicie sesión como administrador en el Microsoft Azure Portal** > **Azure Active Directory** > **Dispositivos** > **Configuración de dispositivos** >
\*\*Establecer que los usuarios puedan unir dispositivos a Azure AD en \*Seleccionados\*\*\*
![Imagen que muestra la configuración de los dispositivos unidos a Azure AD</span><span class="sxs-lookup"><span data-stu-id="b05ed-154">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="b05ed-155">**Opción 3:** Puede impedir a todos los usuarios que unan sus dispositivos al dominio.</span><span class="sxs-lookup"><span data-stu-id="b05ed-155">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="b05ed-156">Esto quiere decir que todos Ios dispositivos tendrán que ser inscritos de forma manual.</span><span class="sxs-lookup"><span data-stu-id="b05ed-156">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="b05ed-157">Instrucciones del administrador de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="b05ed-157">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="b05ed-158">Administración continua de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b05ed-158">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="b05ed-159">Este paso es necesario solo si su empresa tiene un plan para administrar las aplicaciones HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b05ed-159">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="b05ed-160">La administración continua de los dispositivos dependerá de la infraestructura de la administración de dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="b05ed-160">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="b05ed-161">La mayoría tiene la misma funcionalidad general, pero la interfaz de usuario puede variar considerablemente.</span><span class="sxs-lookup"><span data-stu-id="b05ed-161">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="b05ed-162">[Proveedores de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) le permite crear e implementar la configuración de administración de los dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="b05ed-162">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="b05ed-163">Encontrará una lista de los CSP para HoloLens [aquí](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span><span class="sxs-lookup"><span data-stu-id="b05ed-163">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="b05ed-164">Las [directivas de cumplimiento](https://docs.microsoft.com/intune/device-compliance-get-started) son las reglas y la configuración que deben tener los dispositivos para cumplir con la infraestructura de su empresa.</span><span class="sxs-lookup"><span data-stu-id="b05ed-164">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="b05ed-165">Use estas directivas con el acceso condicional para bloquear el acceso a los recursos de la compañía en los dispositivos que no sean compatibles.</span><span class="sxs-lookup"><span data-stu-id="b05ed-165">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="b05ed-166">Por ejemplo, puede crear una directiva que requiera que se habilite BitLocker.</span><span class="sxs-lookup"><span data-stu-id="b05ed-166">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="b05ed-167">[crear una directiva de cumplimiento](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="b05ed-167">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="b05ed-168">El acceso condicional permite o impide que los dispositivos móviles y las aplicaciones móviles obtengan acceso a los recursos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="b05ed-168">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="b05ed-169">Le puede ser útil disponer de dos documentos [planear la implementación de la entidad emisora de certificados](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) y [procedimientos recomendados](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span><span class="sxs-lookup"><span data-stu-id="b05ed-169">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="b05ed-170">[este artículo](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) habla sobre las herramientas de administración de Intune para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b05ed-170">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="b05ed-171">Crear un perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b05ed-171">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="b05ed-172">Administrar actualizaciones</span><span class="sxs-lookup"><span data-stu-id="b05ed-172">Manage updates</span></span>

<span data-ttu-id="b05ed-173">Intune incluye una función llamada timbres de actualización para los dispositivos de Windows 10, incluyendo HoloLens 2 y HoloLens v1 (con Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="b05ed-173">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="b05ed-174">Los timbres de actualización incluyen un grupo de configuraciones que determinan cómo y cuándo se instalarán las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b05ed-174">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="b05ed-175">Por ejemplo, puede elegir entre crear una ventana de mantenimiento para instalar actualizaciones o reiniciar el dispositivo cuando estas sean instaladas</span><span class="sxs-lookup"><span data-stu-id="b05ed-175">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="b05ed-176">También puede optar por pausar las actualizaciones de manera indefinida hasta que esté listo para actualizar.</span><span class="sxs-lookup"><span data-stu-id="b05ed-176">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="b05ed-177">Obtenga más información sobre la [configuración de los timbres de actualización con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="b05ed-177">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="b05ed-178">Administración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b05ed-178">Application management</span></span>

<span data-ttu-id="b05ed-179">Administrar las aplicaciones de HoloLens a través de:</span><span class="sxs-lookup"><span data-stu-id="b05ed-179">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="b05ed-180">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b05ed-180">Microsoft Store</span></span>  
  <span data-ttu-id="b05ed-181">La Microsoft Store es la mejor forma de distribuir y usar las aplicaciones dentro de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b05ed-181">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="b05ed-182">En la tienda hay un gran conjunto de aplicaciones básicas de HoloLens que ya se encuentran disponibles o bien puede [publicar su propia aplicación](https://docs.microsoft.com/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="b05ed-182">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="b05ed-183">Todas las aplicaciones de la tienda se encuentran disponibles para el público en general, en caso de que no lo esté, visite Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="b05ed-183">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="b05ed-184">Microsoft Store para Business</span><span class="sxs-lookup"><span data-stu-id="b05ed-184">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="b05ed-185">Microsoft Store para Empresas y Education son tiendas personalizadas para el entorno corporativo.</span><span class="sxs-lookup"><span data-stu-id="b05ed-185">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="b05ed-186">Esto le permite utilizar la Microsoft Store integrada en Windows 10 y HoloLens para buscar, adquirir, distribuir y administrar aplicaciones para su empresa.</span><span class="sxs-lookup"><span data-stu-id="b05ed-186">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="b05ed-187">También le permite implementar aplicaciones específicas a su entorno comercial pero no a escala mundial.</span><span class="sxs-lookup"><span data-stu-id="b05ed-187">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="b05ed-188">Implementación y administración de aplicaciones a través de Intune u otra solución para la administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="b05ed-188">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="b05ed-189">La mayoría de las soluciones para la administración de dispositivos móviles, incluyendo a Intune, proporcionan una forma de implementar aplicaciones de la línea de negocios directamente a un conjunto de dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="b05ed-189">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="b05ed-190">Vea este artículo para [instalar la aplicación Intune](https://docs.microsoft.com/intune/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="b05ed-190">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="b05ed-191">El portal de dispositivos _no es recomendable_</span><span class="sxs-lookup"><span data-stu-id="b05ed-191">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="b05ed-192">Las aplicaciones también pueden ser instaladas directamente en HoloLens usando el Portal de dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="b05ed-192">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="b05ed-193">Esto no es recomendable ya que el modo de desarrollador tiene que estar habilitado para usar el portal de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b05ed-193">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="b05ed-194">Obtenga más información sobre la [instalación de aplicaciones en HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span><span class="sxs-lookup"><span data-stu-id="b05ed-194">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="b05ed-195">Certificados</span><span class="sxs-lookup"><span data-stu-id="b05ed-195">Certificates</span></span>

<span data-ttu-id="b05ed-196">Puede distribuir los certificados mediante su proveedor de MDM.</span><span class="sxs-lookup"><span data-stu-id="b05ed-196">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="b05ed-197">Si su empresa requiere certificados, Intune soporta PKCS, PFX, y SCEP.</span><span class="sxs-lookup"><span data-stu-id="b05ed-197">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="b05ed-198">Es importante comprender cuál es el certificado adecuado para su empresa.</span><span class="sxs-lookup"><span data-stu-id="b05ed-198">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="b05ed-199">Visite [este vínculo](https://docs.microsoft.com/intune/protect/certificates-configure) para determinar cuál es el certificado más adecuado para usted.</span><span class="sxs-lookup"><span data-stu-id="b05ed-199">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="b05ed-200">Si tiene previsto usar certificados para la autenticación de HoloLens, puede que PFX o SCEP sean adecuados.</span><span class="sxs-lookup"><span data-stu-id="b05ed-200">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="b05ed-201">Puede encontrar los pasos requeridos para SCEP [aquí](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span><span class="sxs-lookup"><span data-stu-id="b05ed-201">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="b05ed-202">Cómo actualizar a Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="b05ed-202">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="b05ed-203">Windows Holographics for Business (commercial suite) está destinado exclusivamente para los dispositivos de primera generación de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b05ed-203">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="b05ed-204">No se aplicará el perfil en los dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b05ed-204">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="b05ed-205">Puede encontrar las instrucciones para la actualización a la commercial suite [aquí](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="b05ed-205">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="b05ed-206">Cómo configurar el modo de pantalla completa usando Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b05ed-206">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="b05ed-207">Sincronizar Microsoft Store con Intune ([aquí](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span><span class="sxs-lookup"><span data-stu-id="b05ed-207">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="b05ed-208">Comprobar la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="b05ed-208">Check your app settings</span></span>
    1. <span data-ttu-id="b05ed-209">Inicie sesión en su cuenta de empresa de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b05ed-209">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="b05ed-210">Administrar > Productos y servicios > Aplicaciones y software > Seleccione la aplicación que quiere sincronizar > Disponibilidad en la tienda privada > Seleccione "todos" o "grupos específicos"</span><span class="sxs-lookup"><span data-stu-id="b05ed-210">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="b05ed-211">Si no ve la aplicación que quiere, tendrá que "obtenerla" buscándola en la tienda.</span><span class="sxs-lookup"><span data-stu-id="b05ed-211">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="b05ed-212">**Haga clic en la barra de búsqueda de la esquina superior derecha > escriba el nombre de la aplicación > haga clic en la aplicación > seleccione "Obtener"**.</span><span class="sxs-lookup"><span data-stu-id="b05ed-212">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="b05ed-213">Si no puede ver sus aplicaciones en **Intune > Aplicaciones cliente > Aplicaciones**, es posible que tenga que volver a [sincronizar las aplicaciones](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps).</span><span class="sxs-lookup"><span data-stu-id="b05ed-213">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="b05ed-214">Crear un perfil de dispositivo para el modo de pantalla completa</span><span class="sxs-lookup"><span data-stu-id="b05ed-214">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="b05ed-215">Puede configurar diferentes usuarios para tener distintas experiencias en el modo de pantalla completa con "Azure AD" como "tipo de inicio de sesión de usuario".</span><span class="sxs-lookup"><span data-stu-id="b05ed-215">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="b05ed-216">Sin embargo, esta opción solo está disponible en el modo de pantalla completa de varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b05ed-216">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="b05ed-217">El modo de pantalla completa de varias aplicaciones funcionará con una sola aplicación y con varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b05ed-217">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Imagen que muestra la configuración del modo de pantalla completa en Intune](images/aad-kioskmode.png)

<span data-ttu-id="b05ed-219">Para ver otros servicios de MDM, consulte la documentación de su proveedor para obtener las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b05ed-219">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="b05ed-220">Si necesita utilizar una configuración personalizada y una configuración XML completa para habilitar la pantalla completa en su servicio de MDM, puede encontrar instrucciones adicionales [aquí](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span><span class="sxs-lookup"><span data-stu-id="b05ed-220">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="b05ed-221">Certificados y autenticación</span><span class="sxs-lookup"><span data-stu-id="b05ed-221">Certificates and Authentication</span></span>

<span data-ttu-id="b05ed-222">Los certificados se pueden implementar mediante MDM (vea "certificados" en la sección [MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span><span class="sxs-lookup"><span data-stu-id="b05ed-222">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="b05ed-223">Los certificados también pueden ser agregados a HoloLens a través del aprovisionamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="b05ed-223">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="b05ed-224">Para obtener más información, vea el [aprovisionamiento de HoloLens](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="b05ed-224">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="b05ed-225">Vínculos rápidos de Intune adicionales</span><span class="sxs-lookup"><span data-stu-id="b05ed-225">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="b05ed-226">[Crear perfiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) los perfiles le permiten agregar y configurar las opciones que se enviarán a los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="b05ed-226">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

