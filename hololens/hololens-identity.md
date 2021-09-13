---
title: Administración de la identidad del usuario y el inicio de sesión HoloLens
description: Aprenda a administrar la identidad de usuario, la compatibilidad con varios usuarios, la seguridad, la autenticación empresarial y el inicio de sesión para HoloLens dispositivos.
keywords: HoloLens, usuario, cuenta, AAD, Azure AD, adfs, cuenta microsoft, msa, credenciales, referencia
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: qianw211
ms.author: v-qianwen
ms.date: 8/13/2021
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c2fd7c8ee82fbf70b9eaa2b5eee1d73e1235d8b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033257"
---
# <a name="manage-user-identity-and-login-for-hololens"></a>Administración de la identidad del usuario y el inicio de sesión HoloLens

> [!NOTE]
> Este artículo es una referencia técnica para profesionales de TI y profesionales de la tecnología. Si busca instrucciones de configuración HoloLens, lea " Setting[up your HoloLens (1st gen)](hololens1-start.md)" o "[Setting up your HoloLens 2](hololens2-start.md)".

## <a name="lets-talk-about-setting-up-user-identity-for-hololens-2"></a>Vamos a hablar sobre cómo configurar la identidad de usuario para HoloLens 2

Al igual que Windows dispositivos de HoloLens, siempre funciona en un contexto de usuario. Siempre hay una identidad de usuario. HoloLens trata la identidad de casi la misma manera que un Windows 10 dispositivo. Al iniciar sesión durante la instalación, se crea un perfil de usuario en HoloLens que almacena aplicaciones y datos. La misma cuenta también proporciona inicio de sesión único para aplicaciones, como Edge o Dynamics 365 Remote Assist, mediante las API Windows Account Manager. 

HoloLens admite varios tipos de identidades de usuario. Puede elegir cualquiera de estos tres tipos de cuenta, pero se recomienda encarecidamente Azure AD, ya que es mejor para administrar dispositivos. Solo Azure AD admiten varios usuarios. 

| Tipo de identidad | Cuentas por dispositivo | Opciones de autenticación |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Proveedor de credenciales web de Azure</li><li>Azure Authenticator App</li><li>Biométrica (Iris) &ndash; HoloLens 2<sup>solo 2</sup> </li><li>Clave de seguridad FIDO2</li><li>PIN &ndash; opcional para HoloLens (1.ª generación), necesario para HoloLens 2</li><li>Contraseña</li></ul> |
| [Cuenta de Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Solo datos biométricos (Iris) &ndash; HoloLens 2 datos</li><li>PIN &ndash; opcional para HoloLens (1.ª generación), necesario para HoloLens 2</li><li>Contraseña</li></ul> |
| [Cuenta local](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Contraseña |

Las cuentas conectadas a la nube (Azure AD y MSA) ofrecen más características porque pueden usar servicios de Azure.  
> [!IMPORTANT]
> 1 - Azure AD Premium no es necesario iniciar sesión en el dispositivo. Sin embargo, es necesario para otras características de una implementación basada en la nube táctil, como la inscripción automática y Autopilot.

> [!NOTE]
> 2 - Aunque un dispositivo HoloLens 2 puede admitir hasta 64 Azure AD, solo 31 de esas cuentas pueden inscribirse en la autenticación iris. Esto se alinea con otras opciones [de autenticación biométrica para Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

> [!IMPORTANT]
> 3 - Una cuenta local solo se puede configurar en un dispositivo a través de un paquete de aprovisionamiento durante la [OOBE,](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)no se puede agregar más adelante en la aplicación de configuración. Si desea usar una cuenta local en un dispositivo que ya está configurado, deberá volver a actualizar o restablecer [el dispositivo.](hololens-recovery.md)

## <a name="setting-up-users"></a>Configuración de usuarios

Hay dos maneras de configurar un nuevo usuario en el HoloLens. La forma más común es durante la HoloLens rápida (OOBE). Si usa Azure Active Directory, [otros usuarios pueden iniciar sesión](#setting-up-multi-user-support-azure-ad-only) después de la OOBE con sus Azure AD credenciales. HoloLens dispositivos configurados inicialmente con una cuenta local o MSA durante la OOBE no admitirán varios usuarios. Consulte Configuración de la [HoloLens (1.ª generación)](hololens1-start.md) [o HoloLens 2](hololens2-start.md).

Si usa una cuenta empresarial u organizativa para iniciar sesión en HoloLens, HoloLens se inscribe en la infraestructura de TI de la organización. Esta inscripción permite al administrador de TI configurar Mobile Administración de dispositivos (MDM) para enviar directivas de grupo a su HoloLens.

Al Windows en otros dispositivos, al iniciar sesión durante la instalación se crea un perfil de usuario en el dispositivo. El perfil de usuario almacena aplicaciones y datos. La misma cuenta también proporciona inicio de sesión único para aplicaciones, como Edge o Microsoft Store, mediante las API Windows Account Manager.

De forma predeterminada, como en Windows 10 dispositivos, tendrá que volver a iniciar sesión cuando HoloLens se reinicie o se reanude desde el modo de espera. Puede usar la aplicación Configuración para cambiar este comportamiento o el comportamiento se puede controlar mediante la directiva de grupo.

### <a name="linked-accounts"></a>Cuentas vinculadas

Como en la versión de escritorio de Windows, puede vincular otras credenciales de cuenta web a su HoloLens web. Este tipo de vinculación facilita el acceso a los recursos a través de aplicaciones (como store) o a recursos personales y de trabajo. Después de conectar una cuenta al dispositivo, puede conceder permiso para usar el dispositivo a las aplicaciones para que no tenga que iniciar sesión en cada aplicación individualmente.

La vinculación de cuentas no separa los datos de usuario creados en el dispositivo, como imágenes o descargas.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Configuración de la compatibilidad con varios usuarios (solo Azure AD)

HoloLens admite varios usuarios del mismo Azure AD inquilino. Para usar esta característica, debe usar una cuenta que pertenezca a su organización para configurar el dispositivo. Posteriormente, otros usuarios del mismo inquilino pueden iniciar sesión en el dispositivo desde la pantalla de inicio de sesión o pulsando el icono de usuario en el panel Inicio. Solo un usuario puede haber iniciado sesión a la vez. Cuando un usuario inicia sesión, HoloLens cierra la sesión del usuario anterior. 

>[!IMPORTANT]
> El primer usuario del dispositivo se considera el propietario del dispositivo, excepto en el caso de Azure AD Join, obtenga [más información sobre los propietarios de dispositivos.](security-adminless-os.md#device-owner)

Todos los usuarios pueden usar las aplicaciones instaladas en el dispositivo. Sin embargo, cada usuario tiene sus propios datos y preferencias de aplicación. Al quitar una aplicación del dispositivo, se quita para todos los usuarios.  

Los dispositivos configurados Azure AD cuentas no permitirán iniciar sesión en el dispositivo con una cuenta Microsoft. Todas las cuentas posteriores usadas deben Azure AD cuentas del mismo inquilino que el dispositivo. Todavía puede iniciar [sesión con una cuenta Microsoft para las aplicaciones](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) que la admiten (por ejemplo, Microsoft Store). Para cambiar de usar Azure AD a cuentas Microsoft para iniciar sesión en el dispositivo, debe [volver a actualizar el dispositivo](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1.ª generación)** comenzó a admitir varios usuarios Azure AD en la actualización de abril de [2018](/windows/mixed-reality/release-notes-april-2018) de Windows 10 como [parte de Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-are-listed-on-sign-in-screen"></a>Varios usuarios aparecen en la pantalla de inicio de sesión

Anteriormente, la pantalla de inicio de sesión mostraba solo el usuario que ha iniciado sesión más recientemente y un punto de entrada "Otro usuario". Hemos recibido comentarios de los clientes que no son suficientes si varios usuarios han iniciado sesión en el dispositivo. Todavía tenían que volver a escribir su nombre de usuario, etc.

Introducido en [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)al  seleccionar Otro usuario que se encuentra a la derecha del campo de entrada del PIN, la pantalla inicio de sesión mostrará varios usuarios con que han iniciado sesión previamente en el dispositivo. Esto permite a los usuarios seleccionar su perfil de usuario y, a continuación, iniciar sesión con sus Windows Hello credenciales. También se puede agregar un nuevo usuario al dispositivo desde esta página **de otros** usuarios mediante el **botón Agregar** cuenta.

Cuando se encuentra **en el menú** Otros usuarios, el botón Otros **usuarios** mostrará el último usuario que ha iniciado sesión en el dispositivo. Seleccione este botón para volver a la pantalla de inicio de sesión de este usuario.

![Pantalla de inicio de sesión predeterminada.](./images/multiusers1.jpg)

<br>

![Pantalla de inicio de sesión de otros usuarios.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Eliminación de usuarios

Puede quitar un usuario del dispositivo si va a Configuración  >  **Cuentas**  >  **de otras personas.** Esta acción también reclama espacio quitando todos los datos de aplicación de ese usuario del dispositivo.  

## <a name="using-single-sign-on-within-an-app"></a>Uso del inicio de sesión único dentro de una aplicación

Como desarrollador de aplicaciones, puede aprovechar las identidades vinculadas en HoloLens mediante las API de administrador de cuentas de [Windows,](/uwp/api/Windows.Security.Authentication.Web.Core)como haría en otros dispositivos Windows. Algunos ejemplos de código para estas API están disponibles en GitHub: [Ejemplo de administración de cuentas web](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Cualquier interrupción de la cuenta que pueda producirse, como solicitar el consentimiento del usuario para la información de la cuenta, la autenticación en dos fases, etc., debe controlarse cuando la aplicación solicita un token de autenticación.

Si la aplicación requiere un tipo de cuenta específico que no se ha vinculado anteriormente, la aplicación puede pedir al sistema que solicite al usuario que agregue uno. Esta solicitud desencadena el panel de configuración de la cuenta para iniciarse como elemento secundario modal de la aplicación. En el caso de las aplicaciones 2D, esta ventana se representa directamente sobre el centro de la aplicación. En el caso de las aplicaciones de Unity, esta solicitud quita brevemente al usuario de la aplicación holográfica para representar la ventana secundaria. Para obtener información sobre cómo personalizar los comandos y las acciones en este panel, vea [WebAccountCommand (Clase).](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Enterprise y otra autenticación

Si la aplicación usa otros tipos de autenticación, como NTLM, Basic o Kerberos, puede usar Windows [Credential UI](/uwp/api/Windows.Security.Credentials.UI) para recopilar, procesar y almacenar las credenciales del usuario. La experiencia del usuario para recopilar estas credenciales es similar a otras interrupciones de cuentas controladas por la nube y aparece como una aplicación secundaria encima de la aplicación 2D o suspende brevemente una aplicación de Unity para mostrar la interfaz de usuario.

## <a name="deprecated-apis"></a>Interfaces API desusadas

Una manera en la que el desarrollo para HoloLens difiere del desarrollo para Desktop es que la API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) no es totalmente compatible. Aunque la API devuelve un token si la cuenta principal está en buen estado, las interrupciones como las descritas en este artículo no muestran ninguna interfaz de usuario para el usuario y no autentican correctamente la cuenta.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>¿Windows Hello para empresas se admite en HoloLens (1.ª generación)?

Windows Hello para empresas (que admite el uso de un PIN para iniciar sesión) es compatible con HoloLens (1.ª generación). Para permitir Windows Hello inicio de sesión del PIN de empresa en HoloLens:

1. El HoloLens dispositivo debe [administrarse mediante MDM](hololens-enroll-mdm.md).
1. Debe habilitar Windows Hello for Business para el dispositivo. ([Vea las instrucciones para Microsoft Intune.](/intune/windows-hello))
1. En HoloLens, el usuario puede usar Configuración opciones de inicio de sesión  >    >  **Agregar PIN** para configurar un PIN.

> [!NOTE]
> Los usuarios que inician sesión con una cuenta Microsoft también pueden configurar un PIN en Configuración opciones de inicio de sesión  >    >  **Agregar PIN.** Este PIN está asociado a [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), en lugar [de Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>¿Cómo se implementa la autenticación biométrica de Iris en HoloLens 2?

HoloLens 2 admite la autenticación iris. Iris se basa en Windows Hello tecnología y es compatible con el uso de cuentas Azure Active Directory y Microsoft. Iris se implementa de la misma manera que otras tecnologías de Windows Hello y logra una seguridad [biométrica de 1/100 000](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello).

Consulte los [requisitos biométricos y las especificaciones Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) para obtener más información. Obtenga más información [sobre Windows Hello](/windows-hardware/design/device-experiences/windows-hello) y Windows Hello [for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="where-is-iris-biometric-information-stored"></a>¿Dónde se almacena la información biométrica de Iris?

La información biométrica de Iris se almacena localmente en cada HoloLens por [Windows Hello especificaciones .](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored) No se comparte y está protegido por dos capas de cifrado. No es accesible para otros usuarios, ni siquiera para un administrador, porque no hay ninguna cuenta de administrador en un HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>¿Tengo que usar la autenticación iris?
No, puede omitir este paso durante la instalación. 

![Configure Iris.](./images/setup-iris.png)

HoloLens 2 proporciona muchas opciones diferentes para la autenticación, incluidas las claves de seguridad FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>¿Se puede quitar la información de Iris del HoloLens?
Sí, puede quitarlo manualmente en Configuración.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>¿Cómo afecta el tipo de cuenta al comportamiento de inicio de sesión?

Si aplica directivas para el inicio de sesión, siempre se respeta la directiva. Si no se aplica ninguna directiva para el inicio de sesión, estos son los comportamientos predeterminados para cada tipo de cuenta:

- **Azure AD:** solicita autenticación de forma predeterminada y se puede configurar **Configuración** para que ya no solicite autenticación.
- **Cuenta Microsoft:** el comportamiento del bloqueo es diferente, lo que permite el desbloqueo automático, pero la autenticación de inicio de sesión sigue siendo necesaria en el reinicio.
- **Cuenta local:** siempre solicita autenticación en forma de contraseña, no configurable en **Configuración**

> [!NOTE]
> Actualmente no se admiten temporizadores de inactividad, lo que significa que la directiva **AllowIdleReturnWithoutPassword** solo se respeta cuando el dispositivo entra en StandBy.

## <a name="additional-resources"></a>Recursos adicionales

Obtenga mucho más información sobre la autenticación y la protección de identidades de usuario en [Windows 10 de seguridad e identidad.](/windows/security/identity-protection/)

Obtenga más información sobre cómo configurar la infraestructura de identidad híbrida en la documentación [de identidad híbrida de Azure.](/azure/active-directory/hybrid/)