---
title: Escenarios habituales de implementación de infraestructura
description: Obtenga información sobre algunos de los escenarios de implementación más comunes basados en distintas implementaciones de infraestructura para realidad mixta.
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283631"
---
# Introducción a los escenarios comunes de implementación de infraestructura

Esta siguiente información proporciona una introducción a la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar dispositivos De Microsoft HoloLens 2 en la empresa. A menudo, la forma en que administras los dispositivos y cómo acceder a los recursos de la organización se determina en gran medida por factores ya establecidos. En función de la infraestructura existente, te invitamos a revisar el estilo común de administración de dispositivos en los siguientes escenarios y probar nuestras guías para la implementación en el escenario que se asememe a tus necesidades.

## Escenarios

El siguiente diagrama representa tres escenarios típicos para implementaciones de HoloLens 2.
![Diagrama de escenarios](images/scenarios.jpg)

### Escenario A: Implementar en dispositivos de conexión en la nube

HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa. No se tiene acceso a los recursos corporativos o pueden estar limitados a través de VPN. Esta implementación es similar a los dispositivos móviles administrados de una empresa.
 * Configuraciones comunes básicas
   * Wi-Fi las redes están completamente abiertas a Internet y a los servicios en la nube.
   * Unión a Azure AD con inscripción automática de administración de dispositivos móviles (MDM): MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o más aplicaciones se implementan a través de MDM

* Desafíos comunes
   * Determinar qué configuraciones de MDM se deben aplicar a HoloLens 2 en función de los requisitos del escenario.

Para obtener una guía de implementación similar al escenario A, revise nuestra guía de [HoloLens 2](hololens2-cloud-connected-overview.md)conectado a la nube con asistencia remota.

> [!div class="nextstepaction"]
> [Guía de implementación: HoloLens 2 conectado en la nube con asistencia remota](hololens2-cloud-connected-overview.md)

### Escenario B: Implementar dentro de la red de la organización

HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos. Es posible que los servicios de Internet y la nube sean limitados. Esta implementación es una implementación típica para la mayoría de los equipos con Windows 10.

 * Configuraciones comunes básicas
   * Wi-Fi red es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube.
   * Unión a Azure AD con inscripción automática de MDM
   * MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo
   * Los distintos niveles de configuración de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o más aplicaciones se implementan a través de MDM

 * Desafíos comunes
   * HoloLens 2 no admite la unión local a AD o SCCM. Solo unirse a Azure AD con MDM. Actualmente, muchas empresas siguen implementando equipos con Windows 10 en este escenario como dispositivos unidos a AD local, administrados por System Center Configuration Manager (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.
   * Como HoloLens 2 es un primer dispositivo en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, y así sucesivamente. Al conectarse a una red corporativa, es muy probable que las reglas de proxy o firewall deban ajustarse para habilitar el acceso para HoloLens 2 y las aplicaciones que se ejecutan en ella.
   * La Wi-Fi corporativa suele requerir certificados para autenticar el dispositivo o el usuario en la red. La infraestructura o configuración necesaria para implementar certificados en dispositivos Windows 10 a través de MDM puede ser difícil de configurar.

### Escenario C: Implementar en un entorno sin conexión seguro

HoloLens 2 se implementa para su uso principalmente sin conexión sin acceso a la red o a Internet. Se trata de una implementación típica para ubicaciones extremadamente seguras o confidenciales.
 * Configuraciones comunes básicas
   * Wi-Fi conectividad está deshabilitada. Ethernet a través de USB puede estar habilitado para la conectividad LAN si es necesario.
   * No administrado.
   * Cuenta de usuario local para el inicio de sesión del dispositivo.
     * HoloLens 2 solo admite una cuenta local.
   * Los distintos niveles de configuración de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos. Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.
   * Una o más aplicaciones se implementan a través del paquete de aprovisionamiento

 * Desafíos comunes
   * Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento
   * Los servicios en la nube no se pueden usar, lo que limita las capacidades de HoloLens 2.
   * Mayor sobrecarga administrativa, ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.

Para obtener una guía de implementación similar a este escenario, consulte nuestra Guía de implementación segura [sin conexión.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Guía de implementación: HoloLens seguro sin conexión 2](hololens-common-scenarios-offline-secure.md)
