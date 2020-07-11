---
title: Configurar HoloLens en un entorno comercial
description: Más información sobre cómo implementar y administrar HoloLens en entornos empresariales.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865569"
---
# Implementar HoloLens en un entorno comercial

Puedes implementar y configurar HoloLens a escala en una configuración comercial. En este artículo se proporcionan instrucciones para implementar dispositivos HoloLens en un entorno comercial. En esta guía se presupone la familiaridad básica con HoloLens. Sigue la [Guía](hololens1-setup.md) introducción para configurar HoloLens por primera vez.

En este documento también se supone que los equipos de seguridad han evaluado la función HoloLens como segura para usarse en la red corporativa.  
> [!Tip]
> Más información sobre la [seguridad de HoloLens](security-overview.md).
> Para obtener la seguridad de HoloLens (1ª generación), consulta [esta pregunta frecuente](hololens1-faq-security.md).

## Información general sobre los pasos de implementación

1. [Determinar qué características necesita](hololens-requirements.md#step-1-determine-what-you-need)
1. [Determinar qué licencias se necesitan](hololens-licenses-requirements.md)
1. [Configura tu red para HoloLens](hololens-commercial-infrastructure.md).
    1. Esta sección incluye los requisitos de ancho de banda, la dirección URL y los puertos que deben permitirse en el Firewall; Guía de Azure AD; Guía de administración de dispositivos móviles (MDM); Guía de implementación y administración de aplicaciones; y la guía de certificados.
1. Faculta [Configurar HoloLens con un paquete de aprovisionamiento](hololens-provisioning.md)
1. [Dispositivo de inscripción](hololens-enroll-mdm.md)
1. [Configurar actualizaciones de HoloLens basadas en anillos](hololens-updates.md)
1. [Habilitar el cifrado de dispositivo de Bitlocker para HoloLens](security-encryption-data-protection.md)

## Paso 1. Determinar lo que necesita

Antes de implementar HoloLens en el entorno, es importante determinar primero qué características, aplicaciones y tipo de identidades son necesarias. También es importante asegurarse de que el equipo de seguridad haya aprobado el uso de HoloLens en la red de la empresa. Para obtener más información sobre seguridad, consulta [HoloLens2 seguridad](security-overview.md) .

### Tipo de identidad

Determine el tipo de identidad que se usará para iniciar sesión en el dispositivo.

1. **Cuentas locales:** Esta cuenta es local para el dispositivo (como una cuenta de administrador local en un equipo con Windows). Esto permitirá que solo 1 usuario inicie sesión en el dispositivo.
2. **MSA:** Esta es una cuenta personal (como Outlook, hotmail, gmail, Yahoo, etc.) Esto permitirá que solo 1 usuario inicie sesión en el dispositivo.
3. **Cuentas de Azure Active Directory (Azure ad):** Esta es una cuenta creada en Azure AD. Esto otorga a su corporación la capacidad de administrar el dispositivo HoloLens. Esto permitirá que varios usuarios inicien sesión en el dispositivo de la primera generación comercial de HoloLens/HoloLens.

Para obtener información más detallada sobre los tipos de identidad, visita nuestro artículo de [identidad de HoloLens](hololens-identity.md) .

### Tipo de características

Los requisitos de tu característica determinarán qué HoloLens necesitas. Una característica popular que vemos implementada en entornos de cliente con frecuencia es el modo de pantalla completa. [Aquí](hololens-commercial-features.md)puedes encontrar una lista de características clave de hololens y las ediciones de HoloLens que las admiten.

**¿Qué es el modo de pantalla completa?**

El modo de pantalla completa es una forma de restringir las aplicaciones a las que tiene acceso los usuarios. Esto significa que los usuarios solo tendrán permiso para acceder a determinadas aplicaciones.

**¿Qué modo de quiosco necesito?**

Existen dos tipos de modos de pantalla completa: una sola aplicación y varias aplicaciones. El modo de pantalla única de la aplicación permite que el usuario solo tenga acceso a una aplicación mientras que el modo quiosco de varias aplicaciones permite a los usuarios acceder a varias aplicaciones especificadas. Para determinar qué modo de pantalla completa es adecuado para su corporación, deben contestarse las dos preguntas siguientes:

1. **¿Diferentes usuarios necesitan diferentes experiencias y restricciones?** Considere el ejemplo siguiente: el usuario A es un ingeniero de servicio de campo que solo necesita acceso a asistencia remota. El usuario B es un aprendiz que solo necesita acceder a las guías.
    1. En caso afirmativo, necesitará lo siguiente:
        1. Cuentas de Azure AD como método para iniciar sesión en el dispositivo.
        1. Modo quiosco **de varias aplicaciones** .
    1. En caso de no hacerlo, continúa con la pregunta dos
1. **¿Necesita una experiencia de varias aplicaciones?**
    1. Si el valor es sí, se necesita la pantalla completa **de varias aplicaciones** .
    1. Si su respuesta a las preguntas 1 y 2 no es así, puede usar el modo de pantalla completa **de una sola aplicación** .

**Cómo configurar el modo de pantalla completa:**

Hay dos formas principales ([paquetes de aprovisionamiento](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) y [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) para implementar el modo de pantalla completa para HoloLens. Estas opciones se tratarán más adelante en el documento; sin embargo, puedes usar los vínculos anteriores para ir a las secciones respectivas de este documento.

### Escenarios específicos de aplicaciones y aplicaciones

La mayoría de los pasos que se encuentran en este documento también se aplicarán a las siguientes aplicaciones:

| Aplicación | Escenarios específicos de aplicaciones |
| --- | --- |
| Asistencia remota | [Comunicación entre inquilinos](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| Guías  | *Próximamente* |
|Aplicaciones personalizadas | *Próximamente* |

### Determinar el método de inscripción

1. Inscripción en masa con un token de seguridad en un paquete de aprovisionamiento.  
  Ventajas: este es el enfoque más automatizado \
  Cons: toma la configuración inicial del servidor  
1. Inscriba automáticamente en el inicio de sesión de usuario.  
  Ventajas: enfoque más fácil  
  Cons: los usuarios deberán completar la configuración una vez que se haya aplicado el paquete de aprovisionamiento.
1. _no recomendado_ : inscriba manualmente después de la instalación.  
  Ventajas: posible inscripción después de la configuración  
  Cons: la mayoría de los métodos y los dispositivos manuales no se pueden administrar de forma centralizada hasta que se inscriban de forma manual.

  Puede encontrar más información [aquí](hololens-enroll-mdm.md)

### Determinar si necesita crear un paquete de aprovisionamiento

Existen dos métodos para configurar un dispositivo HoloLens (paquetes de aprovisionamiento y MDMs). Te sugerimos que uses tu MDM para configurar el dispositivo HoloLens. Sin embargo, hay algunos escenarios en los que el uso de un paquete de aprovisionamiento es la mejor opción:

1. Deseas configurar HoloLens para omitir la configuración rápida (OOBE)
1. Tiene problemas para implementar un certificado en una red compleja. La mayoría de las veces, puede implementar certificados con MDM (incluso en entornos complejos). Sin embargo, algunos escenarios requieren que los certificados se implementen a través del paquete de aprovisionamiento.

Algunas de las configuraciones de HoloLens que se pueden aplicar en un paquete de aprovisionamiento son:

- Aplicar certificados al dispositivo
- Configuración de una conexión Wi-Fi
- Dudas preconfiguradas (como el idioma y la configuración regional)
- (HoloLens 2) inscripción en masa en la administración de dispositivos móviles
- (HoloLens V1) Aplicar la clave para habilitar Windows Holographic para Empresas

Si decide usar paquetes de aprovisionamiento, siga [esta guía](hololens-provisioning.md).

## Obtener soporte técnico

Obtenga asistencia a través del sitio de soporte técnico de Microsoft.

[Archivar una solicitud de asistencia](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
