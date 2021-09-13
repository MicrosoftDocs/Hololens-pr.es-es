---
title: 'Guía de implementación: HoloLens 2 con conexión corporativa con Dynamics 365 Guides - Mantener'
description: Obtenga información sobre cómo mantener HoloLens 2 a través de una red conectada corporativa con Dynamics 365 Guides.
keywords: HoloLens, administración, con conexión corporativa, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Administración de dispositivos
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033429"
---
# <a name="maintain---corporate-connected-guide"></a>Mantener: Guía de conexión corporativa

## <a name="update-hololens"></a>Actualización de HoloLens

Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones.

Un método popular para administrar actualizaciones es realizar un aplazamiento de características de 30 días. Esto permite a los administradores actualizar y obtener una vista previa de las nuevas características, y obtener conocimientos de primera mano e informar al departamento de soporte técnico de los nuevos cambios.

Obtenga información sobre cómo [administrar HoloLens](/hololens/hololens-updates)actualizaciones, incluidos los días programados, la hora programada y la configuración de horas activas en el dispositivo, para que se actualice fuera del horario laboral.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Actualización de Dynamics 365 Guides (y otras aplicaciones de la tienda)

Dynamics 365 Guides es una In-Box y se puede actualizar a través de Microsoft Store aplicación. Para todas las aplicaciones que se descargan a través del Microsoft Store, se pueden actualizar a través de Microsoft Store [propia](/hololens/holographic-store-apps#update-apps) aplicación manualmente.

## <a name="how-to-update-lob-apps"></a>Actualización de aplicaciones lob

Las aplicaciones loB se pueden actualizar de la misma manera que se agregaron a Intune. Las aplicaciones se pueden actualizar en Intune cargando la nueva aplicación con un número de versión más alto en la configuración de la aplicación existente. Cuando el dispositivo se sincroniza con Intune, observará que hay una versión más reciente de la aplicación y que la aplicación más reciente se descargará y reemplazará la aplicación anterior.

1. Para cargar la aplicación más reciente, vaya al [portal de MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> All **apps** TheNameOfYourApp Properties (Aplicaciones -> todas las aplicaciones  ->  *TheNameOfYourApp*  ->  **Properties).**
2. Junto a Información de la aplicación, seleccione **Editar.**
3. Para el valor de &quot; Select file to update (Seleccionar archivo para &quot; actualizar), seleccione el archivo.
4. Desde aquí, use el menú contextual para abrir el explorador de archivos y cargar la versión más reciente de la aplicación LOB. Asegúrese de incluir las dependencias según sea necesario.

Vea más: [Implementación de aplicaciones de Intune para HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plan de desarrollo

Con el dispositivo inscrito correctamente, ahora está preparado para implementar más aplicaciones de LOB en los dispositivos. Mientras dure esta guía, usamos una aplicación de ejemplo, pero es más probable que quiera usar aplicaciones personalizadas creadas para las necesidades de su organización.

Si ya tiene una aplicación de LOB, está listo para [implementar la aplicación a través de MDM.](/hololens/app-deploy-intune) Si prefiere un método diferente, revise la introducción a la implementación de aplicaciones de [HoloLens 2](/hololens/app-deploy-overview) para obtener más métodos de implementación de la aplicación de LOB en los dispositivos.

Si aún no ha creado su propia aplicación de LOB o todavía está en proceso de [](/windows/mixed-reality/design/design) creación, revise nuestros documentos de desarrollo de realidad mixta para empezar a diseñar y crear prototipos u aprender los conceptos básicos para empezar a trabajar con el desarrollo de realidad [mixta.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plan de soporte técnico

Un plan de soporte técnico es un elemento excelente que se debe tener en cuenta. Es útil tener a alguien o a un grupo entrenado para solucionar problemas del proceso de inscripción en dispositivos HoloLens y también al uso general del dispositivo HoloLens dentro de la organización. Para permitir que los usuarios tengan la resolución más rápida de sus problemas, se recomienda que el proceso de escalado se controle de forma similar a este orden:

1. El equipo de soporte técnico.
2. Su HoloLens experto
3. [HoloLens Docs](/hololens/)  /  [HoloLens documentos de solución de problemas](/hololens/hololens-troubleshooting)
4. [Ponerse en contacto con el soporte técnico](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Administración del dispositivo

En esta guía se ha hablado sobre la configuración de Mobile Administración de dispositivos (MDM) y se ha usado para configurar algunas configuraciones de dispositivo y aplicar la configuración para permitir el acceso en términos de Wi-Fi certificados y proxy. Sin embargo, MDM también se puede usar para aplicar restricciones de dispositivos a través de CSP y directivas.

En muchos casos, los dispositivos pueden tener restricciones de conectividad, como Bluetooth, VPN, USB o incluso desactivar el acceso a la cámara o el micrófono. Si alguno de estos le interesa, le recomendamos que lea nuestra página [de restricciones de dispositivos comunes](/hololens/hololens-common-device-restrictions).

Hay otras restricciones de dispositivos más complejas que puede usar. Como:

- Limitar las páginas que se pueden ver en la aplicación Configuración mediante [SettingsPageVisibility](/hololens/settings-uri-list), lo que permite a los usuarios acceder solo a la configuración que necesitan ajustar, como cambiar su conexión Wi-Fi.
- Use [el modo de pantalla completa](/hololens/hololens-kiosk) para limitar la interfaz de usuario presentada a los usuarios en un dispositivo. Puede establecer Quioscos para mostrar una sola aplicación o varias aplicaciones con una página de inicio personalizada. Los quioscos también pueden presentar diferentes experiencias a distintos usuarios.
- [Windows Control de aplicaciones (WDAC) para](/hololens/windows-defender-application-control-wdac) evitar que aplicaciones o procesos específicos se inicien por completo.

Si desea obtener información sobre métodos adicionales de administración de dispositivos o restricciones de dispositivos, siga el paso siguiente y lea nuestra información [general Administración de dispositivos de dispositivos.](/hololens/hololens-csp-policy-overview)





