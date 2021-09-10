---
title: Limitación del uso de contraseñas
description: limitación del uso de contraseñas para HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, limitación del uso de contraseñas, contraseña, contraseña de hololens, inicio de sesión, iniciar sesión, Windows Hello, Hello, administrador de cuentas de Windows, inicio de sesión en FIDO2, FIDO 2, WEBAUTHN, cuenta local, seguridad de hololens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "124429022"
---
# <a name="limiting-password-use"></a>Limitación del uso de contraseñas

La mayoría de los sistemas informáticos actuales usan credenciales de usuario como base para la seguridad, por lo que dependen de contraseñas reutilizables creadas por los usuarios. Esto ha provocado que las contraseñas también se conviertan en la causa más común de infracciones de datos y riesgo de las cuentas. Por ejemplo, las contraseñas se pueden interceptar durante la transmisión o robarse de un servidor (mediante ataques de suplantación de identidad, o phishing, o de difusión de contraseña) y vulnerarse para obtener acceso a una cuenta de usuario.

Para mejorar la seguridad y la protección de las cuentas, HoloLens 2 tiene la capacidad de habilitar credenciales “sin contraseña” seguras y respaldadas por hardware (incluido Windows Hello) para iniciar sesión en el dispositivo y ofrece acceso perfectamente integrado a la nube de Microsoft.

## <a name="signing-in-from-another-device"></a>Iniciar sesión desde otro dispositivo

HoloLens 2 ofrece opciones de inicio de sesión en dispositivos remotos para las cuentas profesionales de Azure Active Directory durante la configuración inicial del dispositivo y el inicio de sesión del usuario para reducir la necesidad de escribir contraseñas complejas y minimizar la necesidad de usar contraseñas como credenciales. Los usuarios y las organizaciones que usan tarjetas inteligentes para la autenticación tienen dificultades a la hora de usar esas credenciales en dispositivos como HoloLens 2 y, con frecuencia, las organizaciones desarrollan sistemas complicados y procesos costosos para solucionar el problema. Para resolver este problema, Azure AD ofrece dos opciones de inicio de sesión sin contraseña en HoloLens 2.

El primer método de autenticación se basa en las nuevas funcionalidades de la aplicación Microsoft Authenticator para proporcionar autenticación basada en claves que habilita una credencial de usuario vinculada a un dispositivo. Una vez que el administrador habilite este proceso en un inquilino, se mostrará un mensaje a los usuarios durante la configuración del dispositivo HoloLens que indica que deben pulsar un número en la aplicación. Los usuarios deben usar el número de la aplicación de autenticación, elegir Aprobar, proporcionar el PIN o una credencial biométrica y completar la autenticación para continuar con la configuración de HoloLens. Esto se describe con más detalle en [inicio de sesión sin contraseña](/azure/active-directory/authentication/howto-authentication-passwordless-phone).

El segundo método es un flujo de código de dispositivo intuitivo para los usuarios que no requiere ninguna infraestructura adicional.  Este comportamiento de inicio de sesión remoto se basa en otro dispositivo de confianza que es compatible con el mecanismo de autenticación preferido de la organización. Cuando se completa se emiten tokens en HoloLens para completar el inicio de sesión o la configuración del dispositivo. Los pasos de este flujo son:

  1. El usuario que realiza los procesos de configuración inicial del dispositivo o de inicio de sesión en OOBE recibe un vínculo "Iniciar sesión desde otro dispositivo" y debe pulsarlo. Comienza una sesión de inicio de sesión remoto.
  1. A continuación, se muestra al usuario una página de sondeo, que contiene un URI corto ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) que apunta al punto de conexión de autenticación de dispositivos del Servicio de token seguro (STS) de Azure AD. El usuario también recibirá un código único que se genera de forma segura en la nube y que tiene una vigencia máxima de 15 minutos. Además de la generación del código, Azure AD también crea una sesión cifrada cuando comienza la solicitud de inicio de sesión remoto del paso anterior y, en conjunto, el URI y el código se usan para aprobar la solicitud de inicio de sesión remoto.
  1. A continuación, el usuario se desplaza al URI del otro dispositivo donde se le pide que escriba el código que se muestra en su dispositivo HoloLens 2.
  1. Una vez que el usuario ha introducido el código, STS de Azure AD muestra una página que señala el dispositivo HoloLens 2 del usuario que desencadenó la solicitud de inicio de sesión remoto y solicitó la generación del código. Se pedirá la confirmación del usuario para evitar ataques de suplantación de identidad (phishing).
  1. Si el usuario decide seguir con el inicio de sesión en la "aplicación" que se muestra, STS de Azure AD le pide sus credenciales. Si la autenticación es correcta, STS de Azure AD actualiza la sesión remota en caché a "aprobada", junto con un código de autorización.
  1. Por último, la página de sondeo del dispositivo HoloLens 2 del usuario recibe una respuesta de autorización de Azure AD y continúa con la validación del código de usuario y el código de autorización almacenado asociado, y genera los tokens de OAuth solicitados para completar la configuración del dispositivo. El token de autenticación creado es válido durante una hora y el token de actualización tiene una vida útil de 90 días.

Los algoritmos de generación y de cifrado de código utilizados en este flujo son compatibles con FIPS. Los dispositivos HoloLens 2 usan TPM para proteger las claves del dispositivo y cifrar los tokens generados después de la autenticación del usuario con claves protegidas por hardware. La información sobre la seguridad de los tokens en HoloLens 2 se comparte en [¿Qué es un token de actualización principal (PRT)?](/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Inicio de sesión en un dispositivo con Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) ofrece opciones sin contraseña integradas en el sistema operativo, lo que permite que los usuarios inicien sesión en el dispositivo con el iris o un PIN. El PIN siempre está disponible como una credencial y es necesario para la configuración del dispositivo, mientras que el iris es opcional y se puede omitir. Los usuarios pueden iniciar sesión en dispositivos HoloLens con su cuenta de Microsoft personal o con la [cuenta profesional de Azure Active Directory *sin* escribir una contraseña](/azure/active-directory/authentication/concept-authentication-passwordless). Este tipo de opciones proporcionan a los usuarios acceso rápido y seguro a una experiencia completa de aplicaciones, datos, sitios web y servicios de Windows. Aquí se detalla la estrategia de Microsoft para las experiencias sin contraseñas.

Cuando se genera una credencial de Windows Hello, se establece una relación de confianza con el proveedor de identidades y se crea un par de claves asimétricas que se usa para la autenticación. Un gesto de Windows Hello (como el iris o el PIN) proporciona entropía para descifrar una clave privada respaldada por el chip del Módulo de plataforma segura (TPM) del dispositivo. Esta clave privada se usa para firmar solicitudes enviadas a un servidor de autenticación y, una vez que se autentica correctamente, concede acceso al usuario al correo electrónico, las imágenes y otras opciones de la cuenta.

Para obtener más información, consulte la infografía siguiente:

  ![Inicio de sesión en Windows Hello.](images/security-hello-sign-in.png)
  
En el gráfico presentado anteriormente, tenga en cuenta que nonce significa "número una vez" y es un número aleatorio o semialeatorio. Una vez configuradas las credenciales biométricas o el PIN de Windows Hello, nunca dejan el dispositivo en el que se aprovisionaron. Aunque se robe el PIN de Windows Hello del usuario, por ejemplo con un ataque de suplantación de identidad (phishing), [este no sirve de nada sin el dispositivo físico del usuario](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password).

Para mayor seguridad, las credenciales de Windows Hello están protegidas por el Módulo de plataforma segura (TPM) para resistir intentos de manipulación. Esto se complementa con protección contra ataques de repetición (hammering) ante varias entradas incorrectas, y protección contra software malintencionado para evitar la exposición. Para obtener más información sobre el inicio de sesión único (SSO), lea esta [introducción a los métodos de SSO](/azure/active-directory/manage-apps/what-is-single-sign-on).

Si la autenticación con el iris produce un error, se utiliza el PIN. Para configurar un nuevo PIN (un autenticador sólido) en el dispositivo, el usuario debe haber ejecutado recientemente [Multifactor Authentication (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) para poder completar el proceso.

## <a name="single-sign-on-with-web-account-manager"></a>Inicio de sesión único con el Administrador de cuentas web

El inicio de sesión único (SSO) permite que los usuarios sin contraseña inicien sesión en el dispositivo con la cuenta personal del usuario o su cuenta profesional o educativa. Con el SSO el usuario recibe autorización automáticamente en todos los servicios y las aplicaciones integrados a través de las [API del Administrador de cuentas web](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

Una vez que se ha agregado una identidad a través de una aplicación, con el consentimiento del usuario puede estar disponible para todas las aplicaciones y todos los servicios mediante la integración en el nivel del sistema. Esto reduce significativamente la carga de inicio de sesión de la aplicación y proporciona a los usuarios una experiencia de identidad sin problemas.

Para obtener más información sobre cómo implementar las API del Administrador de cuentas web, vaya a [Implementación de las API del Administrador de cuentas web](/windows/uwp/security/web-account-manager).

  ![API de seguridad.](images/security-api-img.png)
  
Para los conjuntos de aplicaciones con requisitos de autenticación especializados, el marco del Administrador de cuentas web (WAM) se puede ampliar a los proveedores de identidades personalizadas. Los usuarios pueden descargar el proveedor de identidades personalizadas como una aplicación para la Plataforma universal de Windows (UWP) en Microsoft Store para habilitar el SSO en otras aplicaciones integradas con ese proveedor de identidades.

Para obtener más información sobre la implementación de proveedores de identidades de WAM personalizados, vea [Referencia de la API del proveedor de identidades de WAM personalizadas](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Inicio de sesión en Windows Hello y FIDO2 con WebAuthn

Con HoloLens 2 es posible usar credenciales de usuario sin contraseña (como las claves de seguridad de Windows Hello o FIDO2) para iniciar sesión de forma segura en la web a través de Microsoft Edge y en sitios web que son compatibles con WebAuthn. FIDO2 habilita credenciales de usuario para el uso de dispositivos basados en estándares para autenticarse en servicios en línea.

> [!Note]
> Las especificaciones de [WebAuthn](https://www.w3.org/TR/webauthn/) y FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) se implementan en los servicios. Los metadatos firmados especificados por WebAuthn y FIDO2 proporcionan información (por ejemplo, si el usuario se encontraba presente) y comprueban la autenticación mediante el gesto local.

Igual que con Windows Hello, cuando el usuario crea y registra credenciales de FIDO2, el dispositivo (HoloLens 2 o la clave de seguridad de FIDO2) genera una clave pública y privada en el dispositivo. La clave privada se almacena de forma segura en el dispositivo y solo se puede usar después de que se desbloquee con un gesto local, como una credencial biométrica o un PIN. Cuando se almacena la clave privada, la clave pública se envía al sistema de la cuenta de Microsoft en la nube y se registra con la cuenta de usuario asociada.

Después de iniciar sesión con una cuenta de MSA y Azure AD, el sistema envía una variable de datos o numérica generada al dispositivo HoloLens 2 o FIDO2. El dispositivo o las HoloLens 2 usan la clave privada para firmar la identificación. La identificación firmada y los metadatos se envían al sistema de la cuenta de Microsoft y se contrastan con la clave pública.

Los dispositivos de Windows Hello y FIDO2 implementan credenciales basadas en el dispositivo HoloLens, específicamente el enclave seguro del Módulo de plataforma segura integrado. El enclave TPM almacena la clave privada y requiere una credencial biométrica o un PIN para desbloquearla. De forma similar, una clave de seguridad de FIDO2 es un pequeño dispositivo externo con un enclave seguro integrado que almacena la clave privada y requiere una credencial biométrica o un PIN para desbloquearla.

Ambas opciones ofrecen autenticación en dos fases en un único paso y requieren un dispositivo registrado y una credencial biométrica o un PIN para iniciar sesión correctamente. Para más información, vea a continuación el gráfico y el proceso de autenticación segura con clave de seguridad FIDO2.

### <a name="strong-authentication-with-fido2-security-key"></a>Autenticación segura con clave de seguridad FIDO2

  ![Imagen de FIDO.](images/security-fido2-whfb-smaller.png)

1. El usuario conecta la clave de seguridad FIDO2 a HoloLens 2.
1. Windows detecta la clave de seguridad de FIDO2.
1. HoloLens envía una solicitud de autenticación.
1. Azure AD devuelve nonce.
1. El usuario completa un gesto para desbloquear los almacenes de claves privadas en el enclave seguro de la clave de seguridad.
1. La clave de seguridad de FIDO2 firma nonce con clave privada.
1. La solicitud de token PRT con nonce firmado se envía a Azure AD.
1. Azure AD comprueba la clave de FIDO.
1. Azure AD devuelve PRT y TGT para habilitar el acceso a los recursos.

MSA y Azure AD están entre los primeros miembros de confianza en admitir una autenticación sin contraseña por medio de la implementación de WebAuthn.

Para obtener más información sobre el uso de WebAuthn con aplicaciones o SDK, vaya a [API de WebAuthn para la autenticación sin contraseña en Windows 10](/windows/security/identity-protection/hello-for-business/webauthnapis).

HoloLens 2 admite dispositivos de seguridad FIDO2 implementados para la especificación y el cumplimiento de los requisitos enumerados en [Inicio de sesión sin contraseña de Azure Active Directory: claves de seguridad de FIDO2](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys).

## <a name="local-accounts"></a>Cuentas locales

Es posible configurar una única cuenta local para las implementaciones en modo sin conexión. Las cuentas locales no están habilitadas de forma predeterminada y deben configurarse durante el aprovisionamiento de dispositivos. Deben iniciar sesión con una contraseña y no admiten métodos de autenticación alternativos (como [Windows Hello para empresas](/windows/security/identity-protection/hello-for-business/hello-overview) o [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)).

Puede encontrar más información sobre las cuentas de usuario de HoloLens en [Identidad de HoloLens](hololens-identity.md).

Los administradores de TI establecen si el usuario puede usar una cuenta de MSA para los servicios y la autenticación de la conexión no relacionada con correo electrónico a través de [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Para ver las directivas de configuración de contraseña, las directivas de inactividad y las directivas de pantalla de bloqueo, consulte [Bloqueo de dispositivo](/windows/client-management/mdm/policy-csp-devicelock).
