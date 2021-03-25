---
title: 'Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365: mantener'
description: Obtenga información sobre cómo mantener dispositivos HoloLens 2 a través de una red conectada corporativa con guías de Dynamics 365.
keywords: HoloLens, administración, con conexión corporativa, Guías de Dynamics 365, AAD, Azure AD, MDM, Administración de dispositivos móviles
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448626"
---
# <a name="maintain---corporate-connected-guide"></a>Mantener: Guía de conexión corporativa

## <a name="update-hololens"></a>Actualizar HoloLens

Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.

Un método popular para administrar actualizaciones es realizar un aplazamiento de características de 30 días. Esto permite a los administradores actualizar y obtener una vista previa de las nuevas características, para obtener conocimientos de primera mano e informar al departamento de soporte técnico de cualquier cambio nuevo.

Aprende a administrar las actualizaciones [de HoloLens,](https://docs.microsoft.com/hololens/hololens-updates)incluidos los días programados, la hora programada y la configuración de horas activas en el dispositivo, para que se actualice fuera del horario laboral.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Cómo actualizar las Guías de Dynamics 365 (y otras aplicaciones de la tienda)

Guías de Dynamics 365 es una In-Box y se puede actualizar a través de la aplicación de Microsoft Store. Para todas las aplicaciones que se descargan a través de la Microsoft Store, se pueden actualizar a través de la propia [aplicación de Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) manualmente.

## <a name="how-to-update-lob-apps"></a>Cómo actualizar aplicaciones de LOB

Las aplicaciones de LOB se pueden actualizar de la misma manera que se agregaron a Intune. Las aplicaciones se pueden actualizar en Intune cargando la nueva aplicación con un número de versión superior a la configuración de la aplicación existente. Cuando el dispositivo se sincroniza con Intune, observará que hay una versión de la aplicación más reciente y la aplicación más reciente se descargará y reemplazará a la aplicación antigua.

1. Para cargar la aplicación más reciente, vaya al [portal de MEM](https://endpoint.microsoft.com/#home)Aplicaciones -> Todas las aplicaciones  ->  **** Propiedades de ****  ->  *TheNameOfYourApp.*  ->  ****
2. Junto a Información de la aplicación, selecciona **Editar.**
3. Para el valor de &quot; Seleccionar archivo que se &quot; actualizará, seleccione el archivo.
4. Desde aquí, usa el menú contextual para abrir el explorador de archivos y cargar la versión más reciente de la aplicación LOB. Asegúrese de incluir las dependencias según sea necesario.

Ver más: [Implementación de aplicaciones de Intune para HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plan de desarrollo

Con el dispositivo inscrito correctamente, ahora estás preparado para implementar más aplicaciones de LOB en tus dispositivos. Durante la duración de esta Guía, estamos usando una aplicación de ejemplo, pero es más probable que quieras usar aplicaciones personalizadas creadas para las necesidades de tu organización.

Si ya tienes una aplicación de LOB, estás listo para [implementar la aplicación a través de MDM](https://docs.microsoft.com/hololens/app-deploy-intune). Si prefieres un método diferente, revisa la introducción a la implementación de aplicaciones de [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) para obtener más información sobre los métodos para implementar la aplicación de LOB en tus dispositivos.

Si aún no has creado tu propia aplicación de LOB o aún estás en proceso de [](https://docs.microsoft.com/windows/mixed-reality/design/design) creación, revisa nuestros documentos de desarrollo de realidad mixta para empezar a diseñar y crear prototipos o aprender los conceptos básicos para empezar a desarrollar realidad [mixta.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plan de soporte técnico

Un plan de soporte es una excelente cosa que se debe tener en cuenta. Es útil tener alguien o un grupo formado para solucionar problemas del proceso de inscripción en dispositivos HoloLens y también el uso general del dispositivo HoloLens en su organización. Para permitir que los usuarios tengan una solución más rápida de sus problemas, le sugerimos que el proceso de escalamiento se controle de forma similar a este orden:

1. Su servicio de soporte técnico.
2. Su equipo de expertos de HoloLens
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Contactar con el soporte técnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Administración del dispositivo

En esta guía se ha hablado sobre cómo configurar la administración de dispositivos móviles (MDM) y se usa para configurar algunas configuraciones de dispositivos y aplicar la configuración para permitir el acceso en términos de Wi-Fi certificados y proxy. Sin embargo, MDM también se puede usar para aplicar restricciones de dispositivos a través de CSP y directivas.

En muchos casos, los dispositivos pueden tener restricciones de conectividad, como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o el micrófono. Si alguno de estos intereses te interesa, te recomendamos que leas nuestra [página de restricciones de dispositivos comunes](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).

Hay otras restricciones de dispositivo más complejas que puedes usar. Por ejemplo:

- Limitar las páginas que se pueden ver en la aplicación Configuración mediante [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su conexión Wi-Fi usuario.
- Usa [el modo quiosco](https://docs.microsoft.com/hololens/hololens-kiosk) para limitar la interfaz de usuario presentada a los usuarios de un dispositivo. Puedes establecer quioscos para que muestren una sola aplicación o varias aplicaciones con una página de inicio personalizada. Los quioscos también pueden presentar diferentes experiencias a diferentes usuarios.
- [Control de aplicaciones de Windows (WDAC) para](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) evitar que aplicaciones o procesos específicos se inicien por completo.

Si quieres obtener información sobre métodos adicionales de administración de dispositivos o restricciones de dispositivos, sigue el siguiente paso y lee información general sobre administración [de dispositivos.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





