---
title: Inscribir HoloLens en MDM
description: Inscribe HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828695"
---
# <span data-ttu-id="8c4c9-103">Inscripción de HoloLens en la MDM</span><span class="sxs-lookup"><span data-stu-id="8c4c9-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="8c4c9-104">Puede administrar varios dispositivos de Microsoft HoloLens a la vez mediante soluciones como [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="8c4c9-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="8c4c9-105">Podrás administrar la configuración, seleccionar qué aplicaciones se instalarán y establecer las opciones de configuración de seguridad adaptadas a las necesidades de tu organización.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="8c4c9-106">Consulta [Administrar dispositivos que ejecuten Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), los [proveedores de servicios de configuración (CSP) que se admiten en Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) y las [directivas compatibles con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="8c4c9-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="8c4c9-107">La administración de dispositivos móviles (MDM), por ejemplo, las características VPN, BitLocker y de modo de pantalla completa, solo está disponible cuando actualizas a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8c4c9-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="8c4c9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c4c9-108">Requirements</span></span>

 <span data-ttu-id="8c4c9-109">Para administrar dispositivos HoloLens, tu organización debe tener configurada la configuración de la administración de dispositivos móviles (MDM).</span><span class="sxs-lookup"><span data-stu-id="8c4c9-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="8c4c9-110">El proveedor de MDM puede ser Microsoft InTune o un proveedor externo que use las API de MDM de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="8c4c9-111">Inscripción automática en la MDM</span><span class="sxs-lookup"><span data-stu-id="8c4c9-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="8c4c9-112">Si la organización usa Azure Active Directory (Azure AD) y una solución de MDM que acepte un token de AAD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción en la MDM después de que el usuario inicie sesión con su cuenta de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="8c4c9-113">Aprende a configurar la inscripción de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="8c4c9-114">Cuando se habilita la inscripción automática, no es necesaria ninguna inscripción manual adicional.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="8c4c9-115">Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="8c4c9-116">Inscripción mediante la aplicación Configuración</span><span class="sxs-lookup"><span data-stu-id="8c4c9-116">Enroll through Settings app</span></span>

 <span data-ttu-id="8c4c9-117">Si el dispositivo no se inscribe en la MDM durante la primera ejecución, el usuario puede inscribirlo manualmente en el servidor de MDM de la organización mediante la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="8c4c9-118">Dirígete a **Configuración** > **Cuentas** > **Obtener acceso al trabajo**.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="8c4c9-119">Selecciona **Inscribirse en la administración de dispositivos** y especifica la cuenta de la organización.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="8c4c9-120">Se te redirigirá a la página de inicio de sesión de la organización.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="8c4c9-121">Una vez que te hayas autenticado debidamente en el servidor de MDM, se mostrará un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="8c4c9-122">El dispositivo ya estará inscrito en el servidor de MDM.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="8c4c9-123">Ahora la aplicación Configuración reflejará que el dispositivo está inscrito en la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="8c4c9-124">Anular inscripción de HoloLens de Intune</span><span class="sxs-lookup"><span data-stu-id="8c4c9-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="8c4c9-125">No es posible [anular la inscripción](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) de HoloLens de Intune de manera remota.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="8c4c9-126">Si el administrador anula la inscripción del dispositivo con MDM, el dispositivo expirará y luego se eliminará del panel de Intune.</span><span class="sxs-lookup"><span data-stu-id="8c4c9-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
