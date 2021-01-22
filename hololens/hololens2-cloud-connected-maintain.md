---
title: 'Guía de implementación: implementación de HoloLens 2 conectada en la nube a escala con asistencia remota: mantenimiento'
description: Manténgase al día con nuestras sugerencias para mantener y admitir dispositivos HoloLens a través de una red conectada a la nube.
keywords: HoloLens, administración, conectado a la nube, Asistencia remota, AAD, Azure AD, MDM, Administración de dispositivos móviles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283901"
---
# Mantenimiento: Guía conectada a la nube

## Actualizaciones

Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.

Aprende a administrar las actualizaciones [de HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) incluidos los días programados, la hora programada y la configuración de horas activas en el dispositivo para que se actualice fuera del horario laboral.

Asistencia remota es una In-Box aplicación y se puede actualizar a través de la aplicación de Microsoft Store. Para todas las aplicaciones que se descargan a través de Microsoft Store, se pueden actualizar a través de la propia aplicación [de Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) manualmente.

## Plan de soporte técnico

Un plan de soporte es una cosa excelente que debe tener en su lugar. Es útil contar con alguien o un grupo formado para solucionar problemas del proceso de inscripción en dispositivos HoloLens y también el uso general del dispositivo HoloLens dentro de la organización. Para permitir que los usuarios tengan la resolución más rápida de sus problemas, le sugerimos que el proceso de escalación se controle de forma similar a este orden:

1. Su servicio de soporte técnico.
2. Su equipo de expertos de HoloLens
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Documentos para la solución de problemas de HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contactar con el soporte técnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Plan de desarrollo

Con el dispositivo inscrito correctamente, ahora estás preparado para implementar aplicaciones de línea de negocio (aplicaciones de LÍNEA DEB) en tus dispositivos. Se trata de aplicaciones personalizadas creadas para las necesidades&#39;organización.

Si ya tienes una aplicación de línea de negocio,&#39;estás listo para implementar la aplicación a [través de MDM.](https://docs.microsoft.com/hololens/app-deploy-intune) Si prefiere&#39;otro método, revise la introducción a la implementación de aplicaciones de [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para obtener más información sobre los métodos de implementación de la aplicación lob en sus dispositivos.

Si aún&#39;crear tu propia aplicación de LOB o aún estás en proceso de creación, [](https://docs.microsoft.com/windows/mixed-reality/design/design) revisa nuestros documentos de desarrollo de realidad mixta para empezar a diseñar y crear prototipos, o aprende los conceptos básicos para empezar a desarrollar realidad [mixta.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## Administración del dispositivo 

Aunque en esta guía se habla sobre cómo configurar la administración de dispositivos móviles (MDM), no se utilizó para aplicar restricciones de dispositivos o se aplicaron directivas a los dispositivos. La administración de dispositivos se puede usar para permitir el acceso al insertar certificados o restringir el acceso con una variedad de restricciones de dispositivo. 

En muchos casos, los dispositivos pueden tener restricciones de conectividad como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o el micrófono. Si alguno de estos intereses te interesa, te animamos a leer nuestra página [de restricciones de dispositivos comunes.](hololens-common-device-restrictions.md)

Hay otras restricciones de dispositivo más complejas que puedes usar. Por ejemplo:

- Limitar las páginas que se pueden ver en la aplicación Configuración mediante [SettingsPageVisibility,](settings-uri-list.md)lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su conexión Wi-Fi usuario.
- Usa [el modo de pantalla completa](hololens-kiosk.md) para limitar la interfaz de usuario que se presenta a los usuarios de un dispositivo. Puedes establecer quioscos para mostrar una sola aplicación o varias aplicaciones con una página de inicio personalizada. Los quioscos también pueden presentar distintas experiencias a diferentes usuarios.  
- [Control de aplicaciones de Windows (WDAC) para](windows-defender-application-control-wdac.md) evitar que aplicaciones o procesos específicos se inicien por completo.

Si quieres obtener información sobre otros métodos de administración de dispositivos o restricciones de dispositivos, sigue el siguiente paso y lee nuestra introducción a la administración de dispositivos.

## Paso siguiente

> [!div class="nextstepaction"]
> [Leer la introducción a los SSP y la administración de dispositivos](hololens-csp-policy-overview.md)