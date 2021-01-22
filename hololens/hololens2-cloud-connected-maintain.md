---
title: 'Guía de implementación: implementación de HoloLens 2 conectada en la nube a escala con asistencia remota: mantenimiento'
description: Manténgase al día con nuestras sugerencias para mantener y admitir dispositivos HoloLens a través de una red conectada a la nube.
keywords: HoloLens, administración, conectado a la nube, Asistencia remota, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283901"
---
# <span data-ttu-id="a64e8-104">Mantenimiento: Guía conectada a la nube</span><span class="sxs-lookup"><span data-stu-id="a64e8-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="a64e8-105">Actualizaciones</span><span class="sxs-lookup"><span data-stu-id="a64e8-105">Updates</span></span>

<span data-ttu-id="a64e8-106">Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a64e8-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="a64e8-107">Aprende a administrar las actualizaciones [de HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) incluidos los días programados, la hora programada y la configuración de horas activas en el dispositivo para que se actualice fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="a64e8-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="a64e8-108">Asistencia remota es una In-Box aplicación y se puede actualizar a través de la aplicación de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="a64e8-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="a64e8-109">Para todas las aplicaciones que se descargan a través de Microsoft Store, se pueden actualizar a través de la propia aplicación [de Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) manualmente.</span><span class="sxs-lookup"><span data-stu-id="a64e8-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="a64e8-110">Plan de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="a64e8-110">Support Plan</span></span>

<span data-ttu-id="a64e8-111">Un plan de soporte es una cosa excelente que debe tener en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a64e8-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="a64e8-112">Es útil contar con alguien o un grupo formado para solucionar problemas del proceso de inscripción en dispositivos HoloLens y también el uso general del dispositivo HoloLens dentro de la organización.</span><span class="sxs-lookup"><span data-stu-id="a64e8-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="a64e8-113">Para permitir que los usuarios tengan la resolución más rápida de sus problemas, le sugerimos que el proceso de escalación se controle de forma similar a este orden:</span><span class="sxs-lookup"><span data-stu-id="a64e8-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="a64e8-114">Su servicio de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="a64e8-114">Your Support desk.</span></span>
2. <span data-ttu-id="a64e8-115">Su equipo de expertos de HoloLens</span><span class="sxs-lookup"><span data-stu-id="a64e8-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="a64e8-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Documentos para la solución de problemas de HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="a64e8-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="a64e8-117">Contactar con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="a64e8-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="a64e8-118">Plan de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a64e8-118">Development Plan</span></span>

<span data-ttu-id="a64e8-119">Con el dispositivo inscrito correctamente, ahora estás preparado para implementar aplicaciones de línea de negocio (aplicaciones de LÍNEA DEB) en tus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a64e8-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="a64e8-120">Se trata de aplicaciones personalizadas creadas para las necesidades&#39;organización.</span><span class="sxs-lookup"><span data-stu-id="a64e8-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="a64e8-121">Si ya tienes una aplicación de línea de negocio,&#39;estás listo para implementar la aplicación a [través de MDM.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="a64e8-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="a64e8-122">Si prefiere&#39;otro método, revise la introducción a la implementación de aplicaciones de [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para obtener más información sobre los métodos de implementación de la aplicación lob en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a64e8-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="a64e8-123">Si aún&#39;crear tu propia aplicación de LOB o aún estás en proceso de creación, [](https://docs.microsoft.com/windows/mixed-reality/design/design) revisa nuestros documentos de desarrollo de realidad mixta para empezar a diseñar y crear prototipos, o aprende los conceptos básicos para empezar a desarrollar realidad [mixta.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="a64e8-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="a64e8-124">Administración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a64e8-124">Device Management</span></span> 

<span data-ttu-id="a64e8-125">Aunque en esta guía se habla sobre cómo configurar la administración de dispositivos móviles (MDM), no se utilizó para aplicar restricciones de dispositivos o se aplicaron directivas a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a64e8-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="a64e8-126">La administración de dispositivos se puede usar para permitir el acceso al insertar certificados o restringir el acceso con una variedad de restricciones de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a64e8-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="a64e8-127">En muchos casos, los dispositivos pueden tener restricciones de conectividad como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o el micrófono.</span><span class="sxs-lookup"><span data-stu-id="a64e8-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="a64e8-128">Si alguno de estos intereses te interesa, te animamos a leer nuestra página [de restricciones de dispositivos comunes.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="a64e8-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="a64e8-129">Hay otras restricciones de dispositivo más complejas que puedes usar.</span><span class="sxs-lookup"><span data-stu-id="a64e8-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="a64e8-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a64e8-130">Such as:</span></span>

- <span data-ttu-id="a64e8-131">Limitar las páginas que se pueden ver en la aplicación Configuración mediante [SettingsPageVisibility,](settings-uri-list.md)lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su conexión Wi-Fi usuario.</span><span class="sxs-lookup"><span data-stu-id="a64e8-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="a64e8-132">Usa [el modo de pantalla completa](hololens-kiosk.md) para limitar la interfaz de usuario que se presenta a los usuarios de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a64e8-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="a64e8-133">Puedes establecer quioscos para mostrar una sola aplicación o varias aplicaciones con una página de inicio personalizada.</span><span class="sxs-lookup"><span data-stu-id="a64e8-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="a64e8-134">Los quioscos también pueden presentar distintas experiencias a diferentes usuarios.</span><span class="sxs-lookup"><span data-stu-id="a64e8-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="a64e8-135">[Control de aplicaciones de Windows (WDAC) para](windows-defender-application-control-wdac.md) evitar que aplicaciones o procesos específicos se inicien por completo.</span><span class="sxs-lookup"><span data-stu-id="a64e8-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="a64e8-136">Si quieres obtener información sobre otros métodos de administración de dispositivos o restricciones de dispositivos, sigue el siguiente paso y lee nuestra introducción a la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a64e8-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="a64e8-137">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a64e8-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a64e8-138">Leer la introducción a los SSP y la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a64e8-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)