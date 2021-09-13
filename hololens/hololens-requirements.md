---
title: Escenarios de implementación comunes
description: Obtenga más información sobre la implementación y administración de HoloLens en entornos empresariales, incluida la infraestructura, la Azure Active Directory y la administración de dispositivos móviles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033825"
---
# <a name="common-deployment-scenarios"></a>Escenarios de implementación comunes

## <a name="overview"></a>Información general

Averiguar cómo implementar un nuevo dispositivo puede ser un problema al probarlo por primera vez. En este caso, compartimos diferentes maneras de implementar y administrar Microsoft HoloLens 2 dispositivos dentro de la organización.

Quiere soluciones implementadas a escala. Queremos que llegue allí. En primer lugar, vamos a hablar sobre los pasos para implementar dispositivos, por lo tanto, hologramas, para lograr valor para el escenario de realidad mixta de destino, ya sea que use D365 Remote Assist, Guides o una aplicación habilitada para el servicio de realidad mixta de Azure que haya creado.

Puede ser un responsable de la toma de decisiones empresariales, profesional de TI o un equipo de innovación que HoloLens dentro de su organización. A medida que se compila desde una prueba de concepto a una implementación a escala, nuestras guías de implementación tienen sentido HoloLens dentro de la infraestructura de TI, independientemente de lo grande o pequeño que sea. Los siguientes escenarios de implementación son los más comunes:

| Escenario |Uso | Puntos clave |
|---------|---------|---------|
| [Escenario A: Dispositivos conectados a la nube](hololens2-cloud-connected-overview.md) | La primera vez que comience la implementación, puede iniciar un dispositivo pequeño e implementar un único dispositivo conectado a la nube solo para ver el proceso básico. | Los dispositivos se conectarán a servicios en la nube e Internet público. Esto es más adecuado para casos de uso del cliente, servicios de campo y prueba de concepto.|
| [Escenario B: red de la organización](hololens2-corp-connected-overview.md) | A medida que se implementa en producción a escala, es posible que tenga que integrarse con la red de su propia organización. | Los dispositivos se conectarán a una red Wi-Fi "corporativa". Esto es más adecuado para los usuarios internos o se usa dentro del entorno corporativo.|
| [Escenario C: entorno seguro sin conexión](hololens-common-scenarios-offline-secure.md) | Algunos procesos críticos o algunas directivas corporativas pueden exigir el uso de entornos sin conexión. | Los dispositivos se conectarán a una red muy restrictiva o serán dispositivos puramente sin conexión. Esto es más adecuado para entornos altamente seguros o restricciones de conectividad a Internet en áreas remotas. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Escenario A: Implementación en dispositivos conectados a la nube

Este escenario es comparable a la implementación de dispositivos móviles administrados dentro de una empresa. HoloLens 2 se implementa para su uso principalmente en entornos externos a una red corporativa. No se accede a los recursos corporativos o se puede limitar a través de VPN.

[![Diagrama del escenario A.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Cuándo se usa

Considere este modelo de implementación para:

* Implementación de pruebas de concepto, pilotos y servicios de campo
* Implementación de [Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Configuraciones comunes básicas

* Wi-Fi las redes están totalmente abiertas a Internet y a los servicios en la nube
* Azure AD unirse a la inscripción automática de Administración de dispositivos móviles (MDM): MDM (Intune) administrado
* Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
  * Se admiten uno o varios usuarios por dispositivo.
* Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
* Una o varias aplicaciones se implementan a través de MDM

### <a name="common-challenges"></a>Desafíos comunes

* Determinar qué configuraciones de MDM se aplicarán a la HoloLens 2 en función de los requisitos del escenario

En la guía conectada a la nube correspondiente se explica cómo inscribir HoloLens 2 en la administración de dispositivos, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar inmediatamente Remote Assist tras la configuración del dispositivo.

> [!div class="nextstepaction"]
> [Guía de implementación conectada a la nube](hololens2-cloud-connected-overview.md)

Use la guía Clientes externos para implementar dispositivos en un sitio remoto para su uso externo a corto o largo plazo.

> [!div class="nextstepaction"]
> [Guía de implementación conectada a la nube (clientes externos)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Escenario B: Implementación dentro de la red de la organización

Este escenario es idéntico a una implementación clásica para la mayoría Windows 10 equipos. HoloLens 2 se implementa para su uso principalmente en la red corporativa con acceso a recursos corporativos internos. Internet y los servicios en la nube pueden estar limitados. 

[![Diagrama del escenario B1.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagrama del escenario B2.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Cuándo se usa

Considere este modelo de implementación para:

* Usuarios internos
* Implementación a escala (piloto y producción) dentro del entorno corporativo

### <a name="basic-common-configurations"></a>Configuraciones comunes básicas

* Wi-Fi es una red corporativa interna con acceso a recursos internos y acceso limitado a Internet o a los servicios en la nube.
* Azure AD unirse a la inscripción automática de MDM
* MDM (Intune) administrado
* Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
  * Se admiten uno o varios usuarios por dispositivo.
* Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.
* Una o varias aplicaciones se implementan a través de MDM

### <a name="common-challenges"></a>Desafíos comunes

* HoloLens 2 no admite la unión a AD local o System Center Configuration Manager (SCCM). Solo Azure AD unirse a MDM. En la actualidad, muchas empresas todavía implementan equipos Windows 10 en este escenario como dispositivos unidos a AD locales, administrados por SCCM y es posible que no tengan la infraestructura implementada o configurada para administrar dispositivos Windows 10 internos a través de soluciones MDM basadas en la nube.
* Como HoloLens 2 es un primer dispositivo en la nube, se basa en gran medida en los servicios conectados a Internet y en la nube para la autenticación de usuarios, las actualizaciones del sistema operativo, la administración de MDM, y así sucesivamente. Al conectarse a una red corporativa, lo más probable es que sea necesario ajustar las reglas de proxy o firewall para habilitar el acceso a HoloLens 2 y a las aplicaciones que se ejecutan en ella.
* La Wi-Fi corporativa normalmente requiere certificados para autenticar el dispositivo o el usuario en la red. La infraestructura o la configuración necesarias para implementar certificados en Windows 10 dispositivos a través de MDM puede ser difícil de configurar.

La guía conectada corporativa correspondiente indica cómo inscribir HoloLens 2 en la administración de dispositivos existente, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar una guía de Dynamics 365, así como usar aplicaciones de línea de negocio personalizadas, después de configurar el dispositivo.

> [!div class="nextstepaction"]
> [Guía de implementación conectada corporativa](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Escenario C: Implementación en un entorno sin conexión seguro

Se trata de una implementación típica para ubicaciones altamente seguras o confidenciales. HoloLens 2 se implementa para su uso principalmente sin conexión sin acceso a la red o a Internet.

[![Diagrama seguro sin conexión 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Cuándo se usa

Considere este modelo de implementación para:

* Entornos altamente seguros en los que es necesario conservar los datos en casa
* "Experiencias" en las que el público va a usar los dispositivos
* Problema de conectividad a Internet en el área remota

### <a name="basic-common-configurations"></a>Configuraciones comunes básicas

* Wi-Fi conectividad está deshabilitada. Ethernet a través de USB puede estar habilitado para la conectividad LAN si es necesario
* No administrado
* Cuenta de usuario local para el inicio de sesión del dispositivo
  * HoloLens 2 solo admite una cuenta local
* Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican a través de paquetes de aprovisionamiento en función de casos de uso específicos. Estas configuraciones suelen estar restringidas debido a los requisitos de entorno seguro.
* Una o varias aplicaciones se implementan a través del paquete de aprovisionamiento

### <a name="common-challenges"></a>Desafíos comunes

* Hay un conjunto limitado de configuraciones disponibles a través de paquetes de aprovisionamiento
* Los servicios en la nube no se pueden usar, por lo que se limitan las funcionalidades HoloLens 2 nube.
* Mayor sobrecarga administrativa, ya que estos dispositivos deben configurarse, configurarse y actualizarse manualmente.

La guía segura sin conexión correspondiente proporciona instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros.

> [!div class="nextstepaction"]
> [Guía de implementación de entornos seguros sin conexión](hololens-common-scenarios-offline-secure.md)
