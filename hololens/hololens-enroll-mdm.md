---
title: Inscripción de HoloLens en la MDM
description: Obtenga información sobre cómo inscribir HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310209"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="d53f2-103">Inscripción de HoloLens en la MDM</span><span class="sxs-lookup"><span data-stu-id="d53f2-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="d53f2-104">Puede administrar varios dispositivos Microsoft HoloLens simultáneamente mediante soluciones [como Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="d53f2-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="d53f2-105">Podrás administrar la configuración, seleccionar qué aplicaciones instalar y establecer las opciones de configuración de seguridad adaptadas a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="d53f2-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="d53f2-106">Consulte [Administrar dispositivos](https://docs.microsoft.com/intune/windows-holographic-for-business)que ejecutan Windows Holographic con Microsoft Intune , los proveedores de servicios de configuración [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)que se admiten en Windows Holographic y las directivas compatibles [con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="d53f2-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="d53f2-107">La administración de dispositivos móviles (MDM), incluidas las características vpn, Bitlocker y pantalla completa, solo está disponible cuando se actualiza [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d53f2-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="d53f2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d53f2-108">Requirements</span></span>

 <span data-ttu-id="d53f2-109">Su organización tendrá que configurar Mobile Administración de dispositivos (MDM) para administrar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="d53f2-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="d53f2-110">El proveedor de MDM puede ser Microsoft Intune o un proveedor externo que use las API de MDM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d53f2-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="d53f2-111">Distintas formas de inscribirse</span><span class="sxs-lookup"><span data-stu-id="d53f2-111">Different ways to enroll</span></span>

<span data-ttu-id="d53f2-112">En función del tipo de [identidad elegido](hololens-identity.md) durante la OOBE o después del inicio de sesión, hay diferentes métodos de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d53f2-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="d53f2-113">Si identity está Azure AD, durante el botón OOBE o **Configuración de App** Access Work o  ->  **School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="d53f2-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="d53f2-114">Por Azure AD, [la inscripción automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) solo se produce si Azure AD se ha configurado con direcciones URL de inscripción.</span><span class="sxs-lookup"><span data-stu-id="d53f2-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="d53f2-115">Si identity es Azure AD y el dispositivo se ha registrado previamente con el servidor MDM de Intune con un perfil de configuración específico asignado, azure AD-Join y la inscripción automática de [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se producirán durante la configuración automática.</span><span class="sxs-lookup"><span data-stu-id="d53f2-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="d53f2-116">También se [denomina Flujo de Autopilot](hololens2-autopilot.md) disponible [en las compilaciones 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="d53f2-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="d53f2-117">Si Identity es MSA, use el botón **Configuración de App** Access Work o  ->  **School**  ->  **Connect.**</span><span class="sxs-lookup"><span data-stu-id="d53f2-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="d53f2-118">También se denomina Agregar flujo de cuenta de trabajo (AWA).</span><span class="sxs-lookup"><span data-stu-id="d53f2-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="d53f2-119">Si Identity es Usuario local, use Configuración **App**  ->  **Access Work o School** Enroll solo en el vínculo de administración de  ->  **dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="d53f2-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="d53f2-120">También se denomina flujo de inscripción mdm pura.</span><span class="sxs-lookup"><span data-stu-id="d53f2-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="d53f2-121">Una vez que el dispositivo se inscriba con el servidor MDM, la aplicación Configuración ahora reflejará que el dispositivo está inscrito en la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d53f2-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="d53f2-122">Inscripción automática en la MDM</span><span class="sxs-lookup"><span data-stu-id="d53f2-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="d53f2-123">Si su organización tiene una suscripción de [Azure Premium,](https://azure.microsoft.com/overview/)usa Azure Active Directory (Azure AD) y una solución MDM que acepta un token de Azure AD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción de MDM después de que el usuario inicie sesión con su cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d53f2-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="d53f2-124">Aprende a configurar la inscripción de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d53f2-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="d53f2-125">Cuando la inscripción automática está habilitada, no se necesita ninguna inscripción manual adicional.</span><span class="sxs-lookup"><span data-stu-id="d53f2-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="d53f2-126">Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="d53f2-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="d53f2-127">Cuando un dispositivo se Azure AD unido, puede afectar a quién consideró [el propietario del dispositivo.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="d53f2-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="d53f2-128">Desarollar HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="d53f2-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="d53f2-129">Según el método de inscripción, es posible que la inscripción del dispositivo no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d53f2-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="d53f2-130">Si el dispositivo se inscribió con una Azure AD o Autopilot, no se puede inscribir desde Intune.</span><span class="sxs-lookup"><span data-stu-id="d53f2-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="d53f2-131">Si desea desasociar HoloLens de Azure AD o volver Azure AD un inquilino diferente Azure AD, debe restablecer [o](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) volver a actualizar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53f2-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="d53f2-132">Si el dispositivo se inscribió desde una cuenta de MSA que agregó una cuenta de trabajo o desde una cuenta local que solo se inscribió en la administración de dispositivos, puede deshacer la inscripción del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53f2-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="d53f2-133">Abra el menú Inicio y, a continuación, seleccione el botón **Configuración Acceso** a la aplicación Trabajo  ->  **o Escuela**  ->  *SuCuenta*  ->  **Desconectar.**</span><span class="sxs-lookup"><span data-stu-id="d53f2-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>