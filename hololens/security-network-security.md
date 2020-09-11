---
title: Seguridad de red
description: seguridad de red
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, red, seguridad de red
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009428"
---
# <span data-ttu-id="b387e-104">Seguridad de red</span><span class="sxs-lookup"><span data-stu-id="b387e-104">Network security</span></span>

## <span data-ttu-id="b387e-105">Protocolos de red</span><span class="sxs-lookup"><span data-stu-id="b387e-105">Network protocols</span></span>

<span data-ttu-id="b387e-106">El antiguo NetBIOS (Sistema básico de entrada y salida de red) era ampliamente usado en escenarios de LAN, generalmente para ofrecer resolución de nombres para un equipo y carpetas compartidas.</span><span class="sxs-lookup"><span data-stu-id="b387e-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="b387e-107">Sin embargo, con el tiempo, se demostró que NetBIOS es susceptible de sufrir múltiples ataques y su relevancia se ha reducido para favorecer a otros protocolos más seguros.</span><span class="sxs-lookup"><span data-stu-id="b387e-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="b387e-108">Para quitar este problema de vulnerabilidad, HoloLens 2 ha eliminado el código relacionado con NetBIOS del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b387e-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="b387e-109">Los protocolos de seguridad de la capa de transporte (TLS) están evolucionando constantemente.</span><span class="sxs-lookup"><span data-stu-id="b387e-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="b387e-110">Para estar al día con las distintas vulneraciones de seguridad que se han descubierto en esta área, el sector informático se ha graduado a versiones más nuevas y efectivas.</span><span class="sxs-lookup"><span data-stu-id="b387e-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="b387e-111">Dado que el tiempo necesario para que todas las implementaciones de servidor adopten las nuevas versiones del protocolo TLS, se puede implementar un mecanismo de reserva que permite que el cliente y los servidores con distintas versiones de protocolo predeterminadas aún puedan comunicarse durante el período de transición.</span><span class="sxs-lookup"><span data-stu-id="b387e-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <span data-ttu-id="b387e-112">Conectividad segura</span><span class="sxs-lookup"><span data-stu-id="b387e-112">Secure connectivity</span></span> 

<span data-ttu-id="b387e-113">El Firewall de Windows Defender ofrece funciones fundamentales para asegurar la conectividad de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b387e-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="b387e-114">Con HoloLens 2, el firewall siempre está habilitado y no hay ninguna manera de deshabilitarlo mediante programación o por medio de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="b387e-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="b387e-115">El acceso remoto y la privacidad de la conexión para clientes móviles pueden asegurarse a través de la [plataforma de complemento de VPN para UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span><span class="sxs-lookup"><span data-stu-id="b387e-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="b387e-116">Los proveedores de VPN de terceros pueden crear sus propios complementos mediante las API de WinRT, que se ejecutarán en el espacio aislado de AppContainer, lo que elimina la complejidad y los problemas que suelen asociarse con la escritura de controladores de nivel de sistema.</span><span class="sxs-lookup"><span data-stu-id="b387e-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
