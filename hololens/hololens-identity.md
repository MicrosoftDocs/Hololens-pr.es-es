---
title: Administrar la identidad e inicio de sesión del usuario para HoloLens
description: Obtenga información sobre cómo administrar la identidad de usuario, el soporte de varios usuarios, la seguridad, la autenticación empresarial y el inicio de sesión para dispositivos HoloLens.
keywords: HoloLens, usuario, cuenta, AAD, Azure AD, adfs, cuenta de Microsoft, msa, credenciales, referencia
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d9b7bebd9fd326def4ddfc2982bfecb09cb14186
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283281"
---
# Administrar la identidad e inicio de sesión del usuario para HoloLens

> [!NOTE]
> Este artículo es una referencia técnica para profesionales de TI y entusiastas de la tecnología. If you're looking for HoloLens set up instructions, read "[Setting up your HoloLens (1st gen)](hololens1-start.md)" or "[Setting up your HoloLens 2](hololens2-start.md)".

Al igual que otros dispositivos Windows, HoloLens siempre funciona en un contexto de usuario. Siempre hay una identidad de usuario. HoloLens trata la identidad casi de la misma manera que otros dispositivos Windows 10. Este artículo es una referencia en profundidad para la identidad en HoloLens y se centra en la diferencia de HoloLens con respecto a otros dispositivos Windows 10.

HoloLens admite varios tipos de identidades de usuario. Puede usar una o más cuentas de usuario para iniciar sesión. A continuación se ofrece información general sobre los tipos de identidad y las opciones de autenticación en HoloLens:

| Tipo de identidad | Cuentas por dispositivo | Opciones de autenticación |
| --- | --- | --- |
| [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Proveedor de credenciales web de Azure</li><li>Aplicación Azure Authenticator</li><li>Biométrico (Iris) &ndash; HoloLens 2 solo <sup> 1</sup> </li><li>PIN &ndash; opcional para HoloLens (1.ª generación), necesario para HoloLens 2</li><li>Contraseña</li></ul> |
| [Cuenta de Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Solo &ndash; HoloLens 2 biométrico (Iris)</li><li>PIN &ndash; opcional para HoloLens (1.ª generación), necesario para HoloLens 2</li><li>Contraseña</li></ul> |
| [Cuenta local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Contraseña |

Las cuentas conectadas a la nube (Azure AD y MSA) ofrecen más características porque pueden usar los servicios de Azure.  

> [!NOTE]
> 1- Aunque un dispositivo HoloLens 2 puede admitir hasta 64 cuentas de Azure AD, solo 10 de esas cuentas pueden inscribirse en la autenticación de Iris. Esto está alineado con otras [opciones de autenticación biométrica para Windows Hello para empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## Configuración de usuarios

La forma más común de configurar un nuevo usuario es durante la configuración rápida (OOBE) de HoloLens. Durante la configuración, HoloLens pide a un usuario que inicie sesión con la cuenta que quiere usar en el dispositivo. Esta cuenta puede ser una cuenta microsoft de consumidor o una cuenta empresarial que se ha configurado en Azure. Consulta Configuración de [HoloLens (1.ª generación)](hololens1-start.md) o [HoloLens 2.](hololens2-start.md)

Al igual que Windows en otros dispositivos, iniciar sesión durante la configuración crea un perfil de usuario en el dispositivo. El perfil de usuario almacena aplicaciones y datos. La misma cuenta también proporciona el inicio de sesión único para aplicaciones como Edge o Skype mediante las API del Administrador de cuentas de Windows.  

Si usa una cuenta empresarial u organizativa para iniciar sesión en HoloLens, HoloLens se inscribe en la infraestructura de TI de la organización. Esta inscripción permite al administrador de TI configurar la Administración de dispositivos móviles (MDM) para enviar directivas de grupo a HoloLens.

De forma predeterminada, al igual que en otros dispositivos Windows 10, tendrás que volver a iniciar sesión cuando HoloLens reinicie o reanude el modo de espera. Puedes usar la aplicación Configuración para cambiar este comportamiento o el comportamiento puede controlarse mediante una directiva de grupo.

### Cuentas vinculadas

Al igual que en la versión de escritorio de Windows, puede vincular credenciales de cuenta web adicionales a su cuenta de HoloLens. Esta vinculación facilita el acceso a recursos en aplicaciones (como la Tienda) o en aplicaciones (como la Tienda) o combinar el acceso a recursos personales y de trabajo. Después de conectar una cuenta al dispositivo, puedes conceder permiso para usar el dispositivo en aplicaciones para que no tenga que iniciar sesión en cada aplicación individualmente.

La vinculación de cuentas no separa los datos de usuario creados en el dispositivo, como imágenes o descargas.  

### Configuración de la compatibilidad con varios usuarios (solo Azure AD)

HoloLens admite varios usuarios del mismo inquilino de Azure AD. Para usar esta característica, debes usar una cuenta que pertenezca a tu organización para configurar el dispositivo. Posteriormente, otros usuarios del mismo inquilino pueden iniciar sesión en el dispositivo desde la pantalla de inicio de sesión o pulsando el icono de usuario en el panel Inicio. Solo un usuario puede haber iniciado sesión a la vez. Cuando un usuario inicia sesión, HoloLens cierra la sesión del usuario anterior. El primer usuario del dispositivo se considera el propietario del dispositivo, excepto en el caso de la unión a Azure AD, obtenga más [información sobre los propietarios de dispositivos.](security-adminless-os.md#device-owner)

Todos los usuarios pueden usar las aplicaciones instaladas en el dispositivo. Sin embargo, cada usuario tiene sus propios datos y preferencias de aplicación. Al quitar una aplicación del dispositivo, se quita para todos los usuarios.  

Los dispositivos configurados con cuentas de Azure AD no permitirán iniciar sesión en el dispositivo con una cuenta de Microsoft. Todas las cuentas posteriores que se usan deben ser cuentas de Azure AD del mismo inquilino que el dispositivo. Es posible que [aún inicies sesión con una cuenta de Microsoft en aplicaciones](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que la admitan (como Microsoft Store). Para cambiar de usar cuentas de Azure AD a cuentas de Microsoft para iniciar sesión en el dispositivo, debe volver a [actualizar el dispositivo.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1.ª generación)** comenzó a admitir a varios usuarios de Azure AD en la actualización de abril de [2018 de Windows 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) como parte de [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

## Quitar usuarios

Puedes quitar un usuario del dispositivo **** yendo a Cuentas  >  **de configuración**  >  **Otras personas.** Esta acción también reclama espacio quitando todos los datos de la aplicación de ese usuario del dispositivo.  

## Uso del inicio de sesión único en una aplicación

Como desarrollador de aplicaciones, puedes aprovechar las identidades vinculadas en HoloLens mediante las API del Administrador de cuentas de [Windows,](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)tal como lo harías en otros dispositivos Windows. Algunos ejemplos de código para estas API están disponibles en GitHub: [ejemplo de administración de cuentas web.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Cualquier interrupción de la cuenta que pueda producirse, como solicitar el consentimiento del usuario para la información de la cuenta, la autenticación en dos fases, etc., debe controlarse cuando la aplicación solicita un token de autenticación.

Si la aplicación requiere un tipo de cuenta específico que no se haya vinculado anteriormente, la aplicación puede pedir al sistema que pida al usuario que agregue uno. Esta solicitud desencadena el panel de configuración de la cuenta para que se inicie como elemento secundario modal de la aplicación. En el caso de las aplicaciones 2D, esta ventana se representa directamente sobre el centro de la aplicación. Para las aplicaciones de Unity, esta solicitud saca brevemente al usuario de la aplicación holográfica para representar la ventana secundaria. Para obtener información sobre cómo personalizar los comandos y acciones en este panel, vea [Clase WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Autenticación empresarial y de otro tipo

Si la aplicación usa otros tipos de autenticación, como NTLM, Basic o Kerberos, puedes usar la interfaz de usuario de Credenciales de [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) para recopilar, procesar y almacenar las credenciales del usuario. La experiencia del usuario para recopilar estas credenciales es muy similar a otras interrupciones de la cuenta controlada por la nube y aparece como una aplicación secundaria encima de la aplicación 2D o suspende brevemente una aplicación de Unity para mostrar la interfaz de usuario.

## API en desuso

Una forma en que el desarrollo de HoloLens difiere del desarrollo para escritorio es que la API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) no es totalmente compatible. Aunque la API devuelve un token si la cuenta principal está en buen estado, las interrupciones como las descritas en este artículo no muestran ninguna interfaz de usuario para el usuario y no autentican correctamente la cuenta.

## Preguntas frecuentes

### ¿Windows Hello para empresas es compatible con HoloLens (1.ª generación)?

Windows Hello para empresas (que admite el uso de un PIN para iniciar sesión) es compatible con HoloLens (1.ª generación). Para permitir el inicio de sesión de PIN de Windows Hello para empresas en HoloLens:

1. El dispositivo HoloLens debe ser [administrado por MDM.](hololens-enroll-mdm.md)
1. Debes habilitar Windows Hello para empresas para el dispositivo. ([Vea las instrucciones de Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. En HoloLens, el usuario **** puede usar opciones de configuración de inicio de sesión  >  ****  >  **Agregar PIN** para configurar un PIN.

> [!NOTE]
> Los usuarios que inician sesión con una cuenta **** de Microsoft también pueden configurar un PIN en Opciones de inicio de sesión  >  **de configuración Agregar**  >  **PIN.** Este PIN está asociado a [Windows Hello, en](https://support.microsoft.com/help/17215/windows-10-what-is-hello)lugar de [a Windows Hello para empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### ¿Cómo se implementa la autenticación biométrica de Iris en HoloLens 2?

HoloLens 2 admite la autenticación de Iris. Iris se basa en la tecnología Windows Hello y es compatible con azure Active Directory y cuentas de Microsoft. Iris se implementa de la misma manera que otras tecnologías de Windows Hello y logra una seguridad biométrica de 1/100 K.

Consulta las [especificaciones y los requisitos biométricos de Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obtener más información. Obtén más información [sobre Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) y Windows Hello para [empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### ¿Cómo afecta el tipo de cuenta al comportamiento de inicio de sesión?

Si aplicas directivas de inicio de sesión, siempre se respeta la directiva. Si no se aplica ninguna directiva para el inicio de sesión, estos son los comportamientos predeterminados para cada tipo de cuenta:

- **Azure AD:** pide autenticación de forma predeterminada y la configuración puede configurarla **para** que ya no solicite la autenticación.
- **Cuenta de Microsoft:** el comportamiento de bloqueo es diferente, lo que permite el desbloqueo automático, pero la autenticación de inicio de sesión sigue siendo necesaria en el reinicio.
- **Cuenta local:** siempre pide autenticación en forma de contraseña, no configurable en **Configuración**

> [!NOTE]
> Actualmente no se admiten temporizadores de inactividad, lo que significa que la directiva **AllowIdleReturnWithoutPassword** solo se respeta cuando el dispositivo entra en StandBy.

## Recursos adicionales

Lee mucho más sobre la autenticación y la protección de identidades de usuario en la documentación de seguridad e [identidad de Windows 10.](https://docs.microsoft.com/windows/security/identity-protection/)

Obtenga más información sobre cómo configurar la infraestructura de identidad híbrida a fondo en [la documentación de identidad híbrida de Azure.](https://docs.microsoft.com/azure/active-directory/hybrid/)
