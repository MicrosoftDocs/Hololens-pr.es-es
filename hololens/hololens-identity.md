---
title: Administración de la identidad y el inicio de sesión del usuario para HoloLens
description: Aprenda a administrar la identidad de usuario, la compatibilidad con varios usuarios, la seguridad, la autenticación empresarial y el inicio de sesión para dispositivos HoloLens.
keywords: HoloLens, usuario, cuenta, AAD, Azure AD, adfs, cuenta microsoft, msa, credenciales, referencia
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
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924424"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Administración de la identidad y el inicio de sesión del usuario para HoloLens

> [!NOTE]
> Este artículo es una referencia técnica para profesionales de TI y profesionales de la tecnología. Si busca instrucciones de configuración de HoloLens, lea "[Setting up your HoloLens (1st gen)](hololens1-start.md)" o "[Setting up your HoloLens 2](hololens2-start.md)".

Al igual que otros dispositivos Windows, HoloLens siempre funciona en un contexto de usuario. Siempre hay una identidad de usuario. HoloLens trata la identidad casi de la misma manera que otras Windows 10 dispositivos. Este artículo es una referencia en profundidad para la identidad en HoloLens y se centra en la diferencia de HoloLens con respecto a otros Windows 10 dispositivos.

HoloLens admite varios tipos de identidades de usuario. Puede usar una o varias cuentas de usuario para iniciar sesión. Esta es una introducción a los tipos de identidad y las opciones de autenticación en HoloLens:

| Tipo de identidad | Cuentas por dispositivo | Opciones de autenticación |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Proveedor de credenciales web de Azure</li><li>Aplicación Azure Authenticator</li><li>Biométrica (Iris) &ndash; HoloLens 2<sup>solo 2</sup> </li><li>PIN &ndash; opcional para HoloLens (1.ª generación), necesario para HoloLens 2</li><li>Contraseña</li></ul> |
| [Cuenta Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Solo datos &ndash; biométricos (Iris) HoloLens 2 datos</li><li>PIN &ndash; opcional para HoloLens (1.ª generación), necesario para HoloLens 2</li><li>Contraseña</li></ul> |
| [Cuenta local](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Contraseña |

Las cuentas conectadas a la nube (Azure AD y MSA) ofrecen más características porque pueden usar servicios de Azure.  
> [!IMPORTANT]
> 1 - Azure AD Premium no es necesario iniciar sesión en el dispositivo. Sin embargo, es necesario para otras características de una implementación basada en la nube táctil, como la inscripción automática y Autopilot.

> [!NOTE]
> 2 - Aunque un dispositivo HoloLens 2 puede admitir hasta 64 cuentas de Azure AD, solo 10 de esas cuentas pueden inscribirse en la autenticación de Iris. Esto se alinea con otras opciones [de autenticación biométrica para Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

## <a name="setting-up-users"></a>Configuración de usuarios

La manera más común de configurar un nuevo usuario es durante la experiencia rápida (OOBE) de HoloLens. Durante la instalación, HoloLens solicita a un usuario que inicie sesión con la cuenta que quiere usar en el dispositivo. Esta cuenta puede ser una cuenta Microsoft de consumidor o una cuenta empresarial que se ha configurado en Azure. Consulte Configuración de [HoloLens (1.ª generación)](hololens1-start.md) [o HoloLens 2](hololens2-start.md).

Al igual que Windows en otros dispositivos, al iniciar sesión durante la instalación se crea un perfil de usuario en el dispositivo. El perfil de usuario almacena aplicaciones y datos. La misma cuenta también proporciona inicio de sesión único para aplicaciones, como Edge o Microsoft Store, mediante las API del Administrador de cuentas de Windows.  

Si usa una cuenta empresarial u organizativa para iniciar sesión en HoloLens, HoloLens se inscribe en la infraestructura de TI de la organización. Esta inscripción permite al administrador de TI configurar Mobile Administración de dispositivos (MDM) para enviar directivas de grupo a HoloLens.

De forma predeterminada, como en Windows 10 dispositivos, tendrá que volver a iniciar sesión cuando HoloLens se reinicie o se reanude desde el modo de espera. Puede usar la aplicación Configuración para cambiar este comportamiento o el comportamiento se puede controlar mediante una directiva de grupo.

### <a name="linked-accounts"></a>Cuentas vinculadas

Al igual que en la versión de escritorio de Windows, puede vincular credenciales de cuenta web adicionales a su cuenta de HoloLens. Esta vinculación facilita el acceso a los recursos a través de aplicaciones (como store) o a recursos personales y de trabajo. Después de conectar una cuenta al dispositivo, puede conceder permiso para usar el dispositivo a las aplicaciones para que no tenga que iniciar sesión en cada aplicación individualmente.

La vinculación de cuentas no separa los datos de usuario creados en el dispositivo, como imágenes o descargas.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configuración de la compatibilidad con varios usuarios (solo Azure AD)

HoloLens admite varios usuarios del mismo Azure AD inquilino. Para usar esta característica, debe usar una cuenta que pertenezca a su organización para configurar el dispositivo. Posteriormente, otros usuarios del mismo inquilino pueden iniciar sesión en el dispositivo desde la pantalla de inicio de sesión o pulsando el icono del usuario en el panel Inicio. Solo un usuario puede haber iniciado sesión a la vez. Cuando un usuario inicia sesión, HoloLens cierra la sesión del usuario anterior. El primer usuario del dispositivo se considera el propietario del dispositivo, excepto en el caso de Azure AD Join, obtenga más [información sobre los propietarios de dispositivos.](security-adminless-os.md#device-owner)

Todos los usuarios pueden usar las aplicaciones instaladas en el dispositivo. Sin embargo, cada usuario tiene sus propios datos y preferencias de aplicación. Al quitar una aplicación del dispositivo, se quita para todos los usuarios.  

Los dispositivos configurados Azure AD cuentas no permitirán iniciar sesión en el dispositivo con una cuenta Microsoft. Todas las cuentas posteriores usadas deben Azure AD cuentas del mismo inquilino que el dispositivo. Todavía puede iniciar [sesión con una cuenta Microsoft en las aplicaciones](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que la admiten (por ejemplo, Microsoft Store). Para cambiar de usar Azure AD a cuentas Microsoft para iniciar sesión en el dispositivo, debe [volver a actualizar el dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1.ª generación)** comenzó a [](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) admitir varios Azure AD en el Actualización de abril de 2018 de Windows 10 como parte [de Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Varios usuarios enumerados en la pantalla de inicio de sesión

Anteriormente, en la pantalla Inicio de sesión solo se mostraba el usuario que ha iniciado sesión más recientemente, así como un punto de entrada "Otro usuario". Hemos recibido comentarios de los clientes que no son suficientes si varios usuarios han iniciado sesión en el dispositivo. Todavía tenían que volver a escribir su nombre de usuario, etc.

Introducido en [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)al seleccionar Otro usuario que se encuentra a la derecha del campo de entrada del PIN, la pantalla Iniciar sesión mostrará varios usuarios con que han iniciado sesión previamente en el dispositivo.  Esto permite a los usuarios seleccionar su perfil de usuario y, a continuación, iniciar sesión con sus Windows Hello credenciales. También se puede agregar un nuevo usuario al dispositivo desde esta página Otros usuarios mediante el **botón Agregar** cuenta.

Cuando se encuentra en el menú Otros usuarios, el botón Otros usuarios mostrará el último usuario que ha iniciado sesión en el dispositivo. Seleccione este botón para volver a la pantalla Inicio de sesión de este usuario.

![Pantalla de inicio de sesión predeterminada](./images/multiusers1.jpg)

<br>

![Pantalla de inicio de sesión de otros usuarios](./images/multiusers2.jpg)

## <a name="removing-users"></a>Eliminación de usuarios

Para quitar un usuario del dispositivo, vaya a Cuentas **de**  >  **configuración**  >  **Otras personas.** Esta acción también reclama espacio quitando todos los datos de la aplicación de ese usuario del dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Uso del inicio de sesión único dentro de una aplicación

Como desarrollador de aplicaciones, puede aprovechar las identidades vinculadas en HoloLens mediante las API del Administrador de cuentas de [Windows,](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)como haría en otros dispositivos Windows. Algunos ejemplos de código para estas API están disponibles en GitHub: [Ejemplo de administración de cuentas web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Cualquier interrupción de la cuenta que pueda producirse, como solicitar el consentimiento del usuario para la información de la cuenta, la autenticación en dos fases, etc., debe controlarse cuando la aplicación solicite un token de autenticación.

Si la aplicación requiere un tipo de cuenta específico que no se ha vinculado anteriormente, la aplicación puede pedir al sistema que solicite al usuario que agregue uno. Esta solicitud desencadena el panel de configuración de la cuenta para iniciarse como elemento secundario modal de la aplicación. En el caso de las aplicaciones 2D, esta ventana se representa directamente sobre el centro de la aplicación. En el caso de las aplicaciones de Unity, esta solicitud quita brevemente al usuario de la aplicación holográfica para representar la ventana secundaria. Para obtener información sobre cómo personalizar los comandos y las acciones en este panel, vea [WebAccountCommand (Clase).](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Enterprise y otra autenticación

Si la aplicación usa otros tipos de autenticación, como NTLM, Basic o Kerberos, puede usar la interfaz de usuario de credenciales de [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) para recopilar, procesar y almacenar las credenciales del usuario. La experiencia del usuario para recopilar estas credenciales es muy similar a otras interrupciones de cuentas controladas por la nube y aparece como una aplicación secundaria encima de la aplicación 2D o suspende brevemente una aplicación de Unity para mostrar la interfaz de usuario.

## <a name="deprecated-apis"></a>Interfaces API desusadas

Una manera en la que el desarrollo para HoloLens difiere del desarrollo para Desktop es que la API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) no es totalmente compatible. Aunque la API devuelve un token si la cuenta principal está en buen estado, las interrupciones como las descritas en este artículo no muestran ninguna interfaz de usuario para el usuario y no autentican correctamente la cuenta.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>¿Windows Hello para empresas se admite en HoloLens (1.ª generación)?

Windows Hello para empresas (que admite el uso de un PIN para iniciar sesión) es compatible con HoloLens (1.ª generación). Para permitir Windows Hello para empresas inicio de sesión de PIN en HoloLens:

1. Mdm debe administrar el [](hololens-enroll-mdm.md)dispositivo HoloLens.
1. Debe habilitar la Windows Hello para empresas para el dispositivo. ([Vea las instrucciones para Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. En HoloLens, el usuario puede usar Opciones de inicio de sesión de configuración  >    >  **Agregar PIN** para configurar un PIN.

> [!NOTE]
> Los usuarios que inician sesión con una cuenta Microsoft también pueden configurar un PIN en Configuración Opciones de inicio de  >  **sesión Agregar**  >  **PIN.** Este PIN está asociado a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), en lugar de [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>¿Cómo se implementa la autenticación biométrica de Iris en HoloLens 2?

HoloLens 2 admite la autenticación iris. Iris se basa en Windows Hello tecnología y se admite para su uso tanto en Azure Active Directory como en las cuentas Microsoft. Iris se implementa de la misma manera que otras tecnologías de Windows Hello y logra una seguridad biométrica de 1/100 000.

Consulte los [requisitos biométricos y las especificaciones Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obtener más información. Obtenga más información [sobre Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) y [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>¿Cómo afecta el tipo de cuenta al comportamiento de inicio de sesión?

Si aplica directivas para el inicio de sesión, siempre se respeta la directiva. Si no se aplica ninguna directiva para el inicio de sesión, estos son los comportamientos predeterminados para cada tipo de cuenta:

- **Azure AD:** solicita autenticación de forma predeterminada y se puede configurar mediante **Configuración** para que ya no solicite autenticación.
- **Cuenta Microsoft:** el comportamiento de bloqueo es diferente, lo que permite el desbloqueo automático, pero la autenticación de inicio de sesión sigue siendo necesaria en el reinicio.
- **Cuenta local:** siempre solicita autenticación en forma de contraseña, no configurable en **Configuración**

> [!NOTE]
> Actualmente no se admiten temporizadores de inactividad, lo que significa que la directiva **AllowIdleReturnWithoutPassword** solo se respeta cuando el dispositivo entra en StandBy.

## <a name="additional-resources"></a>Recursos adicionales

Obtenga mucho más información sobre la autenticación y la protección de identidades de usuario [en Windows 10 de seguridad e identidad.](https://docs.microsoft.com/windows/security/identity-protection/)

Obtenga más información sobre cómo configurar la infraestructura de identidad híbrida a fondo en [la documentación de identidad híbrida de Azure](https://docs.microsoft.com/azure/active-directory/hybrid/).
