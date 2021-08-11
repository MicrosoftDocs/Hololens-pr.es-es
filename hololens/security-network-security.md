---
title: Seguridad de las redes
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
ms.openlocfilehash: c5ac42ee272becfd404a1f00931fa05237e31993288fee16d79d73f79aade646
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665393"
---
# <a name="network-security"></a>Seguridad de las redes

## <a name="network-protocols"></a>Protocolos de red

El antiguo NetBIOS (sistema básico de entrada y salida de red) era ampliamente usado en escenarios de LAN, generalmente para ofrecer resolución de nombres para un equipo y carpetas compartidas. Sin embargo, con el tiempo, se demostró que NetBIOS era susceptible de sufrir múltiples ataques y su relevancia se redujo para favorecer a otros protocolos más seguros. Para eliminar este problema de vulnerabilidad, HoloLens 2 ha eliminado el código relacionado con NetBIOS del sistema operativo.

Los protocolos de seguridad de la capa de transporte (TLS) están evolucionando constantemente. Para estar al día con las distintas vulnerabilidades de seguridad que se han descubierto en esta área, el sector informático ha cambiado a versiones más nuevas y efectivas. Dado que el tiempo necesario para que todas las implementaciones de servidor adopten las nuevas versiones del protocolo TLS, se puede implementar un mecanismo de reserva que permita que el cliente y los servidores con distintas versiones de protocolo predeterminadas aún puedan comunicarse durante el período de transición.

## <a name="secure-connectivity"></a>Conectividad segura 

Firewall de Windows Defender ofrece funcionalidad crítica para garantizar la conectividad de los dispositivos. Con HoloLens 2, el firewall siempre está habilitado y no hay ninguna manera de deshabilitarlo mediante programación ni a través de la interfaz de usuario.

El acceso remoto y la privacidad de la conexión para clientes móviles pueden garantizarse a través de la [plataforma de complementos VPN de UWP](/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Los proveedores de VPN de terceros pueden crear sus propios complementos mediante las API de WinRT, que se ejecutarán en el espacio aislado de AppContainer, lo que elimina la complejidad y los problemas que suelen asociarse con la escritura de controladores de nivel de sistema.
