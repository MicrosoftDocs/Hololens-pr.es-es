---
title: Conectar a redes de telefonía móvil y 5G
description: Conectarse a redes de telefonía móvil desde sus dispositivos de realidad mixta de HoloLens.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385651"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="21f2b-103">Conectar a redes de telefonía móvil y 5G</span><span class="sxs-lookup"><span data-stu-id="21f2b-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="21f2b-104">HoloLens 2 admite dos métodos para conectarse a las redes de telefonía móvil y 5G:</span><span class="sxs-lookup"><span data-stu-id="21f2b-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="21f2b-105">Una red WiFi ad hoc proporcionada por el dispositivo de telefonía móvil, más frecuentemente conocida como "Punto de acceso"</span><span class="sxs-lookup"><span data-stu-id="21f2b-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="21f2b-106">Compatibilidad limitada con dispositivos USB-C anclados a la red</span><span class="sxs-lookup"><span data-stu-id="21f2b-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="21f2b-107">Punto de acceso (WiFi)</span><span class="sxs-lookup"><span data-stu-id="21f2b-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="21f2b-108">La mayoría de las necesidades de conectividad de la red de telefonía móvil pueden satisfacerse con un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="21f2b-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="21f2b-109">HoloLens 2 WiFi es compatible con 802.11ac, el cual proporciona el ancho de banda y los requisitos de latencia necesarios para la mayoría de los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="21f2b-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="21f2b-110">Además, el WiFi no necesita cable y ofrece compatibilidad con la mayoría de los dispositivos de red de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="21f2b-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="21f2b-111">Conectar a un punto de acceso</span><span class="sxs-lookup"><span data-stu-id="21f2b-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="21f2b-112">Consulte el manual de su dispositivo para saber cómo habilitar el modo de punto de acceso.</span><span class="sxs-lookup"><span data-stu-id="21f2b-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="21f2b-113">Habilitar el modo de punto de acceso, proporcionar un nombre para la red y una contraseña conocida.</span><span class="sxs-lookup"><span data-stu-id="21f2b-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="21f2b-114">En la configuración de red de HoloLens 2, localice la red WiFi que creó en el paso 2 y únase a ella.</span><span class="sxs-lookup"><span data-stu-id="21f2b-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="21f2b-115">Anclado de red USB-C</span><span class="sxs-lookup"><span data-stu-id="21f2b-115">USB-C Tethering</span></span>

<span data-ttu-id="21f2b-116">El anclado de red con USB-C proporciona una latencia inferior para las cargas de trabajo avanzadas que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="21f2b-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="21f2b-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), por ejemplo, puede beneficiarse del anclado de red.</span><span class="sxs-lookup"><span data-stu-id="21f2b-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="21f2b-118">Tenga en cuenta que el anclado de red requiere un cable entre el dispositivo de red de telefonía móvil y HoloLens, y que solo es compatible con un número limitado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="21f2b-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="21f2b-119">Compatibilidad con USB-C</span><span class="sxs-lookup"><span data-stu-id="21f2b-119">USB-C compatibility</span></span>

<span data-ttu-id="21f2b-120">Los dispositivos que se presentan por sí solo como adaptadores de ethernet pueden usarse con Windows Holographic versión 2004 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="21f2b-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="21f2b-121">Los dispositivos que no se presenten por sí solos como adaptadores de ethernet deben ser compatibles con el controlador genérico de Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-).</span><span class="sxs-lookup"><span data-stu-id="21f2b-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="21f2b-122">Consulte al fabricante del dispositivo para obtener más información sobre si es compatible con el controlador genérico de Microsoft RNDIS.</span><span class="sxs-lookup"><span data-stu-id="21f2b-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="21f2b-123">No se admiten dispositivos que no sean compatibles con RNDIS o que necesiten instalar un controlador o una aplicación.</span><span class="sxs-lookup"><span data-stu-id="21f2b-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="21f2b-124">Aunque Microsoft no mantiene ninguna lista de dispositivos compatibles, puede encontrar una discusión de la comunidad sobre el tema [aquí](https://aka.ms/HLCommunityCell).</span><span class="sxs-lookup"><span data-stu-id="21f2b-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="21f2b-125">Conectarse a un dispositivo anclado a la red</span><span class="sxs-lookup"><span data-stu-id="21f2b-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="21f2b-126">Consulte el manual de su dispositivo para saber cómo habilitar el uso compartido de datos por USB.</span><span class="sxs-lookup"><span data-stu-id="21f2b-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="21f2b-127">Esta configuración se conoce a menudo como "anclado de red USB", "uso compartido de datos" o "módem USB".</span><span class="sxs-lookup"><span data-stu-id="21f2b-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="21f2b-128">Habilite el uso compartido de datos por USB.</span><span class="sxs-lookup"><span data-stu-id="21f2b-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="21f2b-129">Conecte el dispositivo al puerto USB-C de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21f2b-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="21f2b-130">En la configuración de red de HoloLens 2, el dispositivo aparecerá automáticamente como una conexión a Ethernet.</span><span class="sxs-lookup"><span data-stu-id="21f2b-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
