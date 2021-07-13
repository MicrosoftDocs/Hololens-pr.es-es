---
title: Escenarios de implementación comunes
description: Obtenga más información sobre la implementación y administración de HoloLens en entornos empresariales, incluida la infraestructura, la Azure Active Directory y la administración de dispositivos móviles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635473"
---
# <a name="common-deployment-scenarios"></a>Escenarios de implementación comunes

## <a name="overview"></a>Información general

En esta página se proporciona información general sobre la arquitectura de alto nivel para tres escenarios comunes al implementar y administrar Microsoft HoloLens 2 dispositivos dentro de la empresa.

A menudo, la forma en que administra los dispositivos y accede a los recursos de la organización viene determinada en gran medida por factores ya establecidos. En función de la infraestructura existente, le invitamos a revisar el estilo común de administración de dispositivos (MDM) en los escenarios siguientes y, a continuación, [leer Planeamiento](hololens-core-components.md) de implementaciones de HoloLens 2 en un entorno comercial para determinar qué escenario se corresponde con sus necesidades. También hay tres guías correspondientes disponibles para su uso durante la implementación.


 1. [Guía de implementación del entorno conectado a la nube](hololens2-cloud-connected-overview.md)
     1. [Guía de implementación del entorno conectado a la nube (clientes externos)](hololens2-deployment-guide.md)
 1. [Guía de implementación de red corporativa](hololens2-corp-connected-overview.md)
 1. [Guía de implementación de entornos seguros sin conexión](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Escenario A: Implementación en dispositivos conectados a la nube

Este escenario es comparable a la implementación de dispositivos móviles administrados dentro de una empresa. HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa. No se accede a los recursos corporativos o se puede limitar a través de VPN. 
 * Configuraciones comunes básicas
   * Wi-Fi las redes están totalmente abiertas a Internet y a los servicios en la nube.
   * Azure AD unirse a mobile Administración de dispositivos (MDM) Auto Enrollment--MDM (Intune) Managed
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo.
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o varias aplicaciones se implementan a través de MDM

* Desafíos comunes
   * Determinar qué configuraciones de MDM se aplicarán a la HoloLens 2 en función de los requisitos del escenario.

[![Diagrama del escenario A ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

En la guía conectada a la nube correspondiente se explica cómo inscribir HoloLens 2 en la administración de dispositivos, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar inmediatamente Remote Assist tras la configuración del dispositivo. Use la guía Clientes externos para implementar dispositivos en un sitio remoto para su uso externo a corto o largo plazo.

> [!div class="nextstepaction"]
> [Guía de implementación del entorno conectado a la nube](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Guía de implementación del entorno conectado a la nube (clientes externos)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Escenario B: Implementación dentro de la red de la organización

Este escenario es idéntico a una implementación clásica para la mayoría Windows 10 equipos. HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos. Internet y los servicios en la nube pueden estar limitados. 

 * Configuraciones comunes básicas
   * Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o a los servicios en la nube.
   * Azure AD unirse a la inscripción automática de MDM
   * MDM (Intune) administrado
   * Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
     * Se admiten uno o varios usuarios por dispositivo.
   * Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
   * Una o varias aplicaciones se implementan a través de MDM

 * Desafíos comunes
   * HoloLens 2 no admite la unión a AD local ni SCCM. Solo Azure AD unirse a MDM. Actualmente, muchas empresas aún implementan equipos Windows 10 en este escenario como dispositivos unidos a AD local, administrados por System Center Configuration Manager (SCCM) y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.
   * Como HoloLens 2 es un dispositivo en primer lugar en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, y así sucesivamente. Al conectarse a una red corporativa, lo más probable es que las reglas de proxy o firewall deban ajustarse para habilitar el acceso para HoloLens 2 y las aplicaciones que se ejecutan en ella.
   * La Wi-Fi corporativa normalmente requiere certificados para autenticar el dispositivo o el usuario en la red. La infraestructura o la configuración necesarias para implementar certificados en Windows 10 dispositivos a través de MDM puede ser difícil de configurar.

[![Diagrama del escenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama del escenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

La guía de red corporativa correspondiente indica cómo inscribir HoloLens 2 en la administración de dispositivos existente, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar una guía de Dynamics 365, así como usar aplicaciones de línea de negocio personalizadas, después de configurar el dispositivo.

> [!div class="nextstepaction"]
> [Guía de implementación de red corporativa](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Escenario C: Implementación en un entorno sin conexión seguro

Se trata de una implementación típica para ubicaciones altamente seguras o confidenciales. HoloLens 2 se implementa para su uso principalmente sin conexión sin acceso a la red o a Internet. 
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

La guía segura sin conexión correspondiente proporciona instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros.

> [!div class="nextstepaction"]
> [Guía de implementación de entornos seguros sin conexión](hololens-common-scenarios-offline-secure.md)


