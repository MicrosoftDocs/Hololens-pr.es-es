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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397430"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>Información general sobre escenarios comunes de implementación de infraestructura

Esta información siguiente proporciona información general sobre la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar Microsoft HoloLens 2 dispositivos dentro de la empresa. A menudo, la forma en que administra los dispositivos y cómo acceder a los recursos de la organización viene determinada en gran medida por factores ya establecidos. En función de la infraestructura existente, le invitamos a revisar el estilo común de administración de dispositivos en los escenarios siguientes y probar nuestras guías para implementar en el escenario que se acoda a sus necesidades.

## <a name="scenarios"></a>Escenarios

El diagrama siguiente representa dos escenarios administrados típicos para HoloLens 2 implementaciones.
 

También hay un tercer escenario que permite implementaciones seguras sin conexión.

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Escenario A: Implementación en dispositivos conectados a la nube

HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa. No se accede a los recursos corporativos o se puede limitar a través de VPN. Esta implementación es similar a los dispositivos móviles administrados dentro de una empresa.
 * Configuraciones comunes básicas
   * Wi-Fi las redes están completamente abiertas a Internet y a los servicios en la nube.
   * Azure AD unirse a la inscripción automática de Administración de dispositivos móviles (MDM): MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Pantalla completa de aplicación única.
   * Una o varias aplicaciones se implementan a través de MDM



* Desafíos comunes
   * Determinar qué configuraciones de MDM se aplicarán a la HoloLens 2 en función de los requisitos del escenario.

[![Diagrama del escenario A ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

Para obtener una guía de implementación similar a este escenario, revise nuestra guía de la guía de implementación del entorno [conectado a la nube](hololens2-cloud-connected-overview.md).

> [!div class="nextstepaction"]
> [Guía de implementación del entorno conectado a la nube](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [Guía de implementación del entorno conectado a la nube (clientes externos)](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>Escenario B: Implementación dentro de la red de la organización

HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos. Internet y los servicios en la nube pueden estar limitados. Esta implementación es una implementación típica para la mayoría Windows 10 equipos.

 * Configuraciones comunes básicas
   * Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o a los servicios en la nube.
   * Azure AD unirse a la inscripción automática de MDM
   * MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo.
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o varias aplicaciones se implementan a través de MDM

 * Desafíos comunes
   * HoloLens 2 no admite la unión a AD local ni SCCM. Solo Azure AD unirse a MDM. En la actualidad, muchas empresas todavía implementan equipos Windows 10 en este escenario como dispositivos unidos a AD local, administrados por System Center Administrador de configuración (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.
   * Como HoloLens 2 es un primer dispositivo en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, entre otros. Al conectarse a una red corporativa, lo más probable es que las reglas de proxy o firewall deban ajustarse para permitir el acceso a HoloLens 2 y a las aplicaciones que se ejecutan en ella.
   * La Wi-Fi corporativa normalmente requiere certificados para autenticar el dispositivo o el usuario en la red. La infraestructura o la configuración necesarias para implementar certificados en Windows 10 dispositivos a través de MDM puede ser difícil de configurar.

[![Diagrama del escenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama del escenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Para obtener una guía de implementación similar a este escenario, revise nuestra guía de guía [de implementación de red corporativa](hololens2-corp-connected-overview.md).

> [!div class="nextstepaction"]
> [Guía de implementación de redes corporativas](hololens2-corp-connected-overview.md)

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

[![Diagrama seguro sin conexión 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Para obtener una guía de implementación similar a este escenario, revise nuestra guía de implementación de entorno seguro [sin conexión](hololens-common-scenarios-offline-secure.md).

> [!div class="nextstepaction"]
> [Guía de implementación de entornos seguros sin conexión](hololens-common-scenarios-offline-secure.md)
