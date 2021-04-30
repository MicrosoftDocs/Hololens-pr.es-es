---
title: Escenarios comunes de implementación de infraestructura
description: Obtenga información sobre algunos de los escenarios de implementación más comunes basados en diferentes implementaciones de infraestructura para la realidad mixta.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310158"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Introducción a los escenarios comunes de implementación de infraestructura

Esta información siguiente proporciona información general sobre la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar Microsoft HoloLens 2 dispositivos dentro de la empresa. A menudo, la forma en que administra los dispositivos y cómo acceder a los recursos de la organización viene determinada en gran medida por factores ya establecidos. En función de la infraestructura existente, le invitamos a revisar el estilo común de administración de dispositivos en los escenarios siguientes y probar nuestras guías para implementar en el escenario que se acote a sus necesidades.

## <a name="scenarios"></a>Escenarios

El diagrama siguiente representa tres escenarios típicos para HoloLens 2 implementaciones.
![Diagrama de escenarios](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>Escenario A: Implementación en dispositivos de conexión a la nube

HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa. No se accede a los recursos corporativos o se puede limitar a través de VPN. Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.
 * Configuraciones comunes básicas
   * Wi-Fi las redes están totalmente abiertas a Internet y a los servicios en la nube.
   * Azure AD unirse a mobile Administración de dispositivos (MDM) Auto Enrollment--MDM (Intune) Managed
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo.
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o varias aplicaciones se implementan a través de MDM

* Desafíos comunes
   * Determinar qué configuraciones de MDM se aplicarán al HoloLens 2 en función de los requisitos del escenario.

Para obtener una guía de implementación similar al escenario A revise nuestra guía de cloud [connected HoloLens 2 con Remote Assist](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guía de implementación: conexión a la nube HoloLens 2 con Remote Assist](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Escenario B: Implementación dentro de la red de la organización

HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos. Internet y los servicios en la nube pueden estar limitados. Esta implementación es una implementación típica para la mayoría Windows 10 equipos.

 * Configuraciones comunes básicas
   * Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube.
   * Azure AD unirse a la inscripción automática de MDM
   * MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Pantalla completa de aplicación única.
   * Una o varias aplicaciones se implementan a través de MDM

 * Desafíos comunes
   * HoloLens 2 no admite la unión a AD local o SCCM. Solo Azure AD unirse a MDM. Actualmente, muchas empresas aún implementan equipos Windows 10 en este escenario como dispositivos unidos a AD local, administrados por System Center Administrador de configuración (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.
   * Como HoloLens 2 es un dispositivo en primer lugar en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, y así sucesivamente. Al conectarse a una red corporativa, es probable que las reglas de proxy o firewall deban ajustarse para habilitar el acceso a HoloLens 2 y a las aplicaciones que se ejecutan en ella.
   * La Wi-Fi corporativa normalmente requiere certificados para autenticar el dispositivo o el usuario en la red. La infraestructura o la configuración necesarias para implementar certificados en Windows 10 dispositivos a través de MDM puede ser difícil de configurar.

> [!div class="nextstepaction"]
> [Guía de implementación: guía de HoloLens 2 corporativas con las guías de Dynamics 365](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>Escenario C: Implementación en un entorno sin conexión seguro

HoloLens 2 se implementa para su uso principalmente sin conexión sin acceso a la red o a Internet. Se trata de una implementación típica para ubicaciones altamente seguras o confidenciales.
 * Configuraciones comunes básicas
   * Wi-Fi conectividad está deshabilitada. Ethernet a través de USB puede habilitarse para la conectividad LAN si es necesario.
   * No administrado.
   * Cuenta de usuario local para el inicio de sesión del dispositivo.
     * HoloLens 2 solo admite una cuenta local.
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos. Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.
   * Una o varias aplicaciones se implementan a través del paquete de aprovisionamiento

 * Desafíos comunes
   * Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento
   * Los servicios en la nube no se pueden usar, por lo que se limitan las funcionalidades HoloLens 2 nube.
   * Mayor sobrecarga administrativa, ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.

Para obtener una guía de implementación similar a este escenario, revise nuestra [Guía de implementación segura sin conexión](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guía de implementación: seguridad sin conexión HoloLens 2](hololens-common-scenarios-offline-secure.md)
