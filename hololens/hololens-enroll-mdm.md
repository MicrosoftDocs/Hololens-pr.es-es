---
title: Inscripción de HoloLens en la MDM
description: Aprende a inscribir HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
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
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400680"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="1c8ca-103">Inscripción de HoloLens en la MDM</span><span class="sxs-lookup"><span data-stu-id="1c8ca-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="1c8ca-104">Puedes administrar varios dispositivos de Microsoft HoloLens simultáneamente con soluciones como [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="1c8ca-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="1c8ca-105">Podrás administrar la configuración, seleccionar qué aplicaciones se instalarán y establecer las opciones de configuración de seguridad adaptadas a las necesidades de tu organización.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="1c8ca-106">Consulta [Administrar dispositivos que ejecuten Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), los [proveedores de servicios de configuración (CSP) que se admiten en Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) y las [directivas compatibles con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="1c8ca-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="1c8ca-107">La administración de dispositivos móviles (MDM), por ejemplo, las características VPN, BitLocker y de modo de pantalla completa, solo está disponible cuando actualizas a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1c8ca-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="1c8ca-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c8ca-108">Requirements</span></span>

 <span data-ttu-id="1c8ca-109">Tu organización tendrá que configurar la Administración de dispositivos móviles (MDM) para administrar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="1c8ca-110">El proveedor de MDM puede ser Microsoft InTune o un proveedor externo que use las API de MDM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="1c8ca-111">Distintas formas de inscribirse</span><span class="sxs-lookup"><span data-stu-id="1c8ca-111">Different ways to enroll</span></span>

<span data-ttu-id="1c8ca-112">Según el tipo de identidad [elegido durante](hololens-identity.md) la OOBE o después del inicio de sesión, hay diferentes métodos de inscripción.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="1c8ca-113">Si Identity es Azure AD, ya sea durante OOBE o **configuración app**Access Work o el  ->  **botón School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="1c8ca-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="1c8ca-114">Para Azure AD, [la inscripción automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) solo se produce si Azure AD se ha configurado con direcciones URL de inscripción.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span> 
     
- <span data-ttu-id="1c8ca-115">Si Identity es Azure AD y el dispositivo se ha registrado previamente con el servidor MDM de Intune con un perfil de configuración específico asignado a él, se producirá la inscripción de Azure AD-Join [y MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) automática durante la OOBE.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="1c8ca-116">También denominado [Flujo de Piloto automático](hololens2-autopilot.md) Disponible en [compilaciones 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="1c8ca-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="1c8ca-117">Si Identity es MSA, usa **configuración App**  ->  **Access Work o el botón School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="1c8ca-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="1c8ca-118">También se denomina flujo Agregar cuenta de trabajo (AWA).</span><span class="sxs-lookup"><span data-stu-id="1c8ca-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="1c8ca-119">Si Identity es Usuario local, usa **Configuración App**Access Work  ->  **o School**Enroll solo en el vínculo de administración de  ->  **dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="1c8ca-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="1c8ca-120">También se denomina flujo de inscripción MDM puro.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="1c8ca-121">Una vez que el dispositivo esté inscrito en el servidor MDM, la aplicación Configuración ahora reflejará que el dispositivo está inscrito en la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="1c8ca-122">Inscripción automática en la MDM</span><span class="sxs-lookup"><span data-stu-id="1c8ca-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="1c8ca-123">Si su organización tiene una suscripción a [Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) y una solución MDM que acepta un token de Azure AD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción de MDM después de que el usuario inicie sesión con su cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="1c8ca-124">Aprende a configurar la inscripción de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="1c8ca-125">Cuando se habilita la inscripción automática, no es necesaria ninguna inscripción manual adicional.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-125">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="1c8ca-126">Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="1c8ca-127">Cuando un dispositivo está unido a Azure AD, puede afectar a quién consideró el [propietario del dispositivo](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="1c8ca-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="1c8ca-128">Desenroll HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="1c8ca-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="1c8ca-129">Aunque HoloLens 2 es un dispositivo Windows 10, no se puede simplemente deshacer la inscripción de Intune.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-129">Although HoloLens 2 is Windows 10 device, it cannot be simply unenrolled from Intune.</span></span> <span data-ttu-id="1c8ca-130">Si desea desasoyar HoloLens de Azure AD o volver a unirse a otro inquilino de Azure AD, debe [restablecer o reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1c8ca-130">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>