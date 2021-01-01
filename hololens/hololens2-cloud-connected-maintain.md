---
title: 'Guía de implementación: implementación de la nube conectada a HoloLens 2 a escala con asistencia remota-mantenimiento'
description: Sugerencias para mantener dispositivos HoloLens en una red conectada en la nube
keywords: HoloLens, administración, nube conectada, asistencia remota, AAD, Azure AD, MDM, administración de dispositivos móviles
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252701"
---
# Mantener-guía conectada a la nube

## Actualizaciones

Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.

Más información sobre cómo [administrar las actualizaciones de HoloLens](https://docs.microsoft.com/hololens/hololens-updates) , incluidos días programados, tiempo programado y la configuración de horas activas en el dispositivo para que se actualice fuera del horario laboral.

Asistencia remota es una aplicación In-Box y puede actualizarse a través de la aplicación Microsoft Store. Para todas las aplicaciones que se descargan a través de Microsoft Store, se pueden [actualizar mediante la aplicación de Microsoft Store en](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) forma manual.

## Plan de soporte técnico

Un plan de soporte técnico es un aspecto excelente para hacerlo. Es útil tener a una persona, o a un grupo con formación para solucionar el proceso de inscripción en dispositivos HoloLens, además del uso general del dispositivo HoloLens dentro de su organización. Para que los usuarios puedan tener la resolución más rápida de sus problemas, sugerimos que el proceso de escalado se gestione de forma similar a la siguiente orden:

1. Tu servicio de asistencia al cliente.
2. Tu equipo de expertos de HoloLens
3. [Documentos](https://docs.microsoft.com/hololens/)  /  de HoloLens [Documentación para la solución de problemas de HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contactar con el soporte técnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## Plan de desarrollo

Con el dispositivo correctamente inscrito, ahora está preparado para implementar las aplicaciones de la línea de negocios (aplicaciones LOB) en sus dispositivos. Estas son aplicaciones personalizadas creadas para su organización&#39;s necesidades.

Si ya tiene una aplicación de línea de negocio,&#39;listo para [implementar la aplicación a través de MDM](https://docs.microsoft.com/hololens/app-deploy-intune). Si&#39;d preferir un método diferente, revise la [información general sobre la implementación de la aplicación para HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para obtener más métodos para implementar su aplicación de LOB en sus dispositivos.

Si aún no ha&#39;creado su propia aplicación de LOB o aún está en proceso de creación, revise nuestros documentos de desarrollo de realidad mixta para [empezar a diseñar y generar prototipos](https://docs.microsoft.com/windows/mixed-reality/design/design) o aprender los conceptos básicos para empezar a usar el [desarrollo de realidad mixta.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## Administración del dispositivo 

Aunque en esta guía se ha comentado la configuración de la administración de dispositivos móviles (MDM), no se empleó para aplicar restricciones de dispositivo o directivas que se aplicaron a los dispositivos. La administración de dispositivos se puede usar para permitir el acceso mediante la inserción de certificados o para restringir el acceso con una variedad de restricciones de dispositivos. 

En muchos casos, los dispositivos pueden tener restricciones de conectividad, como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o al micrófono. Si tienes alguno de estos intereses, te recomendamos que leas la [Página de restricciones de dispositivos comunes](hololens-common-device-restrictions.md).

Puedes usar otras restricciones de dispositivos más complejas. Como:

- Limitar las páginas que se pueden ver en la aplicación configuración con [SettingsPageVisibility](settings-uri-list.md), lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su Wi-Fi conexión.
- Use el [modo de pantalla completa](hololens-kiosk.md) para limitar la interfaz de usuario que se presenta a los usuarios en un dispositivo. Puede configurar quioscos para que muestren una sola aplicación o varias aplicaciones con una página de inicio personalizada. Los quioscos también pueden presentar distintas experiencias a diferentes usuarios.  
- [Control de aplicaciones de Windows (WDAC)](windows-defender-application-control-wdac.md) para evitar que determinadas aplicaciones o procesos se inicien por completo.

Si desea obtener más información sobre métodos de administración de dispositivos o restricciones de dispositivos, siga el siguiente paso y lea nuestra descripción general de la administración de dispositivos.

## Paso siguiente

> [!div class="nextstepaction"]
> [Leer los CSP y la descripción general de administración de dispositivos](hololens-csp-policy-overview.md)