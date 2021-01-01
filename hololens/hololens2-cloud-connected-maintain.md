---
title: 'Guía de implementación: implementación de la nube conectada a HoloLens 2 a escala con asistencia remota-mantenimiento'
description: Sugerencias para mantener dispositivos HoloLens en una red conectada en la nube
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252701"
---
# <span data-ttu-id="a8b96-104">Mantener-guía conectada a la nube</span><span class="sxs-lookup"><span data-stu-id="a8b96-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="a8b96-105">Actualizaciones</span><span class="sxs-lookup"><span data-stu-id="a8b96-105">Updates</span></span>

<span data-ttu-id="a8b96-106">Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a8b96-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="a8b96-107">Más información sobre cómo [administrar las actualizaciones de HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , incluidos días programados, tiempo programado y la configuración de horas activas en el dispositivo para que se actualice fuera del horario laboral.</span><span class="sxs-lookup"><span data-stu-id="a8b96-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="a8b96-108">Asistencia remota es una aplicación In-Box y puede actualizarse a través de la aplicación Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="a8b96-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="a8b96-109">Para todas las aplicaciones que se descargan a través de Microsoft Store, se pueden [actualizar mediante la aplicación de Microsoft Store en](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) forma manual.</span><span class="sxs-lookup"><span data-stu-id="a8b96-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="a8b96-110">Plan de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="a8b96-110">Support Plan</span></span>

<span data-ttu-id="a8b96-111">Un plan de soporte técnico es un aspecto excelente para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a8b96-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="a8b96-112">Es útil tener a una persona, o a un grupo con formación para solucionar el proceso de inscripción en dispositivos HoloLens, además del uso general del dispositivo HoloLens dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="a8b96-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="a8b96-113">Para que los usuarios puedan tener la resolución más rápida de sus problemas, sugerimos que el proceso de escalado se gestione de forma similar a la siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="a8b96-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="a8b96-114">Tu servicio de asistencia al cliente.</span><span class="sxs-lookup"><span data-stu-id="a8b96-114">Your Support desk.</span></span>
2. <span data-ttu-id="a8b96-115">Tu equipo de expertos de HoloLens</span><span class="sxs-lookup"><span data-stu-id="a8b96-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="a8b96-116">[Documentos](https://docs.microsoft.com/hololens/)  /  de HoloLens [Documentación para la solución de problemas de HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="a8b96-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="a8b96-117">Contactar con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="a8b96-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="a8b96-118">Plan de desarrollo</span><span class="sxs-lookup"><span data-stu-id="a8b96-118">Development Plan</span></span>

<span data-ttu-id="a8b96-119">Con el dispositivo correctamente inscrito, ahora está preparado para implementar las aplicaciones de la línea de negocios (aplicaciones LOB) en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a8b96-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="a8b96-120">Estas son aplicaciones personalizadas creadas para su organización&#39;s necesidades.</span><span class="sxs-lookup"><span data-stu-id="a8b96-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="a8b96-121">Si ya tiene una aplicación de línea de negocio,&#39;listo para [implementar la aplicación a través de MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span><span class="sxs-lookup"><span data-stu-id="a8b96-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="a8b96-122">Si&#39;d preferir un método diferente, revise la [información general sobre la implementación de la aplicación para HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para obtener más métodos para implementar su aplicación de LOB en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a8b96-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="a8b96-123">Si aún no ha&#39;creado su propia aplicación de LOB o aún está en proceso de creación, revise nuestros documentos de desarrollo de realidad mixta para [empezar a diseñar y generar prototipos](https://docs.microsoft.com/windows/mixed-reality/design/design) o aprender los conceptos básicos para empezar a usar el [desarrollo de realidad mixta.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="a8b96-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="a8b96-124">Administración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a8b96-124">Device Management</span></span> 

<span data-ttu-id="a8b96-125">Aunque en esta guía se ha comentado la configuración de la administración de dispositivos móviles (MDM), no se empleó para aplicar restricciones de dispositivo o directivas que se aplicaron a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a8b96-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="a8b96-126">La administración de dispositivos se puede usar para permitir el acceso mediante la inserción de certificados o para restringir el acceso con una variedad de restricciones de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a8b96-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="a8b96-127">En muchos casos, los dispositivos pueden tener restricciones de conectividad, como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o al micrófono.</span><span class="sxs-lookup"><span data-stu-id="a8b96-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="a8b96-128">Si tienes alguno de estos intereses, te recomendamos que leas la [Página de restricciones de dispositivos comunes](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="a8b96-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="a8b96-129">Puedes usar otras restricciones de dispositivos más complejas.</span><span class="sxs-lookup"><span data-stu-id="a8b96-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="a8b96-130">Como:</span><span class="sxs-lookup"><span data-stu-id="a8b96-130">Such as:</span></span>

- <span data-ttu-id="a8b96-131">Limitar las páginas que se pueden ver en la aplicación configuración con [SettingsPageVisibility](settings-uri-list.md), lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su Wi-Fi conexión.</span><span class="sxs-lookup"><span data-stu-id="a8b96-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="a8b96-132">Use el [modo de pantalla completa](hololens-kiosk.md) para limitar la interfaz de usuario que se presenta a los usuarios en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a8b96-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="a8b96-133">Puede configurar quioscos para que muestren una sola aplicación o varias aplicaciones con una página de inicio personalizada.</span><span class="sxs-lookup"><span data-stu-id="a8b96-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="a8b96-134">Los quioscos también pueden presentar distintas experiencias a diferentes usuarios.</span><span class="sxs-lookup"><span data-stu-id="a8b96-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="a8b96-135">[Control de aplicaciones de Windows (WDAC)](windows-defender-application-control-wdac.md) para evitar que determinadas aplicaciones o procesos se inicien por completo.</span><span class="sxs-lookup"><span data-stu-id="a8b96-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="a8b96-136">Si desea obtener más información sobre métodos de administración de dispositivos o restricciones de dispositivos, siga el siguiente paso y lea nuestra descripción general de la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a8b96-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="a8b96-137">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a8b96-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a8b96-138">Leer los CSP y la descripción general de administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a8b96-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)