---
title: Cumplimiento y RGPD de HoloLens 2
description: Documentación del RGPD
keywords: HoloLens, RGPD, privacidad, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324882"
---
# Declaración de privacidad de HoloLens 2

Uno de los elementos principales del RGPD es la "protección de datos por diseño". Este concepto se aplica especialmente a dispositivos móviles, como HoloLens 2, debido a su portabilidad, conexiones a Internet ilimitadas y canales de comunicación abiertos. Como resultado, la seguridad de [](https://docs.microsoft.com/hololens/security-architecture) HoloLens 2 se ha rediseñado para proporcionar protección avanzada e innovadora de seguridad y privacidad, de un extremo a otro, incorporando tanto el enfoque de Microsoft para la privacidad como las normativas del [RGPD.](https://privacy.microsoft.com/)

 >[!NOTE]
> Este documento no se aplica a HoloLens (1.ª generación).

## Introducción a la privacidad

HoloLens 2 es un equipo windows autocontenido que ejecuta Windows Holographic y ejecuta aplicaciones y soluciones en un entorno envolvente de realidad mixta. Puede usarse como dispositivo sin conexión seguro o implementarse como [dispositivo administrado](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) dentro de la organización. Consulta los siguientes vínculos para comprender cómo HoloLens 2 y Microsoft usan y protegen tus datos:
1. [Declaración de privacidad de Microsoft: HoloLens:](https://privacy.microsoft.com/privacystatement) expanda la sección Empresa y desarrollador en el menú de navegación izquierdo y seleccione Aplicaciones y software empresarial **y de desarrollador.** **** Ve a la **sección HoloLens.**
2.  [Windows 10 y los servicios en línea](https://privacy.microsoft.com/windows10privacy)
3.  [Guía de Windows 10 y el cumplimiento de privacidad](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Privacidad y datos personales en Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## Seguridad de red
Después de los [escenarios](https://docs.microsoft.com/hololens/common-scenarios)comunes de implementación de HoloLens 2, los datos estarán protegidos por el cumplimiento de nivel mundial de [Azure,](https://docs.microsoft.com/azure/compliance/) junto con la integración de estándares legales y normativos. Si no tiene experiencia con Azure AD y Dynamics 365 Remote Assist, consulte la lista de comprobación de preparación de responsabilidad de Azure y [Dynamics 365](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)para el RGPD.

Además, Windows Defender Firewall ofrece funcionalidad crítica para proteger la conectividad de dispositivos. Con HoloLens 2, el firewall siempre está habilitado y no hay ninguna manera de deshabilitarlo mediante programación o por medio de la interfaz de usuario. Cuando HoloLens 2 se implementa como dispositivo administrado con [Intune,](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)hay más funcionalidad de cumplimiento disponible con la integración de Endpoint con [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) como solución de Mobile Threat Defense. 

Obtenga más información sobre la arquitectura y seguridad de HoloLens [2.](https://docs.microsoft.com/hololens/security-architecture)

## Seguridad del sistema operativo
Las actualizaciones se realizan automáticamente (de forma predeterminada) para que HoloLens 2 esté siempre actualizado con la versión más reciente de Windows Holographic y cualquier aplicación instalada. Vea lo siguiente para obtener más información sobre cómo nuestro sistema operativo está diseñado de forma segura:
1. [Separación y aislamiento de estado](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Sistema operativo sin administrador](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Limitar el uso de contraseñas](https://docs.microsoft.com/hololens/security-limiting-password-use)

## Seguridad física
HoloLens 2 tiene memoria flash que está protegida por el [cifrado de BitLocker](https://docs.microsoft.com/hololens/security-encryption-data-protection). El dispositivo y sus datos locales se pueden flashear sin conexión con [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) o borrarse de forma remota a través de MDM si se ha implementado como dispositivo administrado.

## Protección de datos
Las actualizaciones de Windows se ejecutan automáticamente (de forma predeterminada) y la integración [de Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) protege los datos que viajan entre sí y la nube. 

Al implementar HoloLens 2 en clientes externos, [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) garantiza que los datos y los recursos confidenciales de la empresa sean independientes y seguros. 

Mdm o el usuario pueden configurar manualmente el uso compartido de datos de diagnóstico con Microsoft durante la OOBE. Hay dos opciones: datos de diagnóstico opcionales y datos de diagnóstico necesarios. Si es necesario cambiar la configuración de diagnóstico original en un momento posterior para solucionar problemas, el usuario puede cambiarla en Configuración -> Privacidad **->** Comentarios de diagnóstico & o el administrador de TI (MDM) si es un dispositivo administrado. Consulta más sobre [diagnósticos, comentarios y privacidad en Windows 10.](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> Los registros de diagnóstico de dispositivos contienen información de identificación personal (PII), como sobre qué procesos o aplicaciones inicia el usuario durante las operaciones típicas. Cuando varios usuarios comparten un dispositivo HoloLens (por ejemplo, los usuarios inician sesión en el mismo dispositivo con diferentes cuentas de Microsoft Azure Active Directory (Azure AD), los registros de diagnóstico pueden contener información de PII que se aplica a varios usuarios.

 

Existen varios [métodos de recopilación y directivas de retención de datos](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) para recopilar datos de diagnóstico de HoloLens 2.  Para obtener más información acerca de cómo Microsoft recopila y usa datos de diagnóstico, consulte Declaración de privacidad de [Microsoft: Diagnóstico:](https://privacy.microsoft.com/privacystatement) expanda **Windows** en el menú de navegación izquierdo y seleccione **Diagnóstico.** Vaya a la **sección Diagnóstico.**
