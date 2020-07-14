---
title: Inalámbrico y Wi-Fi
description: Inalámbrico y Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, inalámbrico, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865771"
---
# <span data-ttu-id="dd03c-104">Inalámbrico y Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="dd03c-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="dd03c-105">La conectividad de LAN inalámbrica con HoloLens 2 es compatible con una gran variedad de los últimos estándares de seguridad Wi-Fi, como:</span><span class="sxs-lookup"><span data-stu-id="dd03c-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="dd03c-106">WPA2 (acceso protegido Wi-Fi 2)</span><span class="sxs-lookup"><span data-stu-id="dd03c-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="dd03c-107">TEAP (túnel, protocolo de autenticación extensible)</span><span class="sxs-lookup"><span data-stu-id="dd03c-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="dd03c-108">DEBE (cifrado inalámbrico oportunista)</span><span class="sxs-lookup"><span data-stu-id="dd03c-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="dd03c-109">TEAP, la próxima generación de la autenticación de red empresarial, ofrece la posibilidad de concatenar varias credenciales de forma segura en una sola transacción.</span><span class="sxs-lookup"><span data-stu-id="dd03c-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="dd03c-110">Esto permite a los administradores exigir una actitud de seguridad mayor: una que necesita identidades válidas para el equipo y el usuario durante la misma transacción de autenticación.</span><span class="sxs-lookup"><span data-stu-id="dd03c-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="dd03c-111">HoloLens 2 tiene protocolos inalámbricos y Wi-Fi modernos que permiten a los clientes con la asistencia máxima.</span><span class="sxs-lookup"><span data-stu-id="dd03c-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="dd03c-112">La radio de HoloLens 2 es una solución de Qualcomm WCN3990 que ofrece una experiencia de radio Premium.</span><span class="sxs-lookup"><span data-stu-id="dd03c-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="dd03c-113">La Wi-Fi es compatible con la 802,11 AC/n.</span><span class="sxs-lookup"><span data-stu-id="dd03c-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="dd03c-114">El rango de frecuencias no es configurable por el usuario y depende del país de uso.</span><span class="sxs-lookup"><span data-stu-id="dd03c-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="dd03c-115">En los Estados Unidos, Wi-Fi usa canales de 2,4 GHz (1-11) y de 5 GHz (36-64, 100-165).</span><span class="sxs-lookup"><span data-stu-id="dd03c-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="dd03c-116">El usuario o el dispositivo no pueden hacer las listas de permitidos y denegación para frecuencias específicas.</span><span class="sxs-lookup"><span data-stu-id="dd03c-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="dd03c-117">El núcleo SIC de 5.0 tiene una antena dedicada de 2.4 GHz para Bluetooth que no se comparte con Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="dd03c-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="dd03c-118">La pila de software de HoloLens 2 es compatible con varios protocolos y perfiles, como HID, HOGP, A2DP y GATT.</span><span class="sxs-lookup"><span data-stu-id="dd03c-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="dd03c-119">Los administradores de TI pueden:</span><span class="sxs-lookup"><span data-stu-id="dd03c-119">IT admins can:</span></span> 
  * <span data-ttu-id="dd03c-120">Permitir o restringir el [Acceso a Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span><span class="sxs-lookup"><span data-stu-id="dd03c-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="dd03c-121">Establezca [nombres de dispositivo Bluetooth locales](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span><span class="sxs-lookup"><span data-stu-id="dd03c-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="dd03c-122">Permita que los[dispositivos sean detectables](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span><span class="sxs-lookup"><span data-stu-id="dd03c-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="dd03c-123">Permitir o denegar [conexiones Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span><span class="sxs-lookup"><span data-stu-id="dd03c-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="dd03c-124">Permitir o denegar el [de conexión a Wi-Fi fuera de las redes instaladas en servidor MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span><span class="sxs-lookup"><span data-stu-id="dd03c-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
