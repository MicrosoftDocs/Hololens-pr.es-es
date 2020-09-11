---
title: Limitar el uso de contraseñas
description: Limitar el uso de contraseñas en holoLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, limitar el uso de la contraseña, contraseña, contraseña de hololens, información de inicio de sesión, iniciar sesión, Windows Hello, Hello, administrador de cuentas de Windows, inicio de sesión en FIDO2, FIDO 2, WEBAUTHN, cuenta local, seguridad de hololens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d577bc23089650e47159a8a77004a984059b095e
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009518"
---
# Limitar el uso de contraseñas

La mayoría de los sistemas informáticos usan credenciales de usuario como base para la seguridad, por lo que dependen de contraseñas reutilizables, creadas por los usuarios. Esto ha tenido como resultado que las contraseñas también se conviertan en la causa más común de compromiso de las cuentas y de infracciones de datos. Por ejemplo, las contraseñas se pueden interceptar durante la transmisión o robarse de un servidor (mediante ataques de suplantación de identidad, o phishing, o por rociado de contraseña) y vulnerarse para obtener acceso a una cuenta de usuario.

Para mejorar la seguridad y la protección de las cuentas, HoloLens 2 tiene la capacidad de habilitar credenciales “sin contraseña” seguras y respaldadas por hardware (incluido Windows Hello) para iniciar sesión, que ofrecen acceso perfectamente integrado a la nube de Microsoft. 

## Inicio de sesión desde otro dispositivo

HoloLens 2 ofrece opciones de inicio de sesión de dispositivo remoto para las cuentas de trabajo de Azure Active Directory durante la configuración inicial del dispositivo y del inicio de sesión del usuario para reducir la necesidad de escribir contraseñas complejas y minimizar la necesidad de usar contraseñas como credenciales. Los usuarios y las organizaciones que usan tarjetas inteligentes para la autenticación tienen dificultades a la hora de usar esas credenciales en dispositivos como HoloLens 2 y, por lo general, las organizaciones desarrollan sistemas complicados y procesos costosos para solucionar el problema. Para resolver este problema, Azure AD ofrece dos opciones de inicio de sesión sin contraseña en HoloLens 2. 

El primer método de autenticación se basa en las nuevas capacidades de la aplicación Microsoft Authenticator que proporciona autenticación basada en clave que habilita una credencial de usuario vinculada a un dispositivo. Una vez que el administrador habilite este proceso para un espacio empresarial, se mostrará un mensaje a los usuarios durante la configuración del dispositivo HoloLens que indica que deben pulsar un número en la aplicación. Los usuarios deben usar el mismo número que el número de la aplicación de autenticación, elegir aprobar, proporcionar el PIN o una credencial biométrica y completar la autenticación para que la configuración de HoloLens continúe. Este proceso se describe con mayor detalle en [inicio de sesión sin contraseña](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone).

El segundo método es un flujo de código de dispositivo intuitivo para los usuarios que no requiere ninguna infraestructura adicional.  Este comportamiento de inicio de sesión remoto se basa en otro dispositivo de confianza que es compatible con el mecanismo de autenticación preferido de la organización. Cuando se completa se emiten tokens en HoloLens para realizar el inicio de sesión o la configuración del dispositivo. Los pasos de este flujo son:

  1.    Se presenta para que lo pulse un vínculo de inicio de sesión desde otro dispositivo al usuario que realiza la configuración inicial del dispositivo o los flujos de inicio de sesión en OOBE. Comienza una sesión de inicio de sesión remoto.
  2.    El usuario verá una página de sondeo que contiene un URI breve ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) que señala al punto de conexión de autenticación del dispositivo del servicio de token de seguridad (STS) de Azure AD. El usuario también recibirá un código único que se genera de forma segura en la nube y que tiene una vigencia máxima de 15 minutos. Además de la generación del código, Azure AD también crea una sesión cifrada cuando comienza la solicitud de inicio de sesión remoto en el paso anterior y, en conjunto, el URI y el código se usan para aprobar la solicitud de inicio de sesión remoto. 
  3.    A continuación, el usuario se desplaza al URI del otro dispositivo donde se le pide que escriba el código que se muestra en su dispositivo HoloLens 2. 
  4.    Una vez que el usuario ha introducido el código, STS de Azure AD muestra una página que señala el dispositivo HoloLens 2 del usuario que desencadenó la solicitud de inicio de sesión remoto y solicitó la generación del código. Se pedirá la confirmación del usuario para evitar ataques de suplantación de identidad. 
  5.    Si el usuario decide seguir con el inicio de sesión en la "aplicación" que se muestra, STS de Azure AD le pide sus credenciales. Si la autenticación es correcta, STS de Azure AD actualiza la sesión remota en caché a "aprobada", junto con un código de autorización.
  6.    Por último, la página de sondeo del dispositivo HoloLens 2 del usuario recibe una respuesta de autorización de Azure AD y continúa con la validación del código de usuario y el código de autorización almacenado asociado, y genera tokens de OAuth como se solicitó para completar la configuración del dispositivo. El token de autenticación creado es válido durante una hora y el token de actualización tiene una vida útil de 90 días. 

Los algoritmos de generación y de cifrado de código utilizados en este flujo son compatibles con FIPS. Los dispositivos HoloLens 2 usan TPM para proteger las claves del dispositivo y cifrar los tokens generados después de la autenticación del usuario con claves protegidas por hardware. Para obtener más información sobre la seguridad de los tokens en HoloLens 2 vea [¿Qué es un token de actualización principal?](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token).

## Inicio de sesión en un dispositivo con Windows Hello

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) ofrece opciones sin contraseña integradas en el sistema operativo, lo que permite que los usuarios inicien sesión en el dispositivo con el iris o un PIN. El PIN siempre está disponible como una credencial y es necesario para la configuración del dispositivo, mientras que el iris es opcional y se puede omitir. Los usuarios pueden iniciar sesión en los dispositivos HoloLens por medio de su cuenta Microsoft personal o de la [cuenta de trabajo de Azure Active Directory *sin* introducir una contraseña](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless). Este tipo de opciones proporcionan a los usuarios acceso rápido y seguro a una experiencia completa de aplicaciones, datos, sitios web y servicios de Windows. Aquí se detalla la estrategia de Microsoft para las experiencias sin contraseñas.

Cuando se genera una credencial de Windows Hello, se establece una relación de confianza con el proveedor de identidades y se crea un par de claves asimétricas que se usa para la autenticación. Un gesto de Windows Hello (como el iris o el PIN) proporciona entropía para descifrar una clave privada respaldada por el chip del Módulo de plataforma segura (TPM) del dispositivo. Esta clave privada se usa para firmar solicitudes enviadas a un servidor de autenticación y, una vez que se autentica correctamente, concede acceso al usuario al correo electrónico, las imágenes y otras opciones de la cuenta. 

Para obtener más información, consulte los temas siguientes:

  ![Información de inicio de sesión en Winows Hello](images/security-hello-sign-in.png)
  
En el gráfico presentado más arriba, tenga en cuenta que nonce significa "número una vez" y es un número aleatorio o semialeatorio. Una vez configuradas las credenciales biométricas o el PIN de Windows Hello, nunca dejan el dispositivo en el que se aprovisionaron. Aunque al usuario le roben el PIN de Windows Hello, por ejemplo, a través de un ataque de suplantación de identidad (phishing), [será inútil sin el dispositivo físico del usuario](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password). 

Para mayor seguridad, las credenciales de Windows Hola están protegidas por el Módulo de plataforma segura (TPM) para que resistan intentos de manipulación. Esto se complementa con protecciones contra ataques de repetición (hammering) ante varias entradas incorrectas y protecciones contra software malintencionado para evitar la exposición. Para obtener más información sobre el inicio de sesión único (SSO), vea esta [información general sobre los métodos de SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).

Si la autenticación con el iris produce un error, se utiliza el PIN. Para configurar un nuevo PIN (un autenticador sólido) en el dispositivo, el usuario debe haber superado recientemente la [autenticación multifactor (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) para poder completar el proceso.

## Inicio de sesión único con el administrador de cuentas web 

El inicio de sesión único (SSO) permite que los usuarios sin contraseña inicien sesión en el dispositivo, usando la cuenta personal del usuario o su cuenta profesional o educativa. Con el SSO el usuario recibe autorización automáticamente en todas las aplicaciones y servicios integrados a través de las [API del administrador de cuentas web](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041).

Una vez que se ha agregado una identidad a través de una aplicación, puede, con el consentimiento del usuario, estar disponible para todas las aplicaciones y servicios mediante la integración a nivel de sistema. Esto reduce significativamente la carga de inicio de sesión de la aplicación y proporciona a los usuarios una experiencia de identidad ininterrumpida.

Para obtener más información sobre cómo implementar las API del administrador de cuentas web, vaya a [Implementar las API del administrador de cuentas web](https://docs.microsoft.com/windows/uwp/security/web-account-manager).

  ![Información de inicio de sesión en Winows Hello](images/security-api-img.png)
  
Para los conjuntos de aplicaciones con requisitos de autenticación especializados, el marco del administrador de cuentas web (WAM) se puede ampliar a los proveedores de identidades personalizadas. Los usuarios pueden descargar el proveedor de identidades personalizadas como una aplicación para la Plataforma universal de Windows (UWP) en la tienda de Microsoft para habilitar el SSO en otras aplicaciones integradas con ese proveedor de identidades. 

Para obtener más información sobre cómo implementar proveedores de identidades de WAM personalizadas, vea la [Referencia de API de identidades WAM personalizadas](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041).

## Inicio de sesión en Windows Hello y FIDO2 con WebAuthn

Con HoloLens 2 es posible usar credenciales de usuario sin contraseña (como las claves de seguridad de Windows Hello o FIDO2) para iniciar sesión de forma segura en la web a través de Microsoft Edge y en los sitios web que son compatibles con WebAuthn. FIDO2 habilita credenciales de usuario para que aprovechen los dispositivos basados en estándares para autenticarse en los servicios en línea.

> [!Note] 
> Las especificaciones [WebAuthn](https://www.w3.org/TR/webauthn/) y [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) de FIDO2 se implementan en los servicios. Los metadatos firmados especificados por WebAuthn y FIDO2 proporcionan información, por ejemplo, si el usuario se encontraba presente, y comprueban la autenticación con el gesto local.

Al igual que con Windows Hello, cuando el usuario crea y registra credenciales de FIDO2, el dispositivo (HoloLens 2 o la clave de seguridad de FIDO2) genera una clave pública y privada en el dispositivo. La clave privada se almacena de forma segura en el dispositivo y solo se puede usar después de que se desbloquee con un gesto local, como una credencial biométrica o un PIN. Cuando se almacena la clave privada, la clave pública se envía al sistema de la cuenta de Microsoft en la nube y se registra con la cuenta de usuario asociada.

Después de iniciar sesión con una cuenta MSA y AAD, el sistema envía una variable de datos o número generado al dispositivo HoloLens 2 o FIDO2. El dispositivo o HoloLens 2 usa la clave privada para firmar la identificación. La identificación firmada y los metadatos se envían al sistema de la cuenta de Microsoft y se contrastan con la clave pública.

Los dispositivos de Windows Hello y FIDO2 implementan credenciales basadas en el dispositivo HoloLens, específicamente el enclave seguro del Módulo de plataforma segura integrado. El enclave TPM almacena la clave privada y necesita una credencial biométrica o un PIN para desbloquearla. De forma similar, una clave de seguridad de FIDO2 es un pequeño dispositivo externo con un enclave seguro integrado que almacena la clave privada y requiere una credencial biométrica o un PIN para desbloquearla.

Ambas opciones ofrecen autenticación en dos fases en un único paso y requieren un dispositivo registrado y una credencial biométrica o un PIN para iniciar sesión correctamente. Para obtener más información, consulte el gráfico de autenticación sólida con clave de seguridad FIDO2, que se muestra a continuación:

  ![FIDO img](images/security-fido2-whfb.png)

MSA y AAD se encuentran entre los primeros servicios de confianza que admiten la autenticación sin contraseña a través de la implementación de WebAuthn. 

Para obtener más información sobre el uso de WebAuthn con aplicaciones o SDK, vaya a [API de WebAuthn para la autenticación sin contraseña en Windows 10](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis).

## Cuentas locales

Es posible configurar una única cuenta local para las implementaciones en modo sin conexión. Las cuentas locales no están habilitadas de forma predeterminada y deben configurarse durante el aprovisionamiento de dispositivos. Tienen que iniciar sesión con una contraseña y no admiten métodos de autenticación alternativos (como [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) o [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)). 

Puede obtener más información sobre las cuentas de usuario de HoloLens en [Identidad de HoloLens](https://docs.microsoft.com/hololens/hololens-identity). 

Los administradores de TI establecen si el usuario puede usar una cuenta de MSA para los servicios y la autenticación de la conexión no relacionada con correo electrónico a través de [AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Para conocer las directivas de configuración de contraseña, las directivas de inactividad y las directivas de bloqueo de pantalla, vea [DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock). 
