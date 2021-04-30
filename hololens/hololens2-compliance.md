---
title: HoloLens 2 cumplimiento normativo y RGPD
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310249"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 declaración de privacidad

Uno de los elementos principales del RGPD es la "protección de datos por diseño". Este concepto se aplica especialmente a los dispositivos móviles, como HoloLens 2, debido a su portabilidad, a las conexiones a Internet ilimitadas y a los canales de comunicación abiertos. Como resultado, la seguridad del [](https://docs.microsoft.com/hololens/security-architecture) HoloLens 2 se ha rediseñado para proporcionar una protección avanzada e innovadora de seguridad y privacidad, de un extremo a otro, que incorpora tanto el enfoque de Microsoft para la privacidad como las regulaciones del [RGPD.](https://privacy.microsoft.com/)

 >[!NOTE]
> Este documento no se aplica a HoloLens (1.ª generación).

## <a name="privacy-overview"></a>Información general sobre privacidad

HoloLens 2 es un equipo Windows independiente, que ejecuta Windows Holographic, que ejecuta aplicaciones y soluciones en un entorno de realidad mixta envolvente. Se puede usar como un dispositivo sin conexión seguro o implementarse como [un dispositivo administrado](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) dentro de la organización. Consulte los vínculos siguientes para comprender cómo el HoloLens 2 y Microsoft usan y protegen los datos:
1. [Declaración de privacidad de Microsoft: HoloLens:](https://privacy.microsoft.com/privacystatement) expanda la sección **Enterprise and developer** (Empresa y desarrollador) en el menú de navegación izquierdo y seleccione Enterprise and developer software and appliances (Software y dispositivos empresariales y para **desarrolladores).** Vaya a la **sección HoloLens.**
2.  [Windows 10 y su servicios en línea](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & de cumplimiento de privacidad](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Privacidad y datos personales en Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Seguridad de redes
Después de HoloLens 2 [escenarios](https://docs.microsoft.com/hololens/common-scenarios)comunes de implementación, los datos estarán protegidos por el cumplimiento de nivel mundial de [Azure](https://docs.microsoft.com/azure/compliance/) junto con la integración de estándares legales y normativos. Si no está nunca Azure AD y Dynamics 365 Remote Assist, haga referencia a la lista de comprobación de preparación para la responsabilidad de Azure y [Dynamics 365 para el RGPD.](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)

Además, Firewall de Windows Defender proporciona funcionalidad crítica para proteger la conectividad del dispositivo. Con HoloLens 2, el firewall siempre está habilitado y no hay maneras de deshabilitarlo mediante programación o a través de la interfaz de usuario. Cuando el HoloLens 2 se implementa como un dispositivo administrado mediante [Intune,](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)hay más funcionalidad de cumplimiento disponible con la integración de [Endpoint con Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) como una solución de Mobile Threat Defense. 

Obtenga más información sobre la HoloLens 2 [y la arquitectura](https://docs.microsoft.com/hololens/security-architecture).

## <a name="os-security"></a>Seguridad del sistema operativo
Las actualizaciones se realizan automáticamente (de forma predeterminada), por lo que el HoloLens 2 siempre está actualizado con la versión más reciente de Windows Holographic y las aplicaciones instaladas. Consulte lo siguiente para obtener más información sobre cómo nuestro sistema operativo está diseñado de forma segura:
1. [Separación y aislamiento de estado](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Sistema operativo sin administrador](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Limitación del uso de contraseñas](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Seguridad física
HoloLens 2 memoria flash protegida por el [cifrado de BitLocker](https://docs.microsoft.com/hololens/security-encryption-data-protection). El dispositivo y sus datos locales se pueden flashear sin conexión mediante Advanced [Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) o borrarse de forma remota a través de MDM si se ha implementado como un dispositivo administrado.

## <a name="data-protection"></a>Protección de datos
Las actualizaciones de Windows se ejecutan automáticamente (de forma predeterminada) y la integración [de Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) protege los datos que viajan entre sí y la nube. 

Al implementar HoloLens 2 en clientes externos, [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) garantiza que los datos y los recursos confidenciales de la empresa son independientes y seguros. 

El uso compartido de datos de diagnóstico con Microsoft puede configurarse manualmente mediante MDM o por el usuario durante la configuración automática. Hay dos opciones: Datos de diagnóstico opcionales y Datos de diagnóstico necesarios. Si la configuración de diagnóstico original debe cambiarse más adelante para solucionar problemas, el usuario puede cambiarla en Configuración **-> Privacidad -> Diagnósticos & Comentarios** o el Administrador de TI (MDM) si es un dispositivo administrado. Consulte más información [sobre diagnósticos, comentarios y privacidad en Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Los registros de diagnóstico de dispositivos contienen información de identificación personal (PII), como sobre qué procesos o aplicaciones inicia el usuario durante las operaciones típicas. Cuando varios usuarios comparten un dispositivo HoloLens (por ejemplo, los usuarios inician sesión en el mismo dispositivo con diferentes cuentas de Microsoft Azure Active Directory (Azure AD), los registros de diagnóstico pueden contener información de PII que se aplica a varios usuarios.

 

Hay varios [métodos de recopilación y directivas de retención de datos](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) para recopilar datos de diagnóstico del HoloLens 2.  Para obtener más información sobre cómo Microsoft recopila y usa datos de diagnóstico, vea Declaración de privacidad de [Microsoft - Diagnósticos:](https://privacy.microsoft.com/privacystatement) expandir **Windows** en el menú de navegación izquierdo y **seleccionar Diagnósticos.** Vaya a la **sección Diagnósticos.**
