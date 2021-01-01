---
title: Inscripción de HoloLens en la MDM
description: Inscribe HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7c17cbf88fc2e7a6dcd9aa600ad6e6910edb29a8
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253237"
---
# <span data-ttu-id="f742d-103">Inscripción de HoloLens en la MDM</span><span class="sxs-lookup"><span data-stu-id="f742d-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="f742d-104">Puede administrar varios dispositivos de Microsoft HoloLens a la vez mediante soluciones como [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="f742d-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="f742d-105">Podrás administrar la configuración, seleccionar qué aplicaciones se instalarán y establecer las opciones de configuración de seguridad adaptadas a las necesidades de tu organización.</span><span class="sxs-lookup"><span data-stu-id="f742d-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="f742d-106">Consulta [Administrar dispositivos que ejecuten Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), los [proveedores de servicios de configuración (CSP) que se admiten en Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) y las [directivas compatibles con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="f742d-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="f742d-107">La administración de dispositivos móviles (MDM), por ejemplo, las características VPN, BitLocker y de modo de pantalla completa, solo está disponible cuando actualizas a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="f742d-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="f742d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f742d-108">Requirements</span></span>

 <span data-ttu-id="f742d-109">Para administrar dispositivos HoloLens, tu organización debe tener configurada la configuración de la administración de dispositivos móviles (MDM).</span><span class="sxs-lookup"><span data-stu-id="f742d-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="f742d-110">El proveedor de MDM puede ser Microsoft InTune o un proveedor externo que use las API de MDM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f742d-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="f742d-111">Diferentes formas de inscribirse</span><span class="sxs-lookup"><span data-stu-id="f742d-111">Different ways to enroll</span></span>

<span data-ttu-id="f742d-112">Según el tipo de identidad elegido durante la OOBE o el inicio de sesión de post, existen diferentes métodos de inscripción.</span><span class="sxs-lookup"><span data-stu-id="f742d-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="f742d-113">Para obtener más información sobre cada tipo de identidad en HoloLens, visita [esta página](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="f742d-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="f742d-114">Si Identity es Azure ad, entonces durante el acceso a la aplicación de configuración de Oobe o de **configuración de App**,  ->  botón**trabajo o escuela**  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="f742d-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="f742d-115">Para Azure AD, la inscripción automática de MDM solo se produce si Azure AD se ha configurado con direcciones URL de inscripción.</span><span class="sxs-lookup"><span data-stu-id="f742d-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="f742d-116">Si la identidad es Azure AD y el dispositivo se ha registrado previamente con el servidor MDM de Intune y tiene asignado un perfil de configuración específico, Azure AD-Join y la inscripción se producirá automáticamente durante la instalación de OOBE.</span><span class="sxs-lookup"><span data-stu-id="f742d-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="f742d-117">También se denomina [flujo piloto automático](hololens2-autopilot.md) disponible en las [compilaciones de 19041.1103 +](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="f742d-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="f742d-118">Si Identity es MSA, use **Settings**  ->  **Access App Connect Work o**el botón School  ->  **Connect** .</span><span class="sxs-lookup"><span data-stu-id="f742d-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="f742d-119">También se conoce como agregar flujo de trabajo (AWA).</span><span class="sxs-lookup"><span data-stu-id="f742d-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="f742d-120">Si se trata de una identidad de usuario local, use la configuración de la **aplicación**  ->  **Access o la escuela**  ->  **inscribirse solo en el vínculo administración de dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="f742d-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="f742d-121">También se denomina flujo de inscripción de MDM puro.</span><span class="sxs-lookup"><span data-stu-id="f742d-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="f742d-122">Una vez que el dispositivo se haya inscrito en el servidor MDM, la aplicación configuración reflejará ahora que el dispositivo se ha inscrito en la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f742d-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="f742d-123">Inscripción automática en la MDM</span><span class="sxs-lookup"><span data-stu-id="f742d-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="f742d-124">Si su organización usa Azure Active Directory (Azure AD) y una solución MDM que acepta un token de Azure AD para la autenticación (actualmente, solo se admite en Microsoft Intune y en el reloj de la guardia), su administrador de ti puede configurar Azure AD para que permita automáticamente la inscripción de MDM después de que el usuario inicie sesión con su cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f742d-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="f742d-125">Aprende a configurar la inscripción de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f742d-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="f742d-126">Cuando se habilita la inscripción automática, no es necesaria ninguna inscripción manual adicional.</span><span class="sxs-lookup"><span data-stu-id="f742d-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="f742d-127">Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="f742d-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="f742d-128">Cuando se une un dispositivo a Azure AD, puede afectar a la persona que consideró al [propietario del dispositivo](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="f742d-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="f742d-129">Anular inscripción de HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="f742d-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="f742d-130">Para obtener más información acerca de cómo anular la inscripción a un dispositivo, visita [esta página](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="f742d-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
