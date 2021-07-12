---
title: Solución de problemas de implementación y dispositivo administrado de HoloLens 2
description: Solución de problemas de dispositivos HoloLens 2 en un entorno empresarial
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Solución de problemas
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961508"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Solución de problemas de implementación y dispositivos administrados 

En este artículo se explica cómo resolver varios problemas o responder a preguntas sobre la implementación y la administración de HoloLens 2.

>[!IMPORTANT]
> Antes de iniciar cualquier procedimiento de solución de problemas, asegúrese de que el dispositivo tenga entre un **20 y un 40 por ciento** de batería, si es posible. Las [luces indicadoras de batería](hololens2-setup.md#lights-that-indicate-the-battery-level) que se encuentran debajo del botón de encendido son una manera rápida de comprobar la capacidad de la batería sin iniciar sesión en el dispositivo.


<a id="list"></a>
- [Solución de problemas de EAP](#eap-troubleshooting)
- [Solución de problemas de Wi-Fi](#wi-fi-troubleshooting)
- [Solución de problemas de red](#network-troubleshooting)
- [No se puede iniciar sesión en un dispositivo HoloLens ya configurado](#cant-sign-in-to-a-previously-setup-hololens-device)
- [No se puede iniciar sesión después de actualizar a Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Solución de problemas de Autopilot](#autopilot-troubleshooting)
- [Preguntas más frecuentes sobre dispositivos HoloLens administrados](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Solución de problemas de EAP
1. Asegúrese de que el perfil de Wi-Fi tiene la configuración adecuada:
    - El tipo de EAP está configurado correctamente, tipos comunes de EAP: EAP-TLS (13), EAP-TTLS (21) y PEAP (25).
    - El nombre de Wi-Fi (SSID) es correcto y coincide con la cadena hexadecimal.
    - En el caso de EAP-TLS, TrustedRootCA contiene el hash SHA-1 del certificado de entidad de certificación raíz de confianza del servidor. En el caso de un equipo Windows, el comando "certutil.exe -dump cert_file_name" muestra la cadena hash SHA-1 de un certificado.
2. Recopile la captura de paquetes de red en el punto de acceso o controlador o registros del servidor AAA para averiguar dónde se produce un error en la sesión de EAP.
    - Si la identidad de EAP proporcionada por HoloLens no es la esperada, compruebe si la identidad se ha aprovisionado correctamente mediante el perfil de Wi-Fi o el certificado de cliente.
    - Si el servidor rechaza el certificado de cliente de HoloLens, compruebe si el certificado de cliente necesario se ha aprovisionado en el dispositivo.
    - Si HoloLens rechaza el certificado de servidor, compruebe si el certificado de entidad de certificación raíz del servidor se ha aprovisionado en HoloLens.
3. Si el perfil empresarial se aprovisiona mediante el paquete de aprovisionamiento Wi-Fi, considere la posibilidad de aplicar el paquete de aprovisionamiento en un equipo con Windows 10. Si también se produce un error en un equipo con Windows 10, siga la guía de solución de problemas de autenticación del cliente Windows 802.1X.
4. Envíe sus comentarios por medio del Centro de opiniones.

[Volver a la lista](#list)

## <a name="wi-fi-troubleshooting"></a>Solución de problemas de Wi-Fi

Estas son algunas de las cosas que debe intentar si no puede conectar HoloLens a una red Wi-Fi:

1. Asegúrese de que la Wi-Fi está activada. Para ello, use el gesto Inicio y seleccione Configuración > Red e Internet > Wi-Fi. Si la Wi-Fi está activada, intente desactivarla y volver a activarla.
2. Acérquese al enrutador o al punto de acceso.
3. Reinicie el enrutador Wi-Fi y luego HoloLens. Try connecting again (Intente conectarse de nuevo).
4. Si ninguna de estas cosas funciona, asegúrese de que el enrutador usa el firmware más reciente. Puede encontrar esta información en el sitio web del fabricante.

Al iniciar sesión en una cuenta empresarial u organizativa en el dispositivo, también puede aplicarse la directiva de Administración de dispositivos móviles (MDM) si el administrador de TI la ha configurado.

## <a name="network-troubleshooting"></a>Solución de problemas de red
Si los problemas de red son un obstáculo para implementar y usar correctamente HoloLens 2 en la organización, obtenga información sobre cómo dos conocidas herramientas de diagnóstico de red, Fiddler y Wireshark, pueden ayudarle a examinar, diagnosticar e identificar problemas. Vea este [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) para obtener más detalles.

[Volver a la lista](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>No se puede iniciar sesión en un dispositivo HoloLens ya configurado

Si el dispositivo se ha configurado previamente para otra persona, ya sea para un cliente o para un ex-empleado, y no tiene su contraseña para desbloquearlo, puede usar Intune para [borrar](https://docs.microsoft.com/intune/remote-actions/devices-wipe) el dispositivo de forma remota. Entonces el dispositivo se reprograma automáticamente.  
> [!IMPORTANT]
> Al borrar el dispositivo, asegúrese de dejar desactivada la opción **Conservar el estado de inscripción y la cuenta de usuario**.
[Volver a la lista](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>No se puede iniciar sesión después de actualizar a Windows Holographic 21H1

### <a name="symptoms"></a>Síntomas
- Se produce un error en el uso de PIN para iniciar sesión después de escribir el PIN correcto.
- Se produce un error en el uso del método de inicio de sesión web después de iniciar sesión correctamente en la página web.
- El dispositivo no aparece como "Unido a Azure AD" en [Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Dispositivos.

### <a name="cause"></a>Causa
Es posible que el dispositivo afectado se haya eliminado del inquilino de Azure AD. Por ejemplo, esto puede ocurrir porque:

- Un administrador o usuario ha eliminado el dispositivo en Azure Portal o mediante PowerShell.
- El dispositivo se ha quitado del inquilino de Azure AD por inactividad. Para tener un entorno administrado de manera eficaz, normalmente se recomienda a los administradores de TI [quitar dispositivos obsoletos e inactivos del inquilino de Azure AD](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).

Cuando un dispositivo afectado intenta ponerse en contacto de nuevo con el inquilino de Azure AD después de que se haya eliminado, no puede autenticarse con Azure AD. Este efecto suele ser invisible para el usuario del dispositivo, ya que el inicio de sesión almacenado en caché mediante PIN sigue permitiéndole iniciar sesión.

### <a name="mitigation"></a>Mitigación
Actualmente no hay ninguna manera de volver a agregar un dispositivo HoloLens eliminado a Azure AD. Los dispositivos afectados tienen que reprogramarse con las instrucciones para [Reprogramar el dispositivo](hololens-recovery.md#clean-reflash-the-device).

## <a name="autopilot-troubleshooting"></a>Solución de problemas de Autopilot

Los siguientes artículos pueden ser un recurso útil para obtener más información y solucionar problemas de Autopilot, pero tenga en cuenta que se basan en el escritorio de Windows 10 y no toda la información puede aplicarse a HoloLens:

- [Windows Autopilot: problemas conocidos](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Solución de problemas con la inscripción de dispositivos Windows en Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: conflictos de directivas](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Preguntas más frecuentes sobre dispositivos HoloLens administrados

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>¿Puedo usar System Center Configuration Manager (SCCM) para administrar dispositivos HoloLens?

No. Debe usar un sistema de MDM para administrar dispositivos HoloLens.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>¿Puedo usar Active Directory Domain Services (AD DS) para administrar cuentas de usuario de HoloLens?

No. Tiene que usar Azure Active Directory (Azure AD) para administrar cuentas de usuario de dispositivos HoloLens.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>¿Es capaz HoloLens de inscribirse automáticamente en Sistemas de captura de datos automatizados (ADCS)?

No.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>¿Puede HoloLens participar en la autenticación de Windows integrada?

No.

### <a name="does-hololens-support-branding"></a>¿HoloLens admite la personalización de marca?

No. Pero puede solucionar este problema si usa uno de los enfoques siguientes:

- Cree una aplicación personalizada y [habilite el modo de pantalla completa](hololens-kiosk.md). La aplicación personalizada puede tener personalización de marca y puede iniciar otras aplicaciones (como Remote Assist).  
- Cambie todas las imágenes de perfil de usuario de Azure AD por el logotipo de la empresa. Sin embargo, esto puede no ser deseable en todos los escenarios.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>¿Qué capacidades de registro ofrece HoloLens 2?

El registro se limita a los seguimientos que se pueden capturar en escenarios de desarrollo o solución de problemas, o a telemetría que los dispositivos envían a los servidores de Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Preguntas sobre la protección de los dispositivos HoloLens

Vea la [información de seguridad de HoloLens 2](security-overview.md).
En el caso de los dispositivos HoloLens de primera generación, revise estas [Preguntas frecuentes](hololens1-faq-security.md).

[Volver a la lista](#list)
