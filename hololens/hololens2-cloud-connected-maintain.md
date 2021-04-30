---
title: 'Guía de implementación: implementación de HoloLens 2 en la nube a escala con Remote Assist - Mantener'
description: Manténgase al día con nuestras sugerencias para mantener y admitir dispositivos HoloLens a través de una red conectada a la nube.
keywords: HoloLens, administración, conexión a la nube, Remote Assist, AAD, Azure AD, MDM, Mobile Administración de dispositivos
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310223"
---
# <a name="maintain---cloud-connected-guide"></a>Mantener: guía conectada a la nube

## <a name="updates"></a>Actualizaciones

Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.

Obtenga información sobre cómo administrar [las actualizaciones de HoloLens, incluidos](https://docs.microsoft.com/hololens/hololens-updates) los días programados, la hora programada y la configuración de horas activas en el dispositivo para que se actualice fuera del horario laboral.

Remote Assist es una In-Box y se puede actualizar a través de Microsoft Store aplicación. Para todas las aplicaciones que se descargan a través del Microsoft Store pueden actualizarse a través de la propia [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) aplicación de forma manual.

## <a name="support-plan"></a>Plan de soporte técnico

Un plan de soporte técnico es un elemento excelente que se debe tener en cuenta. Es útil tener a alguien o a un grupo entrenado para solucionar problemas del proceso de inscripción en dispositivos HoloLens y también al uso general del dispositivo HoloLens dentro de su organización. Para permitir que los usuarios tengan la resolución más rápida de sus problemas, se recomienda que el proceso de escalado se controle de forma similar a este orden:

1. El equipo de soporte técnico.
2. Su equipo de expertos de HoloLens
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Documentos de solución de problemas de HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Ponerse en contacto con el soporte técnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plan de desarrollo

Con el dispositivo inscrito correctamente, ahora está preparado para implementar aplicaciones de línea de negocio (aplicaciones LOB) en los dispositivos. Se trata de aplicaciones personalizadas creadas para las necesidades&#39;organización.

Si ya tiene una aplicación de línea de negocio,&#39;listo para implementar la aplicación a [través de MDM.](https://docs.microsoft.com/hololens/app-deploy-intune) Si prefiere&#39;método diferente, revise la introducción a la implementación de aplicaciones de [HoloLens 2 para](https://docs.microsoft.com/hololens/app-deploy-overview) obtener más métodos de implementación de la aplicación lob en los dispositivos.

Si aún&#39;ha creado su propia aplicación de LOB o todavía está en proceso de creación, revise nuestros documentos de desarrollo de realidad mixta para empezar a diseñar y crear prototipos u aprender los conceptos básicos para empezar a trabajar con el desarrollo de realidad [mixta.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr) [](https://docs.microsoft.com/windows/mixed-reality/design/design)

## <a name="device-management"></a>Administración del dispositivo 

Aunque en esta guía se ha hablado sobre la configuración de Mobile Administración de dispositivos (MDM), no se empleó para aplicar restricciones de dispositivos o se aplicaron directivas a los dispositivos. La administración de dispositivos se puede usar para permitir el acceso mediante la insertar certificados o restringir el acceso con una variedad de restricciones de dispositivos. 

En muchos casos, los dispositivos pueden tener restricciones de conectividad como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o al micrófono. Si alguno de estos intereses le interesa, le recomendamos que lea nuestra página [de restricciones de dispositivos comunes](hololens-common-device-restrictions.md).

Hay otras restricciones de dispositivos más complejas que puede usar. Como:

- Limitar las páginas que se pueden ver en la aplicación Configuración mediante [SettingsPageVisibility](settings-uri-list.md), lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su conexión Wi-Fi usuario.
- Use [el modo de pantalla](hololens-kiosk.md) completa para limitar la interfaz de usuario que se presenta a los usuarios en un dispositivo. Puede establecer Quioscos para mostrar una sola aplicación o varias aplicaciones con una página de inicio personalizada. Los quioscos también pueden presentar experiencias diferentes a distintos usuarios.  
- [Control de aplicaciones de Windows (WDAC) para](windows-defender-application-control-wdac.md) evitar que aplicaciones o procesos específicos se inicien por completo.

Si desea obtener información sobre otros métodos diferentes de administración de dispositivos o restricciones de dispositivos, siga el paso siguiente y lea la información general Administración de dispositivos dispositivos.

## <a name="next-step"></a>Paso siguiente

> [!div class="nextstepaction"]
> [Lea la información general sobre los Administración de dispositivos DE CSP.](hololens-csp-policy-overview.md)