---
title: Acceso asignado global
description: Guía para usar OMA-URI para quioscos de acceso asignado global
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253207"
---
# <span data-ttu-id="bf1bd-104">Acceso asignado global: quiosco</span><span class="sxs-lookup"><span data-stu-id="bf1bd-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="bf1bd-105">Esta característica configura el dispositivo HoloLens 2 para varias aplicaciones en modo de pantalla completa, que es aplicable a nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="bf1bd-106">Actualmente, esta característica solo está disponible en las compilaciones de Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="bf1bd-107">Si deseas probar esta característica antes de que esté disponible de forma generalizada en las versiones de HoloLens, infórmate sobre las compilaciones de [Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="bf1bd-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <span data-ttu-id="bf1bd-108">¿Cómo se usa el acceso asignado global en Intune?</span><span class="sxs-lookup"><span data-stu-id="bf1bd-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="bf1bd-109">Tenga en cuenta las áreas marcadas con "<!-".</span><span class="sxs-lookup"><span data-stu-id="bf1bd-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="bf1bd-110">Estas áreas requieren que realice modificaciones en función de sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="bf1bd-111">Cree un perfil de configuración de dispositivo OMA URI personalizado como se indica a continuación y aplíquelo al grupo de dispositivos HoloLens:</span><span class="sxs-lookup"><span data-stu-id="bf1bd-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="bf1bd-112">Valor URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="bf1bd-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > ![Acceso asignado global OMA-URI en Intune](images/global-assigned-access-omauri.png)

2. <span data-ttu-id="bf1bd-114">Para obtener un valor, actualice y pegue el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="bf1bd-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="bf1bd-115">¿Cómo se usa el Acceso asignado global en el Diseñador de configuración de Windows?</span><span class="sxs-lookup"><span data-stu-id="bf1bd-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="bf1bd-116">Actualice y guarde el blob XML indicado anteriormente como archivo XML.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="bf1bd-117">Siga los pasos que se indican en [Usar un paquete de aprovisionamiento para configurar un quiosco de aplicación única o de varias aplicaciones](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), en concreto en la sección "Paquete</span><span class="sxs-lookup"><span data-stu-id="bf1bd-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="bf1bd-118">de aprovisionamiento, paso 2: agregue el archivo XML de configuración de quiosco a un paquete de aprovisionamiento" y use el archivo XML que guardó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <span data-ttu-id="bf1bd-119">¿Puedo crear una configuración en la que "global" se aplique a todos los usuarios y una configuración aparte que se aplique a 1 cuenta de Azure AD o grupo de Azure AD?</span><span class="sxs-lookup"><span data-stu-id="bf1bd-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="bf1bd-120">Sí, consulte el ejemplo de BLOB XML a continuación.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="bf1bd-121">El perfil de acceso asignado global se aplica en Hololens cuando no se encuentra uno específico para el usuario que ha iniciado sesión, por lo que es la configuración predeterminada del modo de pantalla completa para el usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="bf1bd-122">Este es un ejemplo de blob XML que se usará:</span><span class="sxs-lookup"><span data-stu-id="bf1bd-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="bf1bd-123">Tenga en cuenta las áreas resaltadas marcadas con `<!-`.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="bf1bd-124">Estas áreas requieren que realice modificaciones en función de sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="bf1bd-125">Exclusión de DeviceOwners de un perfil de acceso asignado global</span><span class="sxs-lookup"><span data-stu-id="bf1bd-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="bf1bd-126">Esta característica permite que los usuarios considerados como "[Propietario del dispositivo](security-adminless-os.md)" estén excluidos del acceso asignado global.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="bf1bd-127">Para aprovechar esta característica, en el blob XML para la configuración de un quiosco de varias aplicaciones, asegúrese de que se agregan las líneas resaltadas:</span><span class="sxs-lookup"><span data-stu-id="bf1bd-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <span data-ttu-id="bf1bd-128">Ejemplos adicionales de Acceso global asignado</span><span class="sxs-lookup"><span data-stu-id="bf1bd-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="bf1bd-129">Este es el ejemplo de un quiosco de Acceso global asignado en el que, cuando un usuario inicie sesión, tendrá un quiosco de varias aplicaciones con la aplicación Configuración, el Centro de opiniones y Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="bf1bd-130">Este es el ejemplo de un quiosco de Acceso global asignado que excluye al propietario del dispositivo. Cuando cualquier otro usuario de Azure AD inicie sesión, tendrá un quiosco de varias aplicaciones con la aplicación Configuración, el Centro de opiniones y Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="bf1bd-131">Este quiosco también incluye la configuración de un quiosco secundario para una Cuenta de visitante, a la cual se puede acceder desde la pantalla de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="bf1bd-132">Cuando un usuario inicia sesión en la Cuenta de visitante, tendrá un quiosco de varias aplicaciones que solo tendrá la aplicación del Centro de opiniones.</span><span class="sxs-lookup"><span data-stu-id="bf1bd-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
