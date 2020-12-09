---
title: Administrar la identidad e inicio de sesión del usuario para HoloLens
description: Administra la identidad del usuario, la seguridad y el inicio de sesión de HoloLens.
keywords: HoloLens, usuario, cuenta, AAD, ADFS, cuenta de Microsoft, MSA, credenciales, referencia
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
ms.openlocfilehash: 818f6c2be594b1d709acf7daef1d124c6b410ea4
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201364"
---
# Administrar la identidad e inicio de sesión del usuario para HoloLens

> [!NOTE]
> Este artículo es una referencia técnica para profesionales de ti y entusiastas de la tecnología. Si está buscando instrucciones para configurar HoloLens, lea "[configurar hololens (1ª generación)](hololens1-start.md)" o "[configurar hololens 2](hololens2-start.md)".

Al igual que otros dispositivos Windows, HoloLens siempre funciona con un contexto de usuario. Siempre hay una identidad de usuario. HoloLens trata la identidad casi de la misma manera que otros dispositivos de Windows 10. Este artículo es una referencia profunda para la identidad en HoloLens y se centra en el modo en que HoloLens difiere de otros dispositivos Windows 10.

HoloLens admite varios tipos de identidades de usuario. Puede usar una o varias cuentas de usuario para iniciar sesión. Esta es una descripción general de los tipos de identidad y las opciones de autenticación en HoloLens:

| Tipo de identidad | Cuentas por dispositivo | Opciones de autenticación |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Proveedor de credenciales Web de Azure</li><li>Aplicación Azure Authenticator</li><li>Sólo para la biométrica (IRI) &ndash; HoloLens 2 <sup> 1</sup> </li><li>PIN &ndash; opcional para hololens (1ª generación), necesario para hololens 2</li><li>Contraseña</li></ul> |
| [Cuenta de Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | uno | <ul><li>Sólo para la biometría (IRI) de &ndash; HoloLens 2</li><li>PIN &ndash; opcional para hololens (1ª generación), necesario para hololens 2</li><li>Contraseña</li></ul> |
| [Cuenta local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | uno | Contraseña |

Las cuentas conectadas a la nube (AAD y MSA) ofrecen más características porque pueden usar los servicios de Azure.  

> [!NOTE]
> 1-aunque un dispositivo HoloLens 2 puede admitir hasta 64 cuentas de Azure AD, solo 10 de esas cuentas pueden inscribirse en la autenticación de iris. Esto se alinea con otras opciones de autenticación biométricas de Windows Hello para empresas. [Más información aquí.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## Configurar usuarios

La manera más común de configurar un nuevo usuario es durante la configuración rápida (OOBE) de HoloLens. Durante la configuración, HoloLens pide a un usuario que inicie sesión con la cuenta que desea usar en el dispositivo. Esta cuenta puede ser una cuenta de Microsoft o una cuenta de empresa que se haya configurado en Azure. Consulta configurar tu [HoloLens (1. ª gen)](hololens1-start.md) o [hololens 2](hololens2-start.md).

Al igual que Windows en otros dispositivos, iniciar sesión durante la instalación crea un perfil de usuario en el dispositivo. El perfil de usuario almacena las aplicaciones y los datos. La misma cuenta también proporciona un inicio de sesión único para aplicaciones como Edge o Skype mediante las API del administrador de cuentas de Windows.  

Si usa una cuenta de empresa o de organización para iniciar sesión en HoloLens, HoloLens se inscribió en la infraestructura de TI de la organización. Esta inscripción permite que su administrador de ti configure la administración de dispositivos móviles (MDM) para que envíe directivas de grupo a HoloLens.

De forma predeterminada, al igual que en otros dispositivos de Windows 10, tendrás que iniciar sesión de nuevo cuando HoloLens se reinicia o se reanuda desde el modo de espera. Puede usar la aplicación configuración para cambiar este comportamiento o el comportamiento puede controlarse mediante una directiva de grupo.

### Cuentas vinculadas

Como en la versión de escritorio de Windows, puedes vincular las credenciales de cuenta web adicionales a tu cuenta de HoloLens. Esta vinculación facilita el acceso a los recursos en todas las aplicaciones o dentro de ellas (como la tienda) o para combinar el acceso a los recursos personales y del trabajo. Después de conectar una cuenta al dispositivo, puede conceder permiso para usar el dispositivo en las aplicaciones, de modo que no tenga que iniciar sesión en cada aplicación individualmente.

La vinculación de cuentas no separa los datos de usuario creados en el dispositivo, como las imágenes o las descargas.  

### Configuración de la compatibilidad con varios usuarios (solo AAD)

HoloLens admite varios usuarios del mismo inquilino de AAD. Para usar esta característica, debe usar una cuenta que pertenezca a su organización para configurar el dispositivo. Posteriormente, otros usuarios del mismo inquilino pueden iniciar sesión en el dispositivo desde la pantalla de inicio de sesión o pulsando el icono de usuario en el panel de inicio. Solo un usuario puede iniciar sesión a la vez. Cuando un usuario inicia sesión, HoloLens cierra la sesión del usuario anterior. El primer usuario del dispositivo se considera el propietario del dispositivo, excepto en el caso de una Unión a AAD, [Obtenga más información sobre los propietarios del dispositivo](security-adminless-os.md#device-owner).

Todos los usuarios pueden usar las aplicaciones instaladas en el dispositivo. Sin embargo, cada usuario tiene sus propios datos y preferencias de la aplicación. Quitar una aplicación del dispositivo la quita para todos los usuarios.  

Los dispositivos configurados con cuentas de AAD no permiten iniciar sesión en el dispositivo con una cuenta de Microsoft. Todas las cuentas posteriores usadas deben ser cuentas de AAD desde el mismo inquilino que el dispositivo. Aún puede [iniciar sesión con una cuenta de Microsoft para las aplicaciones](hololens-identity.md#setting-up-multi-user-support-aad-only) que lo admitan (como Microsoft Store). Para cambiar el uso de cuentas de AAD a cuentas de Microsoft para iniciar sesión en el dispositivo, debe rehacer [el dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1ª generación)** comenzó a admitir varios usuarios de AAD en la [actualización de Windows 10 de abril de 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) como parte de [Windows Holographic para empresas](hololens-upgrade-enterprise.md).

## Quitar usuarios

Para quitar un usuario del dispositivo, vaya a **configuración**  >  **cuentas**  >  **otras personas**. Esta acción también reclama espacio al quitar todos los datos de la aplicación de ese usuario del dispositivo.  

## Usar el inicio de sesión único en una aplicación

Como desarrollador de aplicaciones, puedes aprovechar las identidades vinculadas en HoloLens con las API del [Administrador de cuentas de Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core), tal como lo harías en otros dispositivos Windows. Algunos ejemplos de código de estas API están disponibles en GitHub: [ejemplo de administración de cuenta web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Cuando la aplicación solicite un token de autenticación, debe controlar las interrupciones de cuenta que se pueden producir, como solicitar el consentimiento del usuario para la información de la cuenta, la autenticación en dos fases, etc.

Si la aplicación requiere un tipo de cuenta específico que no se ha vinculado anteriormente, la aplicación puede solicitar al sistema que solicite al usuario que agregue uno. Esta solicitud desencadena el panel Configuración de la cuenta para que se inicie como un elemento secundario modal de la aplicación. Para las aplicaciones 2D, esta ventana se representa directamente sobre el centro de la aplicación. En el caso de las aplicaciones de Unity, esta solicitud hace que el usuario de la aplicación holográfica represente brevemente la ventana secundaria. Para obtener información sobre cómo personalizar los comandos y acciones de este panel, vea [clase WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## Autenticación empresarial y de otro tipos

Si la aplicación usa otros tipos de autenticación, como NTLM, Basic o Kerberos, puede usar la interfaz de usuario de [credenciales de Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) para recopilar, procesar y almacenar las credenciales del usuario. La experiencia de usuario para recopilar estas credenciales es muy similar a otras interrupciones de cuenta basadas en la nube, y aparece como una aplicación secundaria en la parte superior de la aplicación 2D, o bien detiene brevemente una aplicación de Unity para mostrar la interfaz de usuario.

## API obsoletas

Una de las formas en que el desarrollo para HoloLens difiere del desarrollo para el escritorio es que la API de [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) no es totalmente compatible. Aunque la API devuelve un token si la cuenta principal está en buenas condiciones, las interrupciones como las descritas en este artículo no muestran ninguna interfaz de usuario para el usuario y no pueden autenticar correctamente la cuenta.

## Preguntas frecuentes

### ¿Se admite Windows Hello para empresas en HoloLens (1ª generación)?

Windows Hello para empresas (que admite el uso de un PIN para iniciar sesión) es compatible con HoloLens (1 ª generación). Para permitir el inicio de sesión de PIN de Windows Hello para empresas en HoloLens:

1. El dispositivo HoloLens debe ser [administrado por MDM](hololens-enroll-mdm.md).
1. Debe habilitar Windows Hello para empresas para el dispositivo. ([Consulte instrucciones para Microsoft Intune).](https://docs.microsoft.com/intune/windows-hello)
1. En HoloLens, el usuario puede usar **Settings**  >  **las opciones de inicio de sesión**de configuración  >  **Agregar PIN** para configurar un PIN.

> [!NOTE]
> Los usuarios que inicien sesión con una cuenta de Microsoft también pueden configurar un PIN en **configuración**  >  **Opciones de inicio de sesión**  >  **Agregar PIN**. Este PIN está asociado con [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), en lugar de [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### ¿Cómo se implementa la autenticación biométrica de iris en HoloLens?

HoloLens 2 admite la autenticación de iris. Iris se basa en la tecnología Windows Hello y es compatible con las cuentas Microsoft y Azure Active Directory. Iris se implementa de la misma manera que otras tecnologías de Windows Hello y logra una seguridad biométrica de 1/100 k.

[Aquí](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)puede obtener más información sobre las especificaciones y los requisitos biométricos de Windows Hello. Más información sobre [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) y [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### ¿Cómo afecta el tipo de cuenta al comportamiento de inicio de sesión?

Si aplicas directivas de inicio de sesión, siempre se respeta la directiva. Si no se aplica ninguna directiva para iniciar sesión, estos son los comportamientos predeterminados de cada tipo de cuenta:

- **Azure ad**: solicita autenticación de forma predeterminada y la **configuración** la puede configurar para que dejen de solicitar autenticación.
- **Cuenta de Microsoft**: el comportamiento de bloqueo es diferente y permite el desbloqueo automático, sin embargo, el inicio de sesión sigue siendo necesario en el reinicio.
- **Cuenta local**: pide siempre la autenticación con la forma de una contraseña y no se puede configurar en la **configuración** .

> [!NOTE]
> Actualmente no se admiten los temporizadores de inactividad, lo que significa que la Directiva de **AllowIdleReturnWithoutPassword** solo se respeta cuando el dispositivo entra en modo de espera.

## Recursos adicionales

Obtenga más información sobre la protección y la autenticación de identidades de usuario en [la documentación de seguridad e identidad de Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

Obtenga más información sobre cómo configurar la infraestructura de identidades híbridas con detalle en la [documentación de Azure Hybrid Identity](https://docs.microsoft.com/azure/active-directory/hybrid/).
