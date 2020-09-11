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
# Seguridad de red

## Protocolos de red

El antiguo NetBIOS (Sistema básico de entrada y salida de red) era ampliamente usado en escenarios de LAN, generalmente para ofrecer resolución de nombres para un equipo y carpetas compartidas. Sin embargo, con el tiempo, se demostró que NetBIOS es susceptible de sufrir múltiples ataques y su relevancia se ha reducido para favorecer a otros protocolos más seguros. Para quitar este problema de vulnerabilidad, HoloLens 2 ha eliminado el código relacionado con NetBIOS del sistema operativo.

Los protocolos de seguridad de la capa de transporte (TLS) están evolucionando constantemente. Para estar al día con las distintas vulneraciones de seguridad que se han descubierto en esta área, el sector informático se ha graduado a versiones más nuevas y efectivas. Dado que el tiempo necesario para que todas las implementaciones de servidor adopten las nuevas versiones del protocolo TLS, se puede implementar un mecanismo de reserva que permite que el cliente y los servidores con distintas versiones de protocolo predeterminadas aún puedan comunicarse durante el período de transición.

## Conectividad segura 

El Firewall de Windows Defender ofrece funciones fundamentales para asegurar la conectividad de dispositivos. Con HoloLens 2, el firewall siempre está habilitado y no hay ninguna manera de deshabilitarlo mediante programación o por medio de la interfaz de usuario.

El acceso remoto y la privacidad de la conexión para clientes móviles pueden asegurarse a través de la [plataforma de complemento de VPN para UWP](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041). Los proveedores de VPN de terceros pueden crear sus propios complementos mediante las API de WinRT, que se ejecutarán en el espacio aislado de AppContainer, lo que elimina la complejidad y los problemas que suelen asociarse con la escritura de controladores de nivel de sistema.
