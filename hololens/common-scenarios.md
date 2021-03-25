---
title: Escenarios habituales de implementación de infraestructura
description: Obtenga información sobre algunos de los escenarios de implementación más comunes basados en distintas implementaciones de infraestructura para realidad mixta.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448498"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Introducción a escenarios comunes de implementación de infraestructura

Esta siguiente información proporciona una introducción a la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar dispositivos de Microsoft HoloLens 2 dentro de la empresa. A menudo, la forma de administrar los dispositivos y cómo obtener acceso a los recursos de la organización se determina en gran medida por factores que ya están en marcha. En función de la infraestructura existente, te invitamos a revisar el estilo de administración de dispositivos común en los siguientes escenarios y probar nuestras guías para implementar en el escenario que coincida con tus necesidades.

## <a name="scenarios"></a>Escenarios

El diagrama siguiente representa tres escenarios típicos para implementaciones de HoloLens 2.
![Diagrama de escenarios](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Escenario A: Implementar en dispositivos de conexión en la nube

HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa. Los recursos corporativos no tienen acceso o pueden estar limitados a través de VPN. Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.
 * Configuraciones comunes básicas
   * Wi-Fi las redes suelen estar totalmente abiertas a los servicios de Internet y la nube.
   * Unirse a Azure AD con la inscripción automática de Administración de dispositivos móviles (MDM): MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten usuarios únicos o múltiples por dispositivo
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o más aplicaciones se implementan a través de MDM

* Desafíos comunes
   * Determinación de qué configuraciones MDM se aplicarán a HoloLens 2 en función de los requisitos del escenario.

Para obtener una guía de implementación similar al escenario A revise nuestra guía para [HoloLens 2](hololens2-cloud-connected-overview.md)conectado a la nube con asistencia remota.

> [!div class="nextstepaction"]
> [Guía de implementación: HoloLens 2 conectado a la nube con asistencia remota](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Escenario B: Implementar dentro de la red de la organización

HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos. Es posible que los servicios de Internet y la nube sean limitados. Esta implementación es una implementación típica para la mayoría de los equipos con Windows 10.

 * Configuraciones comunes básicas
   * Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube.
   * Unirse a Azure AD con la inscripción automática de MDM
   * Mdm (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten usuarios únicos o múltiples por dispositivo
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o más aplicaciones se implementan a través de MDM

 * Desafíos comunes
   * HoloLens 2 no admite la unión a AD local o SCCM. Solo se une Azure AD con MDM. Muchas empresas aún implementan equipos con Windows 10 en este escenario como dispositivos locales unidos a AD, administrados por System Center Configuration Manager (SCCM) y pueden no tener la infraestructura implementada o configurada para administrar dispositivos Internos de Windows 10 a través de soluciones MDM basadas en la nube.
   * Como HoloLens 2 es un primer dispositivo en la nube, depende en gran medida de los servicios conectados a Internet y la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, entre otros. Al conectarse a una red corporativa, es muy probable que las reglas de proxy/firewall deban ajustarse para habilitar el acceso a HoloLens 2 y a las aplicaciones que se ejecutan en ella.
   * La Wi-Fi corporativa suele requerir certificados para autenticar el dispositivo o el usuario en la red. La infraestructura o la configuración necesarias para implementar certificados en dispositivos Windows 10 a través de MDM puede ser difícil de configurar.

> [!div class="nextstepaction"]
> [Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Escenario C: Implementar en un entorno sin conexión seguro

HoloLens 2 se implementa para su uso principalmente sin conexión sin red ni acceso a Internet. Se trata de una implementación típica para ubicaciones extremadamente seguras o confidenciales.
 * Configuraciones comunes básicas
   * Wi-Fi conectividad está deshabilitada. Ethernet a través de USB puede estar habilitado para la conectividad de LAN si es necesario.
   * No administrado.
   * Cuenta de usuario local para el inicio de sesión del dispositivo.
     * HoloLens 2 solo admite una cuenta local.
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos. Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.
   * Una o más aplicaciones se implementan a través del paquete de aprovisionamiento

 * Desafíos comunes
   * Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento
   * Los servicios en la nube no se pueden usar, lo que limita las capacidades de HoloLens 2.
   * Mayor sobrecarga administrativa ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.

Para obtener una guía de implementación similar a este escenario, consulte nuestra Guía de implementación segura [sin conexión.](hololens-common-scenarios-offline-secure.md)

> [!div class="nextstepaction"]
> [Guía de implementación: HoloLens seguro sin conexión 2](hololens-common-scenarios-offline-secure.md)
