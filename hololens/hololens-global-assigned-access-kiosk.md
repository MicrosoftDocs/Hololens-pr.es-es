---
title: Acceso asignado global
description: Guía para usar OMA-URI para quioscos de acceso asignado global
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1a0a3eb8ef3d21b34e13711bcc890af57e5ae2c2
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902305"
---
# <span data-ttu-id="182d9-104">Acceso asignado global: quiosco</span><span class="sxs-lookup"><span data-stu-id="182d9-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="182d9-105">Esta característica configura el dispositivo Hololens 2 para varias aplicaciones en modo de pantalla completa que es aplicable a nivel del sistema, no tiene afinidad con ninguna identidad del sistema y se aplica a cualquier usuario que inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="182d9-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="182d9-106">Actualmente, esta característica solo está disponible en las compilaciones de Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="182d9-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="182d9-107">Si desea probar esta característica antes de que esté disponible de forma generalizada en las versiones de HoloLens, obtenga más información sobre las compilaciones de [Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="182d9-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="182d9-108">¿Cómo usar esto en Intune?</span><span class="sxs-lookup"><span data-stu-id="182d9-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="182d9-109">Tenga en cuenta las áreas marcadas con "<!-".</span><span class="sxs-lookup"><span data-stu-id="182d9-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="182d9-110">Estas áreas requieren que realice modificaciones en función de sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="182d9-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="182d9-111">Cree un perfil de configuración de dispositivo OMA URI personalizado como se indica a continuación y aplíquelo al grupo de dispositivos HoloLens: ![OMA-URI de acceso asignado global en Intune</span><span class="sxs-lookup"><span data-stu-id="182d9-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="182d9-112">Para obtener un valor, actualice y pegue el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="182d9-112">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="182d9-113">¿Cómo usar esto en el diseñador de configuraciones de Windows?</span><span class="sxs-lookup"><span data-stu-id="182d9-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="182d9-114">Actualice y guarde el blob XML indicado anteriormente como archivo XML.</span><span class="sxs-lookup"><span data-stu-id="182d9-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="182d9-115">Siga los pasos que se indican en [Usar un paquete de aprovisionamiento para configurar un quiosco de aplicación única o de varias aplicaciones](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), en concreto en la sección "Paquete</span><span class="sxs-lookup"><span data-stu-id="182d9-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="182d9-116">de aprovisionamiento, paso 2: agregue el archivo XML de configuración de quiosco a un paquete de aprovisionamiento" y use el archivo XML que guardó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="182d9-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="182d9-117">¿Puedo crear una configuración en la que global se aplique a todos los usuarios excepto a 1 cuenta de AAD o grupo de AAD?</span><span class="sxs-lookup"><span data-stu-id="182d9-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="182d9-118">Sí, consulte a continuación el blob XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="182d9-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="182d9-119">El perfil de acceso asignado global se aplica en Hololens cuando no se encuentra uno específico para el usuario que ha iniciado sesión, por lo que es la configuración predeterminada del modo de pantalla completa para el usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="182d9-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="182d9-120">Este es un ejemplo de blob XML que se usará:</span><span class="sxs-lookup"><span data-stu-id="182d9-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="182d9-121">Tenga en cuenta las áreas resaltadas con <!-. Estas áreas requieren que realice modificaciones en función de sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="182d9-121">Please be aware of the highlighted areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="182d9-122">Exclusión de DeviceOwners de un perfil de acceso asignado global</span><span class="sxs-lookup"><span data-stu-id="182d9-122">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="182d9-123">Esta característica permite que los usuarios considerados como "[Propietario del dispositivo](security-adminless-os.md)" estén excluidos del acceso asignado global.</span><span class="sxs-lookup"><span data-stu-id="182d9-123">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="182d9-124">Para aprovechar esta característica, en el blob XML para la configuración de un quiosco de varias aplicaciones, asegúrese de que se agregan las líneas resaltadas:</span><span class="sxs-lookup"><span data-stu-id="182d9-124">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
