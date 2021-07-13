---
title: Conexión a redes de telefonía móvil y 5G
description: Conexión a redes de telefonía móvil desde los dispositivos HoloLens de realidad mixta.
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
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397496"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="caceb-103">Conexión a redes de telefonía móvil y 5G</span><span class="sxs-lookup"><span data-stu-id="caceb-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="caceb-104">HoloLens 2 admite dos métodos para conectarse a las redes de telefonía móvil y 5G:</span><span class="sxs-lookup"><span data-stu-id="caceb-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="caceb-105">Una red WiFi ad hoc proporcionada por el dispositivo de telefonía móvil, más frecuentemente conocida como "punto de acceso"</span><span class="sxs-lookup"><span data-stu-id="caceb-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="caceb-106">Compatibilidad limitada con dispositivos USB-C con tethering</span><span class="sxs-lookup"><span data-stu-id="caceb-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="caceb-107">Punto de acceso (WiFi)</span><span class="sxs-lookup"><span data-stu-id="caceb-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="caceb-108">La mayoría de las necesidades de conectividad de la red de telefonía móvil pueden satisfacerse con un punto de acceso.</span><span class="sxs-lookup"><span data-stu-id="caceb-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="caceb-109">La red WiFi de HoloLens 2 es compatible con 802.11ac, que puede proporcionar el ancho de banda y los requisitos de latencia necesarios para la mayoría de los casos de uso.</span><span class="sxs-lookup"><span data-stu-id="caceb-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="caceb-110">Además, la red WiFi no necesita cable y ofrece compatibilidad con la mayoría de los dispositivos de red de telefonía móvil.</span><span class="sxs-lookup"><span data-stu-id="caceb-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="caceb-111">Conexión a un punto de acceso</span><span class="sxs-lookup"><span data-stu-id="caceb-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="caceb-112">Consulte el manual de su dispositivo para saber cómo habilitar el modo de punto de acceso.</span><span class="sxs-lookup"><span data-stu-id="caceb-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="caceb-113">Habilite el modo de punto de acceso, proporcione un nombre para la red y una contraseña conocida.</span><span class="sxs-lookup"><span data-stu-id="caceb-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="caceb-114">En la configuración de red de HoloLens 2, localice la red WiFi que creó en el paso 2 y únase a ella.</span><span class="sxs-lookup"><span data-stu-id="caceb-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="caceb-115">Tethering USB-C</span><span class="sxs-lookup"><span data-stu-id="caceb-115">USB-C Tethering</span></span>

<span data-ttu-id="caceb-116">El tethering USB-C puede ofrecer una latencia inferior para las cargas de trabajo avanzadas que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="caceb-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="caceb-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), por ejemplo, puede beneficiarse del tethering.</span><span class="sxs-lookup"><span data-stu-id="caceb-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="caceb-118">Tenga en cuenta que el tethering requiere un cable entre el dispositivo de red de telefonía móvil y HoloLens, y que solo es compatible con un número limitado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="caceb-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="caceb-119">Compatibilidad con USB-C</span><span class="sxs-lookup"><span data-stu-id="caceb-119">USB-C compatibility</span></span>

<span data-ttu-id="caceb-120">Un número limitado de dispositivos que se presentan a sí mismos como adaptadores de ethernet pueden usarse con Windows Holographic versión 2004 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="caceb-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="caceb-121">Los dispositivos que no se presentan a sí mismos como adaptadores de ethernet deben admitir el controlador genérico de Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-).</span><span class="sxs-lookup"><span data-stu-id="caceb-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="caceb-122">Sin embargo, solo un número limitado de esos dispositivos son compatibles con HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="caceb-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="caceb-123">Consulte al fabricante del dispositivo para obtener más información sobre si es compatible con el controlador genérico de Microsoft RNDIS.</span><span class="sxs-lookup"><span data-stu-id="caceb-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="caceb-124">No se admiten dispositivos que no sean compatibles con RNDIS o que necesiten instalar un controlador o una aplicación.</span><span class="sxs-lookup"><span data-stu-id="caceb-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="caceb-125">Aunque Microsoft no mantiene ninguna lista de dispositivos compatibles, puede consultar una [entrada](https://aka.ms/HLCommunityCell) en la comunidad sobre el tema.</span><span class="sxs-lookup"><span data-stu-id="caceb-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="caceb-126">Conexión a un dispositivo con tethering</span><span class="sxs-lookup"><span data-stu-id="caceb-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="caceb-127">Consulte el manual de su dispositivo para saber cómo habilitar el uso compartido de datos por USB.</span><span class="sxs-lookup"><span data-stu-id="caceb-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="caceb-128">Esta configuración se suele conocer como "tethering USB", "uso compartido de datos" o "módem USB".</span><span class="sxs-lookup"><span data-stu-id="caceb-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="caceb-129">Habilite el uso compartido de datos por USB.</span><span class="sxs-lookup"><span data-stu-id="caceb-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="caceb-130">Conecte el dispositivo al puerto USB-C de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="caceb-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="caceb-131">En la configuración de red de HoloLens 2, el dispositivo aparecerá automáticamente como una conexión a Ethernet.</span><span class="sxs-lookup"><span data-stu-id="caceb-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
