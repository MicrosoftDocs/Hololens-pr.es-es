---
title: Escenarios habituales de implementación de infraestructura
description: Algunos escenarios de implementación comunes basados en diferentes infraestructuras comunes
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: a7d847e2d2d335f2e2388535a5cf9d5246bb330b
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253077"
---
# Introducción a los escenarios de implementación de infraestructura comunes

Esta información proporciona una descripción general de la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar dispositivos de Microsoft HoloLens 2 dentro de la empresa. A menudo, la forma en que se administran los dispositivos y el acceso a los recursos de la organización vienen determinadas en gran medida por factores ya instalados. En función de la infraestructura existente, le invitamos a revisar el estilo de administración de dispositivos común en los siguientes escenarios, y probar nuestras guías para implementar en el escenario que se ajuste a sus necesidades.

## Escenarios

El diagrama siguiente representa tres escenarios típicos para las implementaciones de HoloLens 2.
![Diagrama de escenarios](images/scenarios.jpg)

### Escenario A: implementar en dispositivos de conexión en la nube

HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa. No se puede acceder a los recursos corporativos o pueden estar limitados a través de VPN. Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.
 * Configuraciones básicas comunes
   * Las redes Wi-Fi suelen estar totalmente abiertas a Internet y a los servicios en la nube.
   * Unirse a Azure AD con inscripción automática de MDM: MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Compatible con uno o varios usuarios por dispositivo
   * Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierto a la única.
   * Una o más aplicaciones se implementan a través de MDM

* Desafíos comunes
   * Determinando las configuraciones de MDM que se aplicarán a HoloLens 2 en función de los requisitos del escenario.

Para obtener una guía de implementación similar a la del escenario a, revise nuestra guía de [HoloLens 2 conectada en la nube con asistencia remota](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guía de implementación: HoloLens 2 conectado en la nube con asistencia remota](hololens2-cloud-connected-overview.md)

### Escenario B: implementar dentro de la red de su organización

HoloLens 2 se ha implementado para usarlo principalmente en la red corporativa con acceso a recursos internos de la empresa. Es posible que los servicios de Internet y de nube estén limitados. Esta implementación es una implementación típica de la mayoría de equipos con Windows 10.

 * Configuraciones básicas comunes
   * Wi-Fi red es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o a los servicios en la nube.
   * Unirse a Azure AD con inscripción automática de MDM
   * MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Compatible con uno o varios usuarios por dispositivo
   * Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierto a la única.
   * Una o más aplicaciones se implementan a través de MDM

 * Desafíos comunes
   * HoloLens 2 no admite la Unión de AD local o SCCM. Solo unirse a Azure AD con MDM. Muchas empresas en la actualidad implementan equipos con Windows 10 en este escenario como locales de los dispositivos Unidos a AD, administrados por System Center Configuration Manager (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos internos de Windows 10 a través de soluciones MDM basadas en la nube.
   * Como HoloLens 2 es un dispositivo en la nube, depende en gran medida de los servicios conectados a la nube y de Internet para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, etc. Al conectarse a una red corporativa, es probable que las reglas de proxy o firewall se ajusten para habilitar el acceso a HoloLens 2 y las aplicaciones que se ejecutan en él.
   * La conectividad corporativa Wi-Fi generalmente requiere certificados para autenticar el dispositivo o el usuario en la red. La configuración o la infraestructura requerida para implementar certificados en dispositivos con Windows 10 a través de MDM puede ser difícil de configurar.

### Escenario C: implementar en un entorno seguro sin conexión

HoloLens 2 se ha implementado para usarlo principalmente sin conexión y sin acceso a la red ni a Internet. Esta es una implementación típica para ubicaciones de alta seguridad o confidenciales.
 * Configuraciones básicas comunes
   * La conectividad de Wi-Fi está deshabilitada. Es posible habilitar Ethernet por USB para conectividad de LAN si es necesario.
   * No administrado.
   * Cuenta de usuario local para el inicio de sesión del dispositivo.
     * HoloLens 2 solo admite una cuenta local.
   * Se aplican diversos niveles de configuración de bloqueo de dispositivo mediante paquetes de aprovisionamiento basados en casos de uso específicos. Por lo general, estas configuraciones están muy restringidas a causa de requisitos de entorno seguro.
   * Una o más aplicaciones se implementan mediante el paquete de aprovisionamiento

 * Desafíos comunes
   * Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento
   * Los servicios en la nube no se pueden aprovechar y, por lo tanto, limitan las capacidades de HoloLens 2.
   * Mayor overhead administrativo ya que estos dispositivos se deben configurar, configurar y actualizar de forma manual.

Para obtener una guía de implementación similar a este escenario, revise nuestra [Guía de implementación segura sin conexión](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guía de implementación: HoloLens con conexión segura 2](hololens-common-scenarios-offline-secure.md)
