---
title: 'Guía de implementación: implementación HoloLens 2 en la nube a escala con Remote Assist - Mantener'
description: Manténgase al día con nuestras sugerencias para mantener y admitir HoloLens dispositivos a través de una red conectada a la nube.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635167"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="edcfb-104">Mantener: guía conectada a la nube</span><span class="sxs-lookup"><span data-stu-id="edcfb-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="edcfb-105">Actualizaciones</span><span class="sxs-lookup"><span data-stu-id="edcfb-105">Updates</span></span>

<span data-ttu-id="edcfb-106">Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="edcfb-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="edcfb-107">Obtenga información sobre cómo administrar [HoloLens](/hololens/hololens-updates) actualizaciones, incluidos los días programados, la hora programada y la configuración de horas activas en el dispositivo para que se actualice fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="edcfb-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="edcfb-108">Remote Assist es una In-Box y se puede actualizar a través de Microsoft Store aplicación.</span><span class="sxs-lookup"><span data-stu-id="edcfb-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="edcfb-109">Para todas las aplicaciones que se descargan a través del Microsoft Store pueden actualizarse a través de la [propia Microsoft Store](/hololens/holographic-store-apps#update-apps) aplicación de forma manual.</span><span class="sxs-lookup"><span data-stu-id="edcfb-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="edcfb-110">Plan de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="edcfb-110">Support Plan</span></span>

<span data-ttu-id="edcfb-111">Un plan de soporte técnico es una excelente opción para tener en marcha.</span><span class="sxs-lookup"><span data-stu-id="edcfb-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="edcfb-112">Es útil tener a alguien o a un grupo entrenado para solucionar problemas del proceso de inscripción en dispositivos HoloLens y también el uso general del dispositivo HoloLens dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="edcfb-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="edcfb-113">Para permitir que los usuarios tengan la resolución más rápida de sus problemas, se recomienda que el proceso de extensión se controle de forma similar a este orden:</span><span class="sxs-lookup"><span data-stu-id="edcfb-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="edcfb-114">El servicio de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="edcfb-114">Your Support desk.</span></span>
2. <span data-ttu-id="edcfb-115">Su equipo HoloLens expertos</span><span class="sxs-lookup"><span data-stu-id="edcfb-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="edcfb-116">[HoloLens Docs](/hololens/)  /  [HoloLens de solución de problemas](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="edcfb-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="edcfb-117">Póngase en contacto con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="edcfb-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="edcfb-118">Plan de desarrollo</span><span class="sxs-lookup"><span data-stu-id="edcfb-118">Development Plan</span></span>

<span data-ttu-id="edcfb-119">Con el dispositivo inscrito correctamente, ahora está preparado para implementar aplicaciones de línea de negocio (aplicaciones loB) en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edcfb-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="edcfb-120">Se trata de aplicaciones personalizadas creadas para las necesidades&#39;organización.</span><span class="sxs-lookup"><span data-stu-id="edcfb-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="edcfb-121">Si ya tiene una aplicación de línea de negocio,&#39;listo para implementar la aplicación a [través de MDM.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="edcfb-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="edcfb-122">Si prefiere&#39;método diferente, revise la introducción a la implementación de aplicaciones de [HoloLens 2 para](/hololens/app-deploy-overview) obtener más métodos de implementación de la aplicación lob en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edcfb-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="edcfb-123">Si aún&#39;ha creado su propia aplicación de LOB o todavía está en proceso de creación, revise nuestros documentos de desarrollo de realidad mixta para empezar a diseñar y crear prototipos u aprender los conceptos básicos para empezar a trabajar con el desarrollo de realidad [mixta.](/windows/mixed-reality/discover/get-started-with-mr) [](/windows/mixed-reality/design/design)</span><span class="sxs-lookup"><span data-stu-id="edcfb-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="edcfb-124">Administración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="edcfb-124">Device Management</span></span> 

<span data-ttu-id="edcfb-125">Aunque en esta guía se ha hablado sobre la configuración de Mobile Administración de dispositivos (MDM), no se empleó para aplicar restricciones de dispositivos o se aplicaron directivas a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edcfb-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="edcfb-126">La administración de dispositivos se puede usar para permitir el acceso mediante la insertar certificados o restringir el acceso con una variedad de restricciones de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edcfb-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="edcfb-127">En muchos casos, los dispositivos pueden tener restricciones de conectividad como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o al micrófono.</span><span class="sxs-lookup"><span data-stu-id="edcfb-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="edcfb-128">Si alguno de estos intereses le interesa, le recomendamos que lea nuestra página [de restricciones de dispositivos comunes](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="edcfb-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="edcfb-129">Hay otras restricciones de dispositivos más complejas que puede usar.</span><span class="sxs-lookup"><span data-stu-id="edcfb-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="edcfb-130">Como:</span><span class="sxs-lookup"><span data-stu-id="edcfb-130">Such as:</span></span>

- <span data-ttu-id="edcfb-131">Limitación de las páginas que se pueden ver en la aplicación de Configuración mediante [SettingsPageVisibility](settings-uri-list.md), lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su conexión Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="edcfb-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="edcfb-132">Use [el modo de pantalla](hololens-kiosk.md) completa para limitar la interfaz de usuario que se presenta a los usuarios en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edcfb-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="edcfb-133">Puede establecer Quioscos para mostrar una sola aplicación o varias aplicaciones con una página de inicio personalizada.</span><span class="sxs-lookup"><span data-stu-id="edcfb-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="edcfb-134">Los quioscos también pueden presentar experiencias diferentes a distintos usuarios.</span><span class="sxs-lookup"><span data-stu-id="edcfb-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="edcfb-135">[Windows Application Control (WDAC) para](windows-defender-application-control-wdac.md) evitar que aplicaciones o procesos específicos se inicien por completo.</span><span class="sxs-lookup"><span data-stu-id="edcfb-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="edcfb-136">Si desea obtener información sobre otros métodos diferentes de administración de dispositivos o restricciones de dispositivos, siga el paso siguiente y lea la información general Administración de dispositivos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edcfb-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="edcfb-137">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="edcfb-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="edcfb-138">Lea la información general sobre los Administración de dispositivos DE CSP.</span><span class="sxs-lookup"><span data-stu-id="edcfb-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)